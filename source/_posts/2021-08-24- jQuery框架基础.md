---
title: jQuery框架基础
categories: [前端]
comments: true
---
### jQuery框架

- 对原生JavaScript代码进行封装的框架, 作用也是给页面添加动态效果, 可以提高开发效率
- jQuery框架就是一个普通的js文件, 在html页面中引入即可 
  - 两种引入框架的方式:
    - 下载框架文件,把文件保存在工程中, 在html页面中引入本地文件   
    - 通过CDN服务器, 使用CDN服务器的好处是会根据客户端网络情况选择更合适的服务器下载框架文件, 而使用第一种的话框架文件只能从自己的服务器中获取,工作中推荐使用cdn的方式

### 通过选择器找到元素对象

- 格式:  $("选择器")
  - 新的选择器写法    
    - $("div:first")  匹配到第一个div   
    - $("div:last")      匹配到最后一个div
    - $("div:eq(n)")  匹配到第n个div     n从0开始

### 获取和修改元素的文本内容

- 格式: $("div").text("xxxx");   修改          $("div").text();  获取

### 获取和修改元素的HTML内容

- 格式: $("div").html("xxxx");   修改          $("div").html();  获取

### 获取和修改控件的value值

- 格式: $("input").val("xxx");  修改      $("input").val();  获取 

### 给元素添加事件

- 格式: $("input").click(function(){代码});    

### 创建及添加元素对象

- 创建:   

  ```
  let d = $("<div>xxx</div>");
  ```

- 添加到页面中:

  ```
  $("body").append(d);  //把元素添加到body里面
  ```

### 删除元素

- 格式:    元素对象.remove();

### 显示隐藏相关

- 隐藏:   元素对象.hide();
- 显示:  元素对象.show();
- 切换:  元素对象.toggle();

### 事件相关

- 什么是事件: 事件是系统给提供的一些特定的时间点,包括: 鼠标事件,键盘事件,状态改变事件

- 给元素添加事件的两种方式:

  - 通过事件属性添加:  

    ```html
    <input type="button" onclick="fn()"> 
    ```

  - 动态绑定事件: 在执行JavaScript或jQuery代码过程中添加事件

    ```javascript
    $("input").click(function(){})
    ```

    

- 鼠标事件:

  - onclick点击事件
  - onmouseover 鼠标移入事件
  - onmouseout 鼠标移出事件
  - onmousedown 鼠标按下事件
  - onmouseup 鼠标抬起事件
  - onmousemove 鼠标移动事件

- 键盘事件:
  - onkeydown: 键盘按下事件
  - onkeyup: 键盘抬起事件
- 状态改变事件:
  - onblur: 失去焦点事件  
  - onchange: 值改变事件   

### 动画相关

```javascript
$("input:eq(0)").click(function () {
    $("img").hide(2000);//隐藏
})
$("input:eq(1)").click(function () {
    $("img").show(2000);//显示
})
$("input:eq(2)").click(function () {
    $("img").fadeOut(2000);//淡出
})
$("input:eq(3)").click(function () {
    $("img").fadeIn(2000);//淡入
})
$("input:eq(4)").click(function () {
    $("img").slideUp(2000);//上滑
})
$("input:eq(5)").click(function () {
    $("img").slideDown(2000);//下滑
})
$("input:eq(6)").click(function () {
    $("img").animate({"left":"200px"},1000)
        .animate({"top":"200px"},1000)
        .animate({"left":"0"},1000)
        .animate({"top":"0"},1000)
        .animate({"width":"200px"},1000)
        .animate({"width":"100px"},1000);
})
```
