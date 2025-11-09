---
title: "前端开发"
date: 2025-11-03
draft: false
---

## JavaScript
- 概述
    - JavaScript简介 
        - 简称JS
        - 是一种轻量级、解释型、面向对象的脚本语言
        - 主要用于在网页上实现动态效果，增加用户与网页的交互性
    - 作用
        - 客户端脚本：用于在用户浏览器中执行，实现动态效果和用户交互
        - 网页开发：与HTML、CSS协同工作，使得网页具有更强的交互性和动态性
        - 后端开发：使用Node.js，JavaScript也可以在服务器端运行，实现服务器端应用的开发 
    - 导入方式
        - 内联式
            - ```
                <body>
                    <script>
                    </script>
                </body>
              ```
        - 外部引入
            - ```<script src="./js/myscript.js"></script>```
- 基本语法
    - 变量
        - var：变量，具有函数作用域
        - let：变量，具有块级作用域，更安全灵活
        - const：常量
    - 数据类型
        - 整型
        - 浮点型
        - 字符串
        - 空值
            - undefined：变量已声明，但未被赋值
                - let a;
            - null：明确表示没有对象值
                - let a=null;
    - 控制语句
        - 条件语句
            - if(condition){
            }
            - else if(condition){
            }
            - else{
            }
        - 循环语句
            - for循环
                - for(初始化表达式；循环条件；迭代器){
                }
            - while循环
                - while(循环条件){
                }
            - 循环关键字
                - break：跳出循环
                - continue：跳过循环剩余代码
    - 函数
        - function function_name(参数1,参数2,参数3...){
            return 返回值;
        }
        - 作用域
            - 函数内声明：函数作用域
            - 函数外声明：全局作用域
    - 常用语法
        - console.log(example)
            - 在控制台Console处打印example
        - alert(example)
            - 弹窗显示example
    - 事件
        - 定义
            - 文档或浏览器窗口中发生的特定瞬间
            - 如用户点击，键盘按下，页面加载
        - 常见事件
            - onClick：点击事件
            - onMouseOver：鼠标经过
            - onMouseOut：鼠标移出
            - onChange：文本内容改变事件
            - onSelect：文本框选中
            - onFocus：光标聚集
            - onBlur：移开光标
        - 事件绑定
            - HTML属性
            - DOM属性
            - addEventListener方法
    - DOM
        - DOM（Document Object Model）文档对象模型
        - DOM为文档树提供了一个编程接口，可通过JS来操作这个树状结构
        - DOM API
            - 获取元素节点方法
                - document.getElementById
                - document.getElementsByClassName
                - document.getElementsByName
                - document.getElementsByTagName
                - document.getElementsByTagNameNS
            - 修改标签方法
                - .innerHTML
                    - 可解析HTML 
                - .innerText
                    - 忽略HTML标签
            - 修改样式方法
                - .style.color='red'
                - .style.fontsize='20'
            - DOM属性绑定事件
                - ```
                    <button>example</button>

                    var button_element=getElementsByTagName('button')[0]
                    button_element.onclick=function(){
                        alert('example')
                    }
                  ```
                - ```
                    <button>example</button>

                    var button_element=getElementsByTagNam('button')[0]
                    button_element.addEventListener('click',function(){
                        alert('example')
                    })
                  ```
            - DOM对象常用方法
                - appendChild()
                    - 把新的子节点添加到指定节点
                - removeChild()
                    - 删除子节点
                - replaceChild()
                    - 替换子节点
                - insertBefore()
                    - 在指定节点前插入新的子节点
                - createAttribute()
                    - 创建属性节点
                - createElement()
                    - 创建元素节点
                - creatTextNode()
                    - 创建文本节点
                - getAttribute()
                    - 返回指定的属性值
