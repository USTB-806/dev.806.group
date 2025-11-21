# 面向对象
```python
class Student(object):
    def __init__(self, name, score):
        self.name = name
        self.score = score

    def print_score(self):
        print('%s: %s' % (self.name, self.score))
```
若想将这里代码中的name，score变成private，只需在其名称前加两个下划线
```python
class Student(object):
    def __init__(self, name, score):
        self.__name = name
        self.__score = score

    def print_score(self):
        print('%s: %s' % (self.__name, self.__score))
```
在Python中，变量名类似__xxx__的，也就是以双下划线开头，并且以双下划线结尾的，是特殊变量，特殊变量是可以直接访问的，不是private变量，所以，不能用__name__、__score__这样的变量名。
```python
>>> bart = Student('Bart Simpson', 59)
>>> bart.get_name()
'Bart Simpson'
>>> bart.__name = 'New Name' # 设置__name变量！
>>> bart.__name
'New Name'
```
表面上看，外部代码“成功”地设置了__name变量，但实际上这个__name变量和class内部的__name变量不是一个变量！内部的__name变量已经被Python解释器自动改成了_Student__name，而外部代码给bart新增了一个__name变量。
# 继承和多态（类比c++）
```python
class Animal(object):
    def run(self):
        print('Animal is running...')
class Dog(Animal):
    pass

class Cat(Animal):
    pass
dog = Dog()
dog.run()

cat = Cat()
cat.run()
```
>Animal is running...
>
>Animal is running...

以上为继承，即子类可以继承父类的方法deng
```python
class Dog(Animal):
    def run(self):
        print('Dog is running...')

    def eat(self):
        print('Eating meat...')
```
>Dog is running...
>
>Cat is running...

当子类中的一些方法与父类重名，则会覆盖父类原来的方法，此为多态

有些需要注意的点是：
__xxx__的属性和方法在python帐都是有特殊用途的，比如__len__方法是返回长度
```python
>>>len('abc')
3
>>>'abc'.__len__()
3
```
如果自己创建的类，也想用len，需要自己写一个__len__()方法

hasattr(obj,'x')#判断obj对象中是否有x对象

setattr(obj,'y',19)#对obj对象设置一个新的属性，设初值为19

getattr(obj,'y')#获取属性‘y'

getattr(obj,'z',404)#获取属性'z'，如果不存在，返回默认值404

isinstance(h，husky)判断h是否是husky类
