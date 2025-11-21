# 请求体的更高级用法
## 多个参数
### 混合使用path，query和请求体参数
```python
from typing import Annotated, Union

from fastapi import FastAPI, Path
from pydantic import BaseModel

app = FastAPI()


class Item(BaseModel):
    name: str
    description: Union[str, None] = None
    price: float
    tax: Union[float, None] = None


@app.put("/items/{item_id}")
async def update_item(
    item_id: Annotated[int, Path(title="The ID of the item to get", ge=0, le=1000)],
    q: Union[str, None] = None,
    item: Union[Item, None] = None,
):
    results = {"item_id": item_id}
    if q:
        results.update({"q": q})
    if item:
        results.update({"item": item})
    return results
```
### 多个请求体参数
```python
@app.put("/items/{item_id}")
async def update_item(item_id: int, item: Item, user: User):
    results = {"item_id": item_id, "item": item, "user": user}
    return results
```

### 请求体中的单一值
有时想加入一个请求体，但是它是一个单一值，会被fastapi默认为查询参数，可以使用Body让fastapi把它看作为请求体

```python
@app.put("/items/{item_id}")
async def update_item(
    item_id: int, item: Item, user: User, importance: Annotated[int, Body()]
):
    results = {"item_id": item_id, "item": item, "user": user, "importance": importance}
    return results
```
在这种情况下，fastapi将期望像这样的请求体：
{
    "item": {
        "name": "Foo",
        "description": "The pretender",
        "price": 42.0,
        "tax": 3.2
    },
    "user": {
        "username": "dave",
        "full_name": "Dave Grohl"
    },
    "importance": 5
}
### 多个请求体参数和查询参数

由于默认情况下单一值被解释为查询参数，因此不必显式地添加 Query，你可以仅执行以下操作

>q: str = None

### 嵌入单个请求体参数
也就是将这种期望
```json
{
    "name": "Foo",
    "description": "The pretender",
    "price": 42.0,
    "tax": 3.2
}
```
转变成这种
```json
{
    "item": {
        "name": "Foo",
        "description": "The pretender",
        "price": 42.0,
        "tax": 3.2
    }
}
```

也就是说多显示一个键，可以使用Body(embed=True)

可以将代码中

>async def update_item(item_id: int, item: Item)

转变为

>async def update_item(item_id: int, item: Annotated[Item, Body(embed=True)])

## 字段
导入Field(Pydantic提供)
```python
from typing import Annotated, Union

from fastapi import Body, FastAPI
from pydantic import BaseModel, Field

app = FastAPI()


class Item(BaseModel):
    name: str
    description: Union[str, None] = Field(
        default=None, title="The description of the item", max_length=300
    )
    price: float = Field(gt=0, description="The price must be greater than zero")
    tax: Union[float, None] = None


@app.put("/items/{item_id}")
async def update_item(item_id: int, item: Annotated[Item, Body(embed=True)]):
    results = {"item_id": item_id, "item": item}
    return results
```
与Query，Path，Body的工作方式相同，参数也相同，只不过Field作用在pydantic内部











