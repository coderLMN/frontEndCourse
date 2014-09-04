开课前小测试
==

下面有几个小题目，用来测试一下你当前的水平，都是针对HTML、CSS、Javascript的基本概念，没有偏题难题，全部代码可以写在一个HTML文件里，每题都不会超过50行。记不住的属性可以自己去查。


1. 图片位置
--

下面的HTML页面里有三张图片：

```html
<!DOCTYPE html>
<html>
	<body>
			<img src="http://www.w3schools.com/images/w3html.gif">
			<img src="http://www.w3schools.com/images/w3css.gif">
			<img src="http://www.w3schools.com/images/w3javascript.gif">
	</body>
</html>
```

如何让这三张图片依次居左、居中、居右对齐？


2. 表格样式
--

做一个4行x3列的表格，宽度300px，行与行之间的底部画线，列之间不用画，最下面一行底部也不需要线。也就是说，4行中间用3条线隔开。不过不要硬写，行数是可变的哦。


3. 图片移动
--

用第一题做好的页面，每次点击任意一张图片，最左边的图片移到最右边，中间的移到左边，右边的移到中间。如果把页面看成一个平放的圆盘，就是说点击后圆盘顺时针移动一格。


再来一个选做题
--
这个题难度比较大，现在做不出来也没关系，但是等上完课之后应该能轻松搞定。

给定一个HTML页面：

```html
<!DOCTYPE html>
<html>
	<body>
		<div style="text-align: center;">
			selected items:<input type='text' size="200" id='myOptions'><br>
			<input type="radio" name="root" value="root">root
		</div>
	</body>
</html>
```

要求实现类似于资源管理器的功能，双击可以添加一个下级单选，从而实现多级联动的单选功能。例如：

```html
图书    -小说     -科幻小说
                 -言情小说
                 -战争小说
        -教材     -计算机教材    -数据结构    -算法设计手册
                                -编译原理
                 -英语教材
        -儿童读物
```

给定的HTML页面可以任意修改，增减元素、样式和JS代码。       
