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
- 移动端布局
    - 响应式布局方法
        - 通过rem，vw/vh等单位，实现在不同设备上显示相同比例而适配
        - 响应式布局，通过媒体查询@media实现一套HTML配合多套CSS实现适配
    - Viewport
        - viewport——视区，视口
            - 指浏览器用来显示网页的区域，决定了网页在用户设备上的显示效果
        - width=device-width：将视口的宽度设置为屏幕的宽度，确保网页内容不会被缩放，按照设备的实际宽度进行布局
        - initial-scale=1.0：设置初始缩放级别为1.0，有助于确保网页在加载时以原始大小显示，而不被放大缩小
        - minmum-scale=1.0：最小缩放比例为1
        - maxmum-scale=1.0：最大缩放比例为1
        - user-scalable=no：不允许用户缩放
    - rem
        - 在响应式布局与移动端布局中，使用rem而不是px
        - rem是一个倍数单位，基于html中的font-size属性值的倍数
        - 利用js设置在不同设备下的font-size值
- Flex弹性盒子
    - Flex盒子模型
        - 采用Flex布局的元素，成为Flex容器（flex container），它所有子元素成为容器成员，称为Flex项目（flex item）
        - flex container
          - main axis：主轴
          - cross axis：交叉轴
          - main start
          - main end
          - cross start
          - cross end
        - flex item
          - main size
          - cross size
    - Flex容器属性
        - flex—direction
            - 决定主轴方向，即项目排列方向
            - row（默认值）：从左往右
            - row-reverse：从右往左
            - column：从上往下
            - column-reverse：从下往上
        - flex-wrap
            - 默认情况下项目排列在一条轴线，一条轴线排不下的换行方式
            - nowrap（默认值）：不换行（列）
            - wrap：主轴横向时从上到下换行，主轴纵向时，从左到右换行
            - wrap-reverse：主轴横向时从下到上换行，主轴纵向时，从右到左换行 
        - flex-flow：flex—direction和flex-wrap的简写形式
        - justify-content
            - 定义了项目在主轴上的对齐方式
            - flex-start（默认值）：与主轴起点对齐
            - flex-end：与主轴终点对齐
            - center：与主轴的中点对齐
            - space-between：两端对齐主轴的起点与终点，项目之间间隔相等
            - space-around：每个项目两侧的间隔相等，项目之间间隔比项目与边框的间隔大一倍
        - align-items
            - 定义项目在交叉轴上如何对齐
            - flex-start（默认值）：交叉轴起点对齐
            - flex-end：交叉轴终点对齐
            - center：与交叉轴的中点对齐 
            - baseline：项目的第一行文字的基线对齐
            - stretch（默认值）：如果项目未设置高度或设为auto，项目将占满整个容器的高度
        - align-content
            - 定义了多根轴线的对齐方式，如果项目只有一根轴线，该属性不起作用
            - flex-start（默认值）：交叉轴起点对齐
            - flex-end：交叉轴终点对齐
            - center：与交叉轴的中点对齐 
            - space-between：与交叉轴两端对齐，轴线之间间隔平均分布
            - space-around：每个轴线两侧的间隔相等，轴线之间间隔比项目与边框的间隔大一倍
            - stretch（默认值）：主轴线占满整个交叉轴