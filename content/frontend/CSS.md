---
title: "CSS"
date: 2025-11-06
draft: false
---

## CSS
- CSS简介
    - CSS（Cascading Style Sheets）层叠样式表
    - 用于定义网页样式和布局的样式表语言
    - 可指定元素的颜色、字体、大小、间距等
- CSS语法
    - 由选择器、属性和属性值组成，多个规则可组合在一起
    - 选择器{
        属性1：属性值1；
        属性2：属性值2；
      }
    - 选择器声明中可以写无数条属性
    - 声明中的所有属性和值都以键值对形式出现
- CSS的三种导入方式
    - 内联样式（Inline Styles）
        - ```<h1 style="color:red;">``` 
    - 内部样式表（Internal Stylesheet）
        - ```h1{color:red;}``` 
    - 外部样式表（External Stylesheet）
        - ```<link rel="stylesheet" href="./css/style.css">``` 
    - 优先级：内联样式>内部样式表>外部样式表
    - 优先级：id>class>标签名
- 选择器
    - 元素选择器
    - 类选择器
        ``` 
        <h1 class="hightlight">example</h1>

        .highlight{
            background-color:red;
        } 
        ```
    - ID选择器
        ``` 
        <h1 id="header">example</h1>

        #header{
            background-color:red;
        } 
        ```
    - 通用选择器
        - 应用于全部元素
            ``` 
            *{
                color:red;
            } 
            ```
    - 子元素选择器
        - 仅应用于直接子元素
            ``` 
            <div class="father">
                <p class="son">example</p>
            </div>
            .father>.son{
                background-color:red;
            } 
            ```
    - 后代选择器（包含选择器）
        - 应用于所有层级的后代
            ``` 
            <div class="father">
                <p class="son">example</p>
                <div>
                    <p class="grandson">example</p>
                </div>
            </div>
            .father p{
                background-color:red;
            } 
            ```
    - 并集选择器（兄弟选择器）
        - 相邻兄弟选择器——仅作用于相邻的下一行元素
            ``` 
            <h1>example</h1>
            <p>example</p>
            <p>example</p>

            h1+p{
                background-color:red;
            } 
            ```
        - 并集选择器——仅作用于所有匹配的元素
            ``` 
            <h1>example</h1>
            <p>example</p>
            <p>example</p>

            h1,p{
                background-color:red;
            } 
            ```
    - 伪类选择器
        ``` 
        <h1 id="element">example</h1>

        #element:hover{
            background-color:red;
        } 
        ```
        - 选中子元素
            - 第一个子元素
                - ```:first-child```
            - 第n个子元素
                - ```:nth-child()```
        - 伪类状态
            - ```:hover```——鼠标悬停时
            - ```:active```——鼠标按下时
            - ```:disabled```——元素被禁用时
    - 伪元素选择器
        - 创建虚拟元素并且样式化她们
            - ```::after```
            - ```::before```
- CSS常用属性
    - 复合属性
        - font
            - ```<h1 style="font:bolder 50px "KaiTi";"</h1>
    - 文本属性
        - line-height属性：行高
        - width属性：宽度                  
        - height属性：高度
    - 块、行内、行内块元素
        - 行内块元素
            - 可设置宽度、高度等块级元素属性
            - 可包含其他行内元素或块级元素
        - 相互转换
            - display属性
                - inline：转换成行内元素
                - inline-block：转换成行内块元素
                - block：转换成块元素        
- 盒子模型
    - 属性
        - content：内容 
        - padding：内边距
        - border：边框
        - margin：外边距
- 布局
    - 标准流（普通流、文档流）
        - 网页按照元素的书写顺序依次排列
    - 浮动
        - 创建浮动框，将其移动到一边，直到左边缘或右边缘触及包含快或另一个浮动框的边缘
        - 选择器{
            float:left/right/none;
          }
        - 浮动是相对于父元素浮动，只会在父元素的内部移动 
        - 三大特性
            - 脱标：脱离标准流
            - 一行显示，顶部对齐
            - 具备行内块元素特征 
        - 清除浮动
            - overflow:hidden; 
            - 伪元素清除法    
    - 定位
        - 定位方式
            - 相对定位：相对于元素在文档流中的正常位置进行定位
            - 绝对定位：相对于其最近的一定为祖先元素进行定位不占据文档流
            - 固定定位：相对于浏览器窗口进行定位，不占据文档流，固定在屏幕上的位置，不随滚动而移动
        - 相对定位
            - 选择器{
                position:relative;
                left:100px;
                top:100px;
              }
        - 绝对定位
            - 选择器{
                position:absolute;
                left:100px;
                top:100px;
              }
        - 固定定位
            - 选择器{
                position:fixed;
                left:100px;
                top:100px;
              }
    - Flexbox
    - Grid     