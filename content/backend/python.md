---
title: "python"
date: 2025-11-35
draft: false
---

## python
- 输入输出与变量赋值    
    - 输出
        - print("string")
        - print(int)
        - print(float)
        - print(f"提示：{ }")
    - 输入
        - input("提示")
        - input的是字符串
    - 变量赋值
        - a=xxx(令a=xxx)
        - a，b为数字
            - a+b：相加
        - a，b为字符串
            - a+b：字符串连接
        - 类型转换
            - int(),string()
- 逻辑运算和条件判断
    - 逻辑运算
        - and
        - or
        - not
    - 条件判断
        - if
            - if(条件)：
            - elif(条件)：
            - else：
- 迭代循环
    - for
        - for <变量> in <迭代的对象>:<语句> 
        - for i in a:
        - for i in range(0,20,1):  
            - 可简写 range(20)
        - continue
        - break
- 条件循环
    - while
        - while <条件>:<语句体>
    - /:除法(float)
    - //:整除(int)
- 变量类型
    - 整型 int
    - 浮点型 float
    - 字符串 str
    - [] list 列表
    - () tuple 元组
    - {} set 集合
    - {:} dict 字典
    - 变量类型
        - type()
            - <class '类型'>
    - isinstance(1,int)
    - int() 向下取整
    - round() 四舍五入 
    - round(1.11111,2)(保留两位小数)
    - int("A") 报错
- 数学函数
    - 次方
        - 4**2
        - pow(4,2)
    - import math —— 导入数学库
        - math.sin
        - math.e
        - math.log
        - math.sqrt —— 平方根
        - math.hypot —— 三角形斜边
        - math.pi
- 字符串
    - 字符串
        - a = "XXX"
        - a = 'XXX'
        - a = """ """ —— 存储超文本
    - 转义字符
        - 换行：\n
        - 对齐：\t
    - 特别
        - 数乘
            - print("A" * 100)
        - 索引
            - "ABCD"[0] —— 第一个元素
            - "ABCD"[-1] —— 倒数第一个元素
            - "ABCD"[0：2] —— 第一个和第二个元素（左闭右开）
            - a.count("o") —— o在字符串a中出现几次
            - a.upper() —— a的所有字母变大写
            - a.lower() —— a的所有字母变小写
            - a.find("i") —— i在字符串a的第几位
            - print("XXX:{}".format(100))
                - {} 占位符
                - print("XXX:{}，XXX:{}".format(100,"A"))
                - print("XXX:{1}，XXX:{0}".format(100,"A"))
                - print("XXX:{a}，XXX:{b}".format(a=100,b="A"))
                - print(f"XXX:{100}")
                - print(f"{1/3:.2f}")
- 列表和元组
    - 列表（list）
        - 表示列表
            - a = [1,2,3,4]
            - a = list("abcd")
            - a = list(range[10])
            - a = [1,2,3.'a','b']
        - 列表函数
            -  a.append(1) —— 把1添加到列表最后
            -  a.remove(1) —— 把在列表中找到的第一个1删除
            -  b = a.pop() —— 把列表最后一个元素删除并返回给b
            -  a.pop(0) —— 把列表第0个位置的元素删除
            -  a.extend([1,2,3.4]) —— 把列表[1,2,3,4]添加到a列表最后
            -  a.reverse() —— 把列表反转
            -  a.insert(0.1) —— 把1插入列表的第0个位置
            -  len(a) —— a列表的长度
            -  a.sort —— a列表从小到大排序
            -  a.sort(reverse = True) —— a列表从大到小排序
            -  a.clear —— 清空列表
            -  a.count(1) —— 列表中1出现了几次 
            -  b = a.copy()或b = a.[:]
            -  min(a)
            -  max(a)
            -  a = None —— 把a设为空
    - 元组（tuple）
        - 表示元组
            - a = (1,2,3)
            - 元组可以理解为只读的列表
            - c = tuple(b) —— 把列表b转换为元组
- 推导式
    - 简化代码
    - 一个可迭代对象生成另一个相关联可迭代对象
    - list(range(5))
    - list(str(i) for i in a)
        - list内部的内容是建立了生成器对象
        - 简写：[str(i) for i in a]
    - tuple(str(i) for i in a)
    - [str(i) for i in a if i > 1]
    - [i for i in a for j in range(3)]
- 集合（set）
    - 集合表示
        - a = {1,2,3,1} —— {1,2,3}
        - set() —— 空集合
        - a = set([1,2,3,1]) —— {1,2,3}
    - 集合函数
        - a.add(1) —— 把1添加到集合
        - a.remove(2) —— 把2从集合移除（若2不存在会报错）
        - a.discard(2) —— 把2从集合移除（若2不存在不会报错）
        - 判断：if 1 in a
    - 集合运算
        - a.intersection(b) —— a与b的交集
            - a & b
        - a.union(b) —— a与b的并集
            - a | b
        - a.difference(b) —— a与b的差集（a有b没有）
            - a - b
        - a.symmetric(b) —— a与b的对称差集（a，b独有）
            - a ^ b
- 字典（dict）
    - 语法
        - d = {'key' : value} —— key：键 value：值
        - d['a'] = 0 —— 设置字典中的a元素
        - print(d['a']) —— 获取字典中的元素
        - del d['a'] —— 删除字典中的a
        - d.get('b',0) —— 尝试获取d中b的值，如果没有就返回默认值0
        - 'c' in d —— 判断d中是否有键
        - for key in a.keys() —— 遍历a中的所有键
        - for key,value in a.items() —— 遍历a中的所有键值对
            - 后出现的键值会把之前的覆盖
        - a.update(b) —— 用b更新a
        - d = {key : key * key for key in range(100)}
- 异常处理
    - ```
        try:
            name = input("请输入姓名")
            print("当前的年龄是"，age_data[name])
            new_age = int(input("请输入年龄："))

            if new_age <=0:
                raise ValuError("age must be positive")
            age_data[name] = new_age
        except VauleError as e:
            print("输入不合法")
            print("异常原因是",e)
        except KeyError as e:
            print("人名不存在")
            print("异常原因是",e)
        else：
            print("无事发生")
        finally:
            print("运行完成")
    - 异常类型
        - 可使用pass进行占位
            - if XX:pass
            - except except VauleError as e:pass