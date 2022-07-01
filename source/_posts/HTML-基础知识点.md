---
title: HTML基础知识点
categories: [前端]
comments: true
---
### HTML   盖房子

- HyperTextMarkupLanguage: 超文本标记语言

- XML：可扩展标记语言   

- HTML学习的就是有哪些标签  

```
<books>
	<book>
		<name>Java基础</name>
		<page>20</page>
	</book>
</books>
```

### 文本相关标签

- h1-h6 : 内容标题 

  特点：   独占一行 ，  字体加粗 ，  自带上下间距

- p：  段落标签

  特点： 独占一行， 自带上下间距

- br:  换行

- hr： 水平分割线

- 加粗  b      斜体  i     删除线  s    下划线 u

### 列表标签

- 无序列表： ul和li组合
- 有序列表： ol和li组合
- 列表嵌套： 有序和无序可以任意无限嵌套

###   图片标签img

- src：资源路径
  - 相对路径：访问站内资源时使用 
    - 图片和页面同级目录： 直接写图片名
    - 图片在页面的上级目录： ../图片名
    - 图片在页面的下级目录： 文件夹名/图片名 
  - 绝对路径：可以访问站外资源 图片盗链(存在找不到图片的风险) 

- alt: 图片不能正常显示时显示的文本
- title: 鼠标停在图片上时显示的文本
- width/height:  设置图片宽高,  两种赋值方式: 1. 像素  2. 百分比    如果只设置宽度,高度会等比例缩放

### 超链接a

- href: 资源路径,类似图片标签的src属性
- 页面内部跳转: 在目的地元素里面添加id属性,href="#id" 

- 图片超链接: 用a标签包裹图片即为图片超链接

### 表格标签table

- 相关标签:  table表格   tr表示行  td表示列   th表头(加粗并居中) caption表格标题
- 相关属性:   border边框        colspan跨列   rowspan跨行  

### 表单form

- 作用: 获取用户输入信息并提交给服务器 
- 学习form表单主要学习的就是form表单中有哪些控件
- 控件包括: 文本框,密码框,提交按钮, 单选,多选,下拉选,日期选择器,文件选择器等

- 各种控件:

  ```html
  <form action="http://www.baidu.com">
      <!--placeholder占位文本
      maxlength最大字符长度
      value默认值
      readonly 只读-->
  
      用户名:<input type="text" name="username"
                 placeholder="请输入用户名"
                 maxlength="5" value="xyz"
                 readonly="readonly"><br>
      密码:<input type="password" name="password"><br>
      <!--单选框 value设置提交内容 否则提交on
      checked默认选中-->
      性别: <input type="radio" name="gender" value="m"
                 id="r1"><label for="r1">男</label>
      <input type="radio" name="gender" checked value="w">女<br>
      兴趣爱好: <input type="checkbox" name="hobby" value="cy">抽烟
      <input type="checkbox" name="hobby" checked value="hj">喝酒
      <input type="checkbox" name="hobby" value="tt">烫头<br>
      生日: <input type="date" name="birthday"><br>
      靓照: <input type="file" name="pic"><br>
      所在地:
      <select name="city">
          <option value="bj">北京</option>
          <option value="sh" selected>上海</option>
          <option value="gz">广州</option>
      </select><br>
      <input type="submit" value="注册">
      <!--重置按钮-->
      <input type="reset">
      <!--自定义按钮-->
      <input type="button" value="按钮">
      <!--通过button标签实现上面的效果-->
      <button type="submit">注册</button>
      <button type="reset">重置</button>
      <button type="button">按钮</button>
  </form>
  ```

### 分区标签

- 作用: 将多个有相关性的标签添加到一个分区标签里面, 便于统一管理 

- 如何分区? 

  - 一个页面至少分为三大区, 每个大的区域里面有n个小的区域

  ```html
  <div>头</div>
  <div>体</div>
  <div>脚</div>
  ```

  

- 有哪些分区标签?

  - div:块级分区元素,  特点:独占一行  ,是使用频率最高的分区元素 

  - span: 行内分区元素, 特点: 共占一行 

  - html5版本新增的分区标签, 作用和div是一样的(独占一行)

    - header 头
    - footer 脚  
    - section区域
    - article文章/正文 
    - nav 导航
