---
title: JavaScript(简称JS)基础知识点
categories: [前端]
comments: true
---
**JavaScript(简称JS)**

作用：给页面添加动态效果

特点：

- 属于脚本语言，不需要编译直接解析执行
- 属于弱类型语言,  声明变量时不需要指定类型
- 安全性高, JavaScript语言只能访问浏览器内部数据,浏览器以外磁盘上的数据禁止访问
- 交互性高, 因为JavaScript语言是嵌入到html页面中,最终执行在客户端浏览器中,是可以直接和用户进行交互的,而Java语言是需要通过网络传输后才能进行交互的语言



onclick：点击事件属性

alert：弹出警告框

**引入JavaScript代码方式**:

内联：在标签的事件属性中添加JavaScript代码, 当事件触发时执行.

​		事件: 是系统给提供的一些特定时间点.  

​		点击事件: 当用户点击了某个元素的时候会调用某些代码, 这个点击时间点触发代码的行为 称为点击事件.

内部：在html页面中任意位置添加 script标签 在标签体内添加js代码

外部：在单独的js文件中写JavaScript代码, 在html页面中 通过script标签的src属性引入到页面中

``

```javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<!--alert方法是弹出框
onclick点击事件属性-->
<input type="button" value="按钮" onclick="alert('内联引入成功！')">
<script>
    alert("内部引入成功！")
</script>
<!--引入外部js文件-->
<script src="my.js"></script>
</body>
</html>
```

**注释：**

HTML：	<!--注释内容-->

CSS: 	`/*注释内容*/`

JavaScript:	//单行注释	`/*多行注释*/`

**变量**

let和var的区别

```javascript
for(let i=0;i<10;i++){
   let y = i+1;
}
let z = i-1;  //因为是脚本语言编写过程中不会报错但是运行时i的值得不到,使用let声明变量的作用域和Java中一样
for(var i=0;i<10;i++){
   var y = i+1;
}
var z = i-1;  //使用var声明变量, 不管在什么位置声明的都是一个全局变量   
```

**数据类型**

JavaScript中只有对象类型

常见的几种对象类型：

​	string：字符串，可以引用单引号或双引号修饰"abc" = 'abc'

​	number：数值，相当于Java中所有数值类型的总和

​	boolean：true和false

​	undefined：未定义，当变量只声明不赋值时，变量的类型为undefined

​	typeof(变量)：获取变量的类型

**运算符**

- 算数运算符：+ - * / %	除法运算会自动根据结果转成整数或小数
- 关系运算符：> < >= <= !=  ==和===
- ​	==：先统一两个变量的类型再比较值	"666"==666  true
- ​	===：先比较类型，类型相等后再比较值	"666"===666  false
- 赋值运算符：=  +=  -=  *=  /=  %=  ++  --
- 逻辑运算符：&&   ||   !
- 三木运算符：条件？值1:值2

**语句**

- if else
- for
- while
- do while
- swich case

**方法相关**

方法声明

​	Java：public返回值类型 方法名(参数列表){方法体}

​	JavaScript：function方法名(参数列表){方法体}

常见的四种方法：

- 无参无返回值

  - 无参有返回值
  - 有参无返回值
  - 有参有返回值

声明方法的三种方式：

 -  function 方法名(参数列表){方法体}  
  - let 方法名 = function(参数列表){方法体} 
  - let 方法名 = new Function("参数1","参数2","方法体"); 

**和页面相关的方法**

1. 通过选择器获取页面中的元素对象  

   let d = document.querySelector("选择器");

2. 获取和修改元素的文本内容

   d.innerText = "xxx";   修改

   d.innerText     获取 

3. 获取和修改控件input的值  

   控件对象.value="xxx";   修改 

   控件对象.value;      获取

4. 获取和修改元素的html内容

   元素对象.innerHTML;   获取

   元素对象.innerHTML="xxx";  修改

   元素对象.innerHTML+="xxx";  追加 

**NaN**

- Not a Number: 不是一个数   
- isNaN(变量)       true代表是NaN(不是数)     false代表不是NaN(是数)

**自定义对象**

先定义好一个对象,然后实例化

```javascript
//定义一个空的对象(无属性 无方法) 类似Java中创建一个Person.java里面什么都不写
let Person = function () {}
//实例化对象
let p1 = new Person();
//动态给实例化的对象添加属性和方法(Java是不支持的)
p1.name="张三";
p1.run = function () {
    alert(this.name);
}
```

直接实例化对象

```javascript
let p2 = {
    name:"李四",
    age:18,
    run:function () {
        alert("name:"+this.name+" 年龄:"+this.age);
    }
}
//p2.run();

//创建了一个数组里面装着3个对象
    let arr = [{name:"刘备",type:"战士"},
        {name:"黄忠",type:"射手"},{name:"张飞",type:"战士"}];
    //遍历数组
    for (let i = 0; i < arr.length; i++) {
        //取出数组中的对象
        let hero = arr[i];
        console.log("名字:"+hero.name);
        console.log("类型:"+hero.type);
    }
```

----------------------

### 对象分类

- 内置对象: 包含 string number boolean等 
- BOM: 浏览器对象模型, 包含和浏览器相关的内容
- DOM:文档对象模型, 包含和页面相关内容

### BOM浏览器对象模型

- window: 该对象中的属性和方法称为全局属性和全局方法, 访问时可以省略掉window. 
- window对象中的常见方法:
  - alert("xxx"); 弹出提示框
  - confirm("xxx"); 弹出确认框
  - prompt("xxx"); 弹出文本框
  - parseInt()/parseFloat() 字符串转成整数或小数
  - isNaN(变量) 判断变量是否是NaN 
  - let timer = setInterval(方法,时间间隔) 开启定时器 
  - clearInterval(timer); 停止定时器
  - setTimeout(方法,时间间隔); 只执行一次定时器
- window对象中的常见属性
  - location: 位置
    - location.href 获取或修改浏览器的请求地址 
    - location.reload() 页面刷新
    - location.search 获取地址栏中的参数
  - history: 历史 (当前选项卡历史)
    - history.length 历史页面数量
    - history.back() 返回上一页面
    - history.forward() 前往下一页面

### DOM文档对象模型

- 包含和页面相关内容 
- document.querySelector("选择器");
- innerHTML/ innerText / value 


