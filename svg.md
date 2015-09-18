用 SVG 实现产品图片放大镜功能
==

电商网站上一个典型的功能就是产品图片的放大镜。当用户鼠标悬停在产品图片上时，能够把鼠标所在位置周边的产品图片进行放大，让用户能够看得更清楚。效果如下图所示：

![产品图片放大效果](http://ww4.sinaimg.cn/large/8063ac81gw1ew5rbniebbj20hp0b7dhq.jpg)

我花了点时间看了下京东和淘宝的产品页面，它们都有这个功能，例如：https://detail.tmall.com/item.htm?spm=a230r.1.14.3.Xpop8Z&id=41610798823 和 http://item.jd.com/1217501.html 。如果你没有印象，可以自己去网页上试一试。

这个功能是如何实现的呢？京东和淘宝都用了 JS 库和大量的 JS 代码实现这个动态的效果，从原理上说，就是在 DOM 里动态地插入一些元素（比如 `div` ），然后根据鼠标位置计算并截取图片的一部分放入动态插入的元素中。相关的部分代码见下图：

###淘宝：
![淘宝](http://ww1.sinaimg.cn/large/8063ac81gw1ew6x6h12y5j20wb0fn49a.jpg)

###京东：
![京东](http://ww2.sinaimg.cn/large/8063ac81gw1ew6x6ftx1ej20wf0f8kah.jpg)

这样的实现方法当然是直观并且有效的，但是有没有更好、更简单的方法呢？

对于这种需求，`SVG` 就大有用武之地了。有人可能会觉得奇怪：SVG 不是矢量图吗？用来制作动态图表、画一些曲线什么的挺好，可是这里是显示 JPG 图片，和 SVG 有什么关系呢？

实际上，SVG 是一种 XML 的扩展格式，它也支持很多的元素和属性。在这里，它有两个特别好的特性可以用：

1. 内嵌 JPG 图片；
2. 动态修改 `viewBox` ，显示内嵌 JPG 图片的一部分。

内嵌图片，也就是让 SVG 内部可以包含传统的图片文件，而不仅仅是矢量。这是由 SVG 自带的 `<image>` 元素来定义的，例如：
```html
<image xlink:href="http://img11.360buyimg.com/n1/jfs/t328/90/1014784552/197901/e1173be9/542d0c35N167c45c2.jpg" x="0px" y="0px" width="350px" height="350px"></image>
```
其中的 x 和 y 属性代表内嵌图片在 SVG 内的左上角坐标，width 和 height 属性则表示内嵌图片在 SVG 内占据的宽度和高度， `xlink:href` 定义了图片文件所在的 URL。

为什么要把 JPG 放在 SVG 里呢？这样不是多此一举么？这就涉及到 SVG 的 `viewBox` 属性了。

大家可以看到， SVG 的起始标签里有不少属性，比如：
```html
<svg version="1.0" id="svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" width="350px" height="350px" viewBox="132 243 120 120" xml:space="preserve">
```
其中的 `x, y, width, height` 含义和前面 `<image>` 元素的类似，表示 SVG 图片在 HTML 网页上的位置和大小。需要注意的就是 `viewBox` 属性了。它是一个字符串，里面带有四个数字，对应的还是 `x, y, width, height`，代表当前的视窗显示的部分。

也就是说，SVG 可以只是部分显示在屏幕上。它的 width 和 height 是设定好的，但是屏幕上显示的未必是整个 SVG ，而是在 `viewBox` 里定义的部分。这里的 SVG 中除了要放大的图片，没有其他矢量，所以通过 `viewBox` 就可以对图片进行放大了。

现在，老码农的思路应该就比较好理解了吧？把要放大的图片放到一个和它大小相同的 SVG 里，然后通过鼠标 `mousemove` 事件获取的坐标，把 `viewBox` 设定为向该坐标点四周延伸设定的宽度，就能在图片原始大小的范围内显示图片的一小部分，从而实现放大的效果。

此外，在 SVG 里要实现图片上的水印效果也是很容易的，利用 SVG 的 `<text>` 元素，可以把水印文字加到一个设定的位置，甚至还可以对它应用 `transform` 变换，让它倾斜指定的角度。

下面就是全部的代码了。这里我在 `<image>` 元素里用的是和 `<img>` 元素相同的一张图片，所以放大后有点模糊。反正不管是一张还是两张图，实现原理都是一样的啦。

```html
<html>
<head>
	<meta charset="utf-8">
	<title>用 SVG 实现图片放大镜的功能</title>
</head>
<body>
	<img src="http://img11.360buyimg.com/n1/jfs/t328/90/1014784552/197901/e1173be9/542d0c35N167c45c2.jpg" id="img">
	<svg version="1.0" id="svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" width="350px" height="350px" viewBox="132 243 120 120" enable-background="new 0 0 350 350" xml:space="preserve" style="visibility: hidden;">
		<image xlink:href="http://img11.360buyimg.com/n1/jfs/t328/90/1014784552/197901/e1173be9/542d0c35N167c45c2.jpg" x="0px" y="0px" width="350px" height="350px"></image>
		<text x="96" y="170" style="fill: none; stroke: lightblue; font-size: 20px; opacity: 0.6;" transform="rotate(15 96 170)">
    		@老码农的自留地
		</text>
	</svg>
	<script>
		var img = document.getElementById("img");
		var svg = document.getElementById('svg');
		svg.style.visibility = 'hidden';

		img.addEventListener('mousemove',function(evt){
			svg.style.visibility = 'visible';
			var x = evt.offsetX;
			var y = evt.offsetY;
			svg.setAttribute('viewBox',''+(x-60)+' '+(y-60)+' 120 120');
		},false);
		img.addEventListener('mouseout',function(evt){
			svg.style.visibility = 'hidden';
		},false);
	</script>
</body>
</html>
```

这种方法的几个优点是：

1. 代码量少，逻辑清晰。HTML + JS 原生代码才三十几行，不需要加载任何 JS 库，很难做到更简单了。
2. 兼容性好。主流的浏览器（包括 IE 8 以上版本）都支持 SVG。
3. 性能更好。代码量少，执行的逻辑简单，无需进行 DOM 元素的动态增减，也无需反复读取图片文件，响应的速度会更快。

【注】演示地址是： http://coderlmn.github.io/frontEndCourse/zoom.html 