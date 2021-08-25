![image-20210825103752748](README.assets/image-20210825103752748.png)

**1. 指令的概念**

指令（Directives）是 vue 为开发者提供的模板语法，用于辅助开发者渲染页面的基本结构。

vue 中的指令按照不同的用途可以分为如下 6 大类：

① 内容渲染指令

② 属性绑定指令

③ 事件绑定指令

④ 双向绑定指令

⑤ 条件渲染指令

⑥ 列表渲染指令





**1.1 内容渲染指令**

内容渲染指令用来辅助开发者渲染 DOM 元素的文本内容。常用的内容渲染指令有如下 3 个：

- v-text : 会覆盖元素内部原有的内容！

- {{ }} : 在实际开发中用的最多，只是内容的占位符，不会覆盖原有的内容！

- v-html : 可以把带有标签的字符串，渲染成真正的 HTML 内容！



**v-text**

![image-20210825104501621](README.assets/image-20210825104501621.png)

注意：v-text 指令会覆盖元素内默认的值。



**{{ }} 语法**

vue 提供的 {{ }} 语法，专门用来解决 v-text 会覆盖默认文本内容的问题。这种 {{ }} 语法的专业名称是插值表达

式（英文名为：Mustache）。

![image-20210825105045291](README.assets/image-20210825105045291.png)

注意：相对于 v-text 指令来说，**插值表达式在开发中更常用一些！**因为它不会覆盖元素中默认的文本内容。



**v-html**

v-text 指令和插值表达式只能渲染纯文本内容。如果要把包含 HTML 标签的字符串渲染为页面的 HTML 元素，

则需要用到 v-html 这个指令：

![image-20210825105745503](README.assets/image-20210825105745503.png)



```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <div id="app">
        <p v-text = "username"></p>
        <p v-text = "gender">性别：</p>

        <hr>
        <p>{{ username }}</p>
        <p>性别：{{ gender }}</p>
        <hr>
        <p v-text = "info"></p>
        <p>{{ info }}</p>
        <p v-html = "info"></p>
    </div>

    <!-- 导入Vue的库文件 -->
    <script src="./lib/vue-2.6.12.js"></script>
    <!-- 创建Vue的实例对象 -->
    <script>
        const vm = new Vue({
            //告诉vm要控制哪个区域
            el: '#app',
            //data 要渲染的页面上的数据
            data: {
                username: 'zhangsan',
                gender: '女',
                info: '<h4 style="color:red; font-weight: bold;">欢迎来到黑马学习 vue.js</h4>'
            }
        });
    </script>
</body>
</html>
```

