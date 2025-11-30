---
title: "python"
date: 2025-11-25
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
- 函数
    - 函数定义
        - def 函数名(参数列表):语句块(代码块) return [返回值](可选)
        - 语句块部分不能省略，若为空语句要填充pass
        - return [表达式] 结束函数，不带表达式的return相当于返回None
    - 参数传递
        - 位置传递
        - 关键字传递
        - 序列传递
            - ```
                def myfun(a,b,c):
                    print("a-->",a)
                    print("b-->",b)
                    print("c-->",c)

                s1 = [11,22,33]
                myfun(*s1) 

                s2 = (1.1,2.2,3.3)
                myfun(*s2)

                s3 = "ABC"
                myfun(*s3)
        - 字典关键字传递
            - ```
                def myfun(a,b,c):
                    print("a-->",a)
                    print("b-->",b)
                    print("c-->",c)

                d1 = {'a':100,'b':200,'c':300}
                myfun(**d1)
            - 字典传参的键名和形参名必须一致
            - 键名要在形参中存在
        - 综合传递
            - 以上几种方式的混合使用
    - 缺省参数
        - 形参被赋予默认参数值，函数在调用时使用默认值计算
        - 缺省参数必须从右至左依次存在
        - 缺省参数可以有0个或多个，甚至可以全都是
    - 函数参数列表顺序
        - 位置形参
        - 星号元组形参
        - 命名关键字参数
        - 双星号字典形参
        - 默认
    - 函数的不定长参数
        - 星号元组形参
            - 语法
                - ```
                    def 函数名(*元组形参名)
                        语句块
        - 命名关键字形参
            - 语法
                - ```
                    def 函数名(*,命名关键字形参名)
                        语句块  
        - 双星号字典形参
            - 语法
                - ```
                    def 函数名(**字典形参名)
                        语句块
        - 可变/不可变类型
            - 可变
                - 列表list
                - 集合set
                - 字典dict
            - 不可变
                - frozenset
                - tuple
                - str
                - numbers
- 函数作用域
    - 全局变量与局部变量
        - 全局变量
            - 定义在函数外部，模块内部的变量
        - 局部变量
            - 定义在函数内部的变量，包含函数参数
    - python作用域
        - 作用域
            - python程序的一块文本区域，是变量或函数访问的时候查找名称的范围空间
        - 4个作用域
            - 局部作用域（函数内）：Local（L）
            - 外部嵌套函数作用域：Enclosing function locals（E）
            - 函数定义所在模块（文件）的作用域：Global（module）(G)
            - Python内置模块的作用域：Built-in（Python）(B)
            - L > E > G > B
    - 全局与局部作用域
        - 全局声明
            - global语句
                - 作用：告诉解释器，global语句声明的一个或多个变量，这些变量的作用域为模块级作用域
        - 函数嵌套
            - nonlocal语句
                - 作用：告诉解释器，nonlocal声明的变量不是局部变量，也不是全局变量，而是外部嵌套函数的变量
        - globals()/locals()函数
            - globals()函数
                - 返回房前全局作用域内变量的字典
            - locals()函数
                - 返回当前局部作用域内变量的字典
        - 函数式编程思想
    - 高阶函数
        - 定义
            - 函数接受一个或多个函数作为参数传入
            - 函数返回一个函数（二者满足一个即可）
    - 生成器
        - 是一种创建迭代器的方法
        - 封装可控制结构的内置模板函数
        - map函数
            - map(func，*iterable)
            - 用函数func和可迭代对象iterable中的每个元素作为参数计算出新的可迭代对象，当最短的一个可迭代对象完成迭代后此迭代生成结束
        - reduce函数
            - reduce(function,iterable[,initiallizer])
            - 对参数序列中的元素进行累计
        - filter函数
            - filter(function,iterable)
            - 筛选iterable中的数据，返回一个可迭代对象，此可迭代对象将对iterable进行筛选
            - 会对iterable里的每个元素进行求值，返回false则将数据丢弃，返回true则保留
        - sorted函数
            - 将可迭代对象的数据进行排序，生成排序后的列表，升序
            - sorted(iterable,key=None,reverse=False)
    - 迭代器
    - lambda表达式（匿名函数）
        - 创建一个匿名函数对象，同def，但不提供函数名
        - lambda [参数1，参数2...]:表达式
        - eg:myadd=((lambda a,b:a+b),100,200)
    - 递归
        - 函数直接或间接调用自身
    - 闭包
        - 将组成函数的语句和这些语句的执行环境打包在一起
        - 如果一个内嵌函数访问函数外部作用域的变量
    - 装饰器
        - 是一个函数，主要作用是用来包装另一个函数或类
        - 目的是在不改变原函数的情况下，改变被包装函数（对象）的行为
        - 装饰器函数
            - def 装饰器函数名(参数):函数块 return 函数
- 模块
    - 定义
        - 模块是一个包含一系列变量，函数，类等组成的程序组
        - 模块是一个文件，通常以.py结尾
    - 作用
        - 让一些相关的变量、函数、类等有逻辑的组织在一起，让逻辑更加清晰
        - 模块中的变量、函数和类等可供其他模块或程序使用
    - 分类
        - 内置模块
        - 安装的标准库模块
        - 第三方模块
        - 用户自己编写的模块
    - 模块导入
        - import 语句
            - import 模块名1 [as 模块新名1]，模块名2 [as 模块新名2]
            - eg：import math、import sys，os
            - 作用：将某木哦快整体导入到当前模块
            - 用法：模块名.属性名
                - eg：math.sin(3.14)
            - help(obj)函数：可查看模块相关的文档字符串
            - dir(obj)函数：返回模块所有属性的字符串列表
        - from import语句
            - from 模块名 import 模块属性名1 [as 属性别名1],import 模块属性名2 [as 属性别名2],...
            - 作用：将某模块内的一个或多个属性导入当前模块
            - eg：from math import sin，from math import pi，from math import factorial as fac
        - from import * 语句
            - from 模块名 import *
            - 将某模块的所有属性导入当前模块
            - eg：from math import *
        - 自定义模块的编写
        - 模块的搜索路径
            - import 模块名 #对应 模块名.py 去哪找
        - PYTHONPATH环境变量
        - 模块的属性
            - __name__
                - 模块名字
            - __doc__
                - 绑定模块的文档字符串
            - __all__
                - 存放可导出属性的列表
            - __file__
                - 用来记录模块对应文件路径名
            - 隐藏属性
                - 以'_'或'__'开头，在from import *语句导入时不被导入其他模块
    - 包（模块包） package 
        - 定义
            - 将模块以文件夹的组织形式进行分组管理的方法
        - 作用
            - 将一系列模块进行分类管理，有利于防止名字冲突
            - 可以在需要时加载一个或部分模块而不是全部模块
        - 包的加载
            - import 包名 [as 包别名]
            - import 包名.模块名 [as 模块别名]
            - import 包名.子包名.模块名 [as 模块别名]