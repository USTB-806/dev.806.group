---
title: "前端开发"
date: 2025-11-11
draft: false
---
## Vue.js
- 声明式渲染
    - Vue是单文件组件（SFC：Single-File Component）
    - 将属于同一个组件的HTML，CSS和JavaScript封装在.vue后缀的文件中
    - Vue的核心功能是声明式渲染
        - 通过扩展于标准HTML的模板语法，可根据JavaScript的状态来描述HTML应该是什么样子的，当状态改变时,HTML会自动更新
        - 能在改变时触发更新的状态被认为是响应式的,在Vue中，响应式状态被保存在组件中
    - 语法
        - 使用data组件声明响应式状态，选项式返回对象的函数
        - 使用{{  }}来动态渲染
            - 不只限于标识符或路径，可以是任何有效的JavaScript表达式
        - ```
            export default {
                data() {
                    return {
                        message: 'Hello World!'
                        }
                }
            }
            <h1>{{ message }}</h1>
- Attribute绑定
    - mustache语法(即{{}})只能用于文本插值
    - 为了给attribute绑定一个动态值，需要使用v-bind指令
    - 指令
        - v-开头的一种特殊attribute
        - 指令的值是可以访问组件状态的JavaScript表达式
    - 语法
        - ```<div :id="dynamicId"></div>```
        - 简写：```<div :id="dynamicId"></div>```
        - ```
            <script>
            export default {
            data() {
                return {
                titleClass: 'title'
                }
            }
            }
            </script>

            <template>
            <h1 :class="titleClass">Make me red</h1>
            </template>

            <style>
            .title {
            color: red;
            }
            </style>
- 事件监听
    - 可以使用v-on指令监听DOM事件
    - 语法
        - ```<button v-on:click="increment">{{ count }}</button>```
        - 简写：```<button @click="increment">{{ count }}</button>```
        - ```
            <script>
            export default {
            data() {
                return {
                count: 0
                }
            },
            methods: {
                increment() {
                this.count++
                }
            }
            }
            </script>

            <template>
            <button @click="increment">Count is: {{ count }}</button>
            </template>
- 表单绑定
    - 可以同时使用v-bind和v-on来在表单的输入元素上创建双向绑定
    - 可以使用v-model指令简化双向绑定
    - 语法
        - ```<input :value="text" @input="onInput">```
        - ```<input v-model="text">```
        - ```
            <script>
            export default {
            data() {
                return {
                text: ''
                }
            }
            }
            </script>

            <template>
            <input v-model="text" placeholder="Type here">
            <p>{{ text }}</p>
            </template>
- 条件渲染
    - 可以使用v-if指令来有条件地渲染元素
        - 语法
            - ```<h1 v-if="awesome">Vue is awesome!</h1>```
            - 只会在awesome的值为真值 (Truthy) 时渲
            -  若awesome更改为假值 (Falsy)，它将被从DOM中移除
    - 也可以使用v-else和v-else-if来表示其他的条件分支
        - 语法
            - ```
                <h1 v-if="awesome">Vue is awesome!</h1>
                <h1 v-else>Oh no 😢</h1>
- 列表渲染
    - 可以使用v-for指令来渲染一个基于原数组的列表
        - 语法
            - ```
                <ul>
                <li v-for="todo in todos" :key="todo.id">
                    {{ todo.text }}
                </li>
                </ul>
            - todo是一个局部变量，表示当时正在迭代的数组元素，只能在v-for绑定的元素上或者其内部访问  
            - 还给每个todo设置了id，作为特殊的key属性绑定到每个<li>，key使Vue可以精准的移动到每个<li>
        - 更新列表的两种方式
            - 在源数组上调用变更方式
                - ```this.todos.push(newTodo)```
            - 使用新的数组替代原数组
                - ```this.todos = this.todos.filter(/* ... */)```
- 计算属性
    - 可以使用computed选项声明一个响应式的属性，它的值由其他属性计算而来
        - 语法
            - ```
              