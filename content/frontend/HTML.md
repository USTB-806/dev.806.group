---
title: "HTML"
date: 2025-11-05
draft: false
---

## HTML
- HTML标签
    - HTML（Hyper Text Markup Language）超文本标记语言
    - 标签可定义文本、图像等
    - 属性可提供更多信息
    - 双标签用于有内容的元素，但标签用于没有的
- HTML文件结构
    - ```<!DOCTYPE html>```——html文件
    - ```<html></html>```——起始点，最外层容器
    - ```<head></head>```——头部，包含原信息
        - ```<title></title>```——文档标题
        - ```<meta>```——编码格式
        - ```<link>```——外部样式表
        - ```<script></script>```——外部样式表
    - ```<body></body>```——实际显示在浏览器的内容
    - 输入!
- 标签
    - 常见文本标签 
        - 标题标签
            ```
            <h1></h1>
            <h2></h2>
            <h3></h3>
            <h4></h4>
            <h5></h5>
            <h6></h6>
            ``` 
        - 段落标签
            - ```<p></p>```
            - 字体加粗
                - ```<b></b>```(bold)
                - ```<strong></strong>```      
            - 斜体
                - ```<i></i>```  
            - 下划线
                - ```<u></u>``` 
            - 删除线
                - ```<s></s>```    
        - 列表标签
            - 无序列表
                ```
                <ul>
                    <li></li>
                    <li></li>
                    <li></li> 
                </ul>
                ``` 
            - 有序列表
                ```
                <ol>
                    <li></li>
                    <li></li>
                    <li></li> 
                </ol>
                ``` 
        - 表格标签
            ```
            <table>
                <tr>
                  <th></th>
                  <th></th>
                  <th></th>
                </tr>
                <tr>
                  <td></td>
                  <td></td>
                  <td></td>
                </tr>
                <tr>
                  <td></td>
                  <td></td>
                  <td></td>
                </tr>
                <tr>
                  <td></td>
                  <td></td>
                  <td></td>
                </tr>   
            </table>
            ```      
    - HTML标签属性
        - 基本语法
            - <开始标签 属性名=“属性值”>
            - 每个HTML元素可以具有不同的属性
            - 属性名称不区分大小写，属性值对大小写敏感 
        - 适用大多数的HTML属性
            - class属性：为HTML元素定义一个或多个类名
            - id属性：定义元素唯一的id
            - style属性：规定元素的行内样式
        - 标签与属性
            - ```<a></a>```
                - 用于创建超链接的关键元素
                - herf属性：定义链接到的目标
                - target属性：定义链接的打开方式
                    - _self：在当前窗口打开 
                    - _blank：在新的窗口或标签页打开
                    - _parent：在父窗口或父框架打开
                    - _top：在顶层窗口或顶层框架打开  
                - eg：```<a herf="https://example.com" target="_blank"></a>```
            - ```<br>```：强制文本换行
            - ```<hr>```：创建一条水平分割线
        - ```<img></img>```
            - src属性：要显示图像文件的路径或URL
            - alt属性：定义图像的替代文本 
            - width属性：宽度
            - height属性：高度
    - HTML区块
        - 块元素（bolck）
            - 通常从新行开始，占据整行的宽度，在界面上呈现为一块独立的内容块
            - 可以包含其他块级元素和行内元素
            - 常见块级元素包```<div><p><h1>——<h6><ul><ol><li><table><form>```等 
        - 行内元素（inline）
            - 通常在同一行内呈现，不会独占一行
            - 只占据其内容所需的宽度，而不是整行的宽度
            - 不能包含块级元素，但可以包含其他行内元素
            - 常见行内元素包括```<span><a><strong><em><img><br><input>```等
        - 常用标签
            - ```<span></span>```
                - 相当于没有特殊元素的<a>标签和<img>标签
                - 内联样式化文本
                - 把一小部分文本包装起来，应用样式或标记
            - ```<div></div>```
                - 没有语义，仅用于组织内容，快级标签 
                - 创建块级容器
                - 组织页面的结构和布局      
    - HTML表单
        - 常用标签
            - ```<form></form>```
                - 表单的容器
                - action属性
                    - 向哪里提交填写的数据
                    - 属性值：url 
            - ```<input>```
                - type属性：规定了input元素的类型
                    - type的属性：规定了要显示的input元素的类型
                        - text：文本
                        - radio：选择框
                        - password：密码
                        - chatbox：多选
                        - submit：把输入提交到action的url 
                - placeholder属性：文本框显示的内容（给用户提示，填写后消失）
                - value属性：规定input元素的值（自动填写）
                - name属性
                    - 实现单选框
                    - eg：```<input type="radio" name="example">```
            - ```<label></lable>``` 
                - 仅限input使用
                - 输入框前标识
                - for属性：把label标签绑定到input元素，一般与id连用