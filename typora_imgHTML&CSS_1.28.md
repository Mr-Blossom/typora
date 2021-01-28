# HTML&CSS

## 	1.简单认识HTML

### 		-各种标签

### 		-其他

## 	2.CSS简介

### 		-各大选择器汇总

### 		-其他

## 	3.布局

### 		-文档流

### 		-关于盒模型的一些问题

#### 			-盒子的边框与边距

#### 			-盒子的水平布局

#### 			-盒子的垂直布局

#### 			-盒子布局产生的问题

##### 					-外边距折叠问题

#### 			-盒子的尺寸

#### 			-盒子的轮廓与圆角

### 		-其他

#### 			-行内元素的盒模型

#### 			-默认样式

## 	4.浮动

### 		-浮动简介

### 		-浮动的特点

### 		-浮动带来的问题

#### 			-高度塌陷问题

#### 			-如何解决

## 	5.定位

### 		-几大定位汇总

### 		-其他

#### 			-元素的层级

## 	6.图标字体与背景

### 		-字体

#### 			-图标字体

#### 			-阿里的图标字体

#### 			-行高设置

#### 			-简写属性

### 		-文本样式

### 		-背景

### 		-渐变

## 	7.表格

​			网页中通过table标签来创建一个表格。

### 		-表格

​			其中tr(table_row)表示表格中有几行，td表示每一行有几个单元格。rowspan 表示纵向的合并单元格，colspan 表示横向的合并单元格。

```html
<table border="1" width='50%' align="center">
        <!-- 在table中使用tr表示表格中的一行，有几个tr就有几行 -->
        <tr>
            <!-- 在tr中使用td表示一个单元格，有几个td就有几个单元格 -->
            <td>A1</td>
            <td>B1</td>
            <td>C1</td>
            <td>D1</td>
        </tr>
        <tr>
            <td>A2</td>
            <td>B2</td>
            <td>C2</td>
            <!-- rowspan 纵向的合并单元格 -->
            <td rowspan="2">D2</td>
        </tr>
        <tr>
            <td>A3</td>
            <td>B3</td>
            <td>C3</td>
        </tr>
        <tr>
            <td>A4</td>
            <td>B4</td>
            <!-- 
                colspan 横向的合并单元格
             -->
            <td colspan="2">C4</td>
        </tr>
    </table>
```

程序执行结果：

![](https://raw.githubusercontent.com/Mr-Blossom/typora/typora/typora_img%E8%A1%A8%E6%A0%BC.png)

#### 			-长表格

​                  其实就是规范了一下表格的组成部分有三块：头部thead+主体tbody+底部tfoot。

```html
<table border="1" width='50%' align="center">
        <thead>
            <tr>
               <!-- th 表示头部的单元格-->
                <th>日期</th>
                <th>收入</th>
                <th>支出</th>
                <th>合计</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>2000.1.1</td>
                <td>500</td>
                <td>200</td>
                <td>300</td>
            </tr>
            <tr>
                <td>2000.1.1</td>
                <td>500</td>
                <td>200</td>
                <td>300</td>
            </tr>
            <tr>
                <td>2000.1.1</td>
                <td>500</td>
                <td>200</td>
                <td>300</td>
            </tr>
            <tr>
                <td>2000.1.1</td>
                <td>500</td>
                <td>200</td>
                <td>300</td>
            </tr>
        </tbody>
        <tfoot>
            <tr>
                <td>合计</td>
                <td>2000</td>
                <td>800</td>
                <td>1200</td>
            </tr>
        </tfoot>

    </table>
```

程序执行结果：

![](https://raw.githubusercontent.com/Mr-Blossom/typora/typora/typora_img%E8%A1%A8%E6%A0%BC2.png)

#### 			-表格样式

​				可以利用CSS对表格样式进行调整，比如表格之间的间距以及边框的合并，比如元素在td中垂直居中/水平居中的设置，再比如某一行或奇数行背景颜色改变等等。

| 样式调整                         | 语句                                                         |
| -------------------------------- | ------------------------------------------------------------ |
| 边框之间的距离                   | border-spacing: 0px;                                         |
| 边框的合并                       | border-collapse: collapse;                                   |
| 元素垂直居中与否（默认垂直居中） | vertical-align:middle;                                       |
| 元素水平居中                     | text-align: center;                                          |
| 使表格的奇数行背景颜色改变       | tbody > tr:nth-child(odd){<br>       background-color: #bfa;<br>} |

**注意**：如果表格中没有使用tbody而是直接使用tr，那么浏览器会自动创建一个tbody，并且将tr全都放到tbody中，tr不是table的子元素。

### 		-表单

​				网页中的表单用于将本地的数据提交给远程的服务器,使用form标签来创建一个表单。

```html
 <!-- 其中：target.html中内容如下 -->
<body>
    <h1>您的数据已经收到！</h1>
</body>
```



```html
 <form action="target.html">
        <!--文本框
			注意：数据要提交到服务器中，必须要为元素指定一个name属性值
		-->
        文本框
     	<input type="text" name="username">
        <br><br>
     
        <!-- 密码框-->
        密码框
     	<input type="password" name="password">
        <br><br>

        <!--
             单选按钮
                - 像这种选择框，必须要指定一个value属性，value属性最终会作为用户的填写的值传递给服务器
                - checked 可以将单选按钮设置为默认选中
           -->
        单选按钮 
     	<input type="radio" name="hello" value="a">
        <input type="radio" name="hello" value="b" checked>
        <br><br>

        <!-- 多选框 -->
        多选框 <input type="checkbox" name="test" value="1">
        <input type="checkbox" name="test" value="2">
        <input type="checkbox" name="test" value="3" checked>

        <br><br>

        <!-- 
			下拉列表 
			selected可以将下拉按钮中的某一项设置为默认选中
		-->
        <select name="haha">
            <option value="i">选项一</option>
            <option selected value="ii">选项二</option>
            <option value="iii">选项三</option>
        </select>



        <br><br>
        <!-- 
            提交按钮
         -->
        <input type="submit" value="注册">
    </form>
```

执行本程序会出现：

![](https://raw.githubusercontent.com/Mr-Blossom/typora/typora/typora_img%E8%A1%A8%E5%8D%95.png)

点击注册按钮之后会出现：

![](https://raw.githubusercontent.com/Mr-Blossom/typora/typora/typora_img%E8%A1%A8%E5%8D%952.png)

**当然，**还有一些其他属性可以添加至按钮或者文本框之中。

```html
 <form action="target.html">
<!-- 

    autocomplete="off" 关闭自动补全
    readonly 将表单项设置为只读，数据会提交，就是value中的内容会一直显示并最终提交至服务器
    disabled 将表单项设置为禁用，数据不会提交
    autofocus 设置表单项自动获取焦点，就是刷新网页后，鼠标所在的地方
 -->
        <input type="text" name="username" value="hello" readonly>
        <br><br>
        <input type="text" name="username" autofocus>
        <br><br>
        <input type="text" name="b">

        <br><br>

   		<input type="color"> 
        <br><br>
        <input type="email"> 
        <br><br>

        <input type="submit">
        <!-- 重置按钮 -->
        <input type="reset">
        <!-- 普通的按钮 -->
        <input type="button" value="按钮">

        <br><br>
        

        <button type="submit">提交</button>
        <button type="reset">重置</button>
        <button type="button">按钮</button>
 </form>
    
```

程序执行之后：

![](https://raw.githubusercontent.com/Mr-Blossom/typora/typora/typora_img%E8%A1%A8%E5%8D%953.png)

## 	8.动画

### 		-过渡

### 		-动画

### 		-变形

### 		-z轴平移

### 		-旋转

### 		-缩放

# LESS

## 	1.less的简介

## 	2.less的语法

# 移动端

## 	1.弹性盒

### 		-弹性盒的样式

### 		-弹性元素的样式

## 	2.移动端

### 		-移动端页面

### 		-视口

### 		-vw适配

### 		-响应式布局

### 		-媒体查询

# EXERCISES