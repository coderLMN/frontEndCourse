前言
==

我曾经在伯乐在线的社区看到过这样一个问题：《面对技术海洋，如何选择一个属于自己的技术方向？》，楼主是这样说的：

```
“相信很多工作一两年的人都有一个困惑，自己写了不长时间的代码做了一些东西但是都不精通，面对各种层出不穷的
技术方向不知道如何选择。我就是其中的一员困惑者。希望发起一场讨论看看大家的看法和意见以抛砖引玉。”
```

这个问题也引发了我自己的一些思考，然后我提出了自己对这个问题的看法：

```
“我的观点有可能是片面的，但我还是想说在工作过程中最重要的不是去精通某个技术方向，而是不断提高自己快速学
习的能力。

一，技术方向本身就是不断变化的。你可能刚刚精通了Struts，可是Struts 2、Spring、Grails又出来了；刚掌
握了jQuery的精髓，却发现有了HTML5和CSS3，大部分情况下用它多余；刚弄明白线程池等概念，突然流行起单线程
框架；刚把MySQL学会，MongoDB又火了。基本上大部分技术方向上每年都会出不少新东西，想精通一项技术，然后一
招鲜吃遍天，恐怕不太现实。

二，技术方向的演变方向不容易预见。兄弟我就遇到过这个困惑。想当年在IBM主机开发领域（AS/400, ES/9000）
兄弟我在国内也算是一把好手，可是离开原来单位出来居然找不到工作，因为除了那几个IBM大客户，谁知道RPG、
COBOL是什么东西啊？只好重头开始学Java，才混了口饭吃。现在包括微软的那些开发平台，也逐渐衰落了。所以光
是精通一门，也许过几年就落伍了。

三，技术方向的选择是个普遍性难题。其实不光是楼主在这方面有困惑，恐怕楼主的老板们更会有，比如NoSQL、
大数据、云计算这么流行，搞不搞？不搞会不会落后？投资人会不会觉得我们吃老本不思进取？要是搞，咋搞？
招牛人还是自己培养几个？一年投入多少钱？万一搞不出名堂怎么善后？就是Steve Jobs当年不也在HTML5 和
 Flash 之间斗争么。他们为此都得琢磨个三五年，你看不清方向也是正常的。

四，“精通”是关于对一门技术理解的深度，而“技术方向”是对于整个技术理解的广度。没有深度作为基础，所谓
的广度也是虚的。有不少人喜欢夸夸而谈，什么Map Reduce啦，什么Hadoop啦，什么机器学习啦，未来私有云
和公有云融合的发展方向啦，说起来头头是道，似乎一下子就能做个顶层架构，但是让他写个二叉树遍历都写不出
来，这就是too young, too simple，和街头小混混讨论如何收复钓鱼岛差不多意思。

Talk is cheap。你懂的。

所以，楼主提到“很多工作一两年的人都有一个困惑，自己写了不长时间的代码做了一些东西但是都不精通”，这是
很正常的。既然只是“写了不长时间的代码”，“都不精通”基本是必然的，除非你是天才。想精通就多花时间进去，
多写代码，多查资料，多思考，先精通一门再说。在此基础上，业余时间多关心行业内的技术动态，了解一些新的
技术，慢慢积累，这有助于你看清大的趋势。

总之我的看法是，先不要急着爬到很高想看清楚方向，不管你手头用的是什么技术，先踏踏实实地精通它。在这个
过程中，不断提高自主学习的能力。这样即使看不清方向，万一方向变的时候，你总是第一个适应的，那也很不错。”
```

我本人其实一向都是靠自学的，很少参加技术培训。现在互联网上的资源太丰富了，你只需要一台电脑和网络就可以学习任何技术。我学一种新技术一般只需要有官方文档、源码和stackoverflow就够了，关键是自己勤动手、花时间。我也从来没有跟着在线视频学过东西，因为那样不如自己照着文档动手来得快。我之所以把下面自己有关前端技术的一些思考放在github上分享，也是希望能抛砖引玉，吸引喜欢自学的同学来一起讨论。

每次我学会一些新东西，我总是会很兴奋地告诉周围的同事，推荐他们也去学。他们看我的演示觉得很棒，但是很少有人会真的去学。很多码农同事都有一种惰性，他们习惯了躲在自己熟悉的世界里，照着老板的要求按部就班地写着代码，等待着中文版的《21天精通Node.js》之类的书出来。怎么说呢，确实平时的工作压力已经很大了，我们码农都是no money, no life，再花时间学习新技术有时候过于奢侈，这也是可以理解的。但是我觉得，既然选择了码农这样一个苦逼的职业，就只能活到老学到老。

像HTML5, CSS3, SVG这些新的技术，还有AngularJS，Node.js这些新框架，NoSQL数据库等等，出来得都很快，可如果要等别人掌握了再写出中文版的教程，可能两三年时间都过去了。我自己则更喜欢自己通过看文档、找例子、SO问答的渠道自学，这样能比别人快很多，也希望把自学的一些经验和大家分享。下面就是我自己的一些总结，还不成熟，谬误之处请多多指点，谢谢！


一、前端开发自学基础
==


英语读写
--

### 需要达到的水平：

1. 能充分理解技术文档的内容，这是自主学习的重要基础。

2. 能用英语准确表达技术相关的问题，写出清晰的注释。

### 方法：

1. 大量阅读，在阅读过程中熟悉单词，熟悉语法结构。

2. 多模仿读到的好句子，用它们写文档和注释。

### 难点： 

技术文档中有很多长句子，带有多层嵌套的从句，初学者不容易准确理解句子的意思。遇到这种句子，先搞清楚断句，也就是判断每个从句修饰的主体是哪个，然后再组合起来理解。

参考文章：《老码农教你学英语》http://blog.jobbole.com/45296/

### 学习资源： 

https://tools.ietf.org/html/rfc2616  (HTTP协议描述，比较枯燥，但是非常重要，这是web开发的理论基础。不过，马上HTTP/2的RFC要出来了，看新版本的更好。)




StackOverflow
--

### 需要达到的水平：

1. 知道怎么搜索与自己遇到的bug相关的问题。

2. 能够在stackoverflow上顺利地提出问题、尝试答案、选出正确答案。

3. 尝试在SO上回答问题，帮助其他人。

### 方法： 

注册账号，每天使用，编程中遇到问题自己花时间找答案，多尝试多模仿。

### 难点： 

提高英语水平和debug经验。

### 学习资源： 

http://stackoverflow.com/tour




GitHub
--

### 需要达到的水平：

1. 能够在 GitHub 上建立自己的开源项目并管理它。

2. 会给项目建立 GitHub pages用于演示。

3. 会使用git命令行工具进行代码的版本控制。

4. 尝试利用 GitHub 进行多人协作。

### 方法： 

注册账号，每天使用，不会的操作自己查SO寻找答案。

### 难点： 

熟悉git操作。也可以安装一个 GitHub 客户端用来进行可视化的版本控制。

### 学习资源：

https://help.github.com




编码规范
--

### 需要达到的水平： 

1. 理解代码可读性的概念。

2. 遵守代码结构、函数与变量命名、注释等规范。

3. 培养优化代码逻辑的意识

### 方法： 

找一些经典开源项目，作为学习和模仿的对象，平时对自己严格要求

### 学习资源： 

前端代码规范： https://coderlmn.github.io/code-standards/

前端开发指南： https://coderlmn.github.io/Front-End-Development-Guidelines/


二、热身小测试
==

下面有几个小题目，用来测试一下你当前的水平，都是针对HTML、CSS、Javascript的基本概念，没有偏题难题，全部代码可以写在一个HTML文件里，每题都不会超过50行。记不住的属性可以自己去查。


### 1. 图片位置

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


### 2. 表格样式

做一个4行x3列的表格，宽度300px，行与行之间的底部画线，列之间不用画，最下面一行底部也不需要线。也就是说，4行中间用3条线隔开。不过不要硬写，行数是可变的哦。


### 3. 图片移动

用第一题做好的页面，每次点击任意一张图片，最左边的图片移到最右边，中间的移到左边，右边的移到中间。如果把页面看成一个平放的圆盘，就是说点击后圆盘顺时针移动一格。


### 4. 再来一个选做题

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


三、我自己做的参考答案
==
### 1. 三张图片居左、居中、居右

```html
<!DOCTYPE html>
<html>
	<head>
		<style>
			.center{
			 	text-align: center;
			}
			.left{
				float: left;
			}
			.right{
				float:right;
			}
		</style>
	</head>
	<body>
		<div class="center">
			<img src="http://www.w3schools.com/images/w3html.gif" class="left">
			<img src="http://www.w3schools.com/images/w3css.gif">
			<img src="http://www.w3schools.com/images/w3javascript.gif" class="right">
		</div>
	</body>
</html>
```


### 2. 4行x3列的表格

```html
<!DOCTYPE html>
<html>
	<head>
		<style>
			table {
				 width:300px;
			}
			table,tr {
				border-bottom:1px solid black;
				border-collapse:collapse;
			}
			table,tr:last-child {
				border-bottom: none;
			}
		</style>
	</head>
	<body>
		<table>
			<tr>
  				<td>Jill</td>
  				<td>Smith</td>		
  				<td>50</td>
			</tr>
			<tr>
  				<td>Eve</td>
  				<td>Jackson</td>		
  				<td>94</td>
			</tr>
			<tr>
  				<td>John</td>
  				<td>Doe</td>		
  				<td>80</td>
			</tr>
			<tr>
  				<td>Monica</td>
  				<td>Jones</td>		
  				<td>20</td>
			</tr>
		</table>
	</body>
</html>
```


### 3. 图片被点击后，顺序顺时针移动

```html
<!DOCTYPE html>
<html>
	<head>
		<style>
			.center{
			 	text-align: center;
			}
			.left{
				float: left;
			}
			.right{
				float:right;
			}
		</style>
		<script>
			function rotate() {
				document.getElementsByClassName('left')[0].className='change-later';
    			document.getElementsByClassName('none')[0].className='left';
				document.getElementsByClassName('right')[0].className='none';
    			document.getElementsByClassName('change-later')[0].className='right';
			}
		</script>
	</head>
	<body>
		<div class="center">
			<img src="http://www.w3schools.com/images/w3html.gif" class="left" onclick="rotate()">
			<img src="http://www.w3schools.com/images/w3css.gif" class="none" onclick="rotate()">
			<img src="http://www.w3schools.com/images/w3javascript.gif" class="right" onclick="rotate()">
		</div>
	</body>
</html>
```


### 4. 可定制多级联动单选

```html
<!DOCTYPE html>
<html>
	<head>
		<style>
			li {
				display: block;
			}
			i.insert{
				border: 1px solid lightgray;
				border-radius: 4px;
				color: lightgray;
				cursor: pointer;
			}
		</style>
	</head>
	<body>
		<div>
			<!-- This is the input which record all the checked items, could be hidden in a form -->
        	<br><b>selected items: </b><input type='text' size='100' id='myOptions'><br>
        	<ul>
        		<li id="1">
        			<input type="radio" name="top" value="root" checked="1" onchange="refresh()"><b> root </b>
        			<i class="insert" onclick="insertChild('1')"> + </i>    <!-- root -->
        		</li>
        	</ul>
		</div>
		
		<script>			
			function refresh() {
    			var stack = new Array();            // stack used for traversing the tree nodes
    			var result = document.getElementById('myOptions');
    			result.value = '';                  // clear the result text field
        		stack.push('1');       				// push the top level radio into the stack
    			var first = true;

    			while(stack.length > 0){             // go through each node with a depth-first approach
        			var currentId = stack.pop();
        			var currentNode = document.getElementById(currentId).childNodes[0];
        			var subList = document.getElementsByName(currentId);    // all the child nodes of current node
    
        			for (var j=subList.length-1; j>=0; j--){
            			if(currentNode.checked == false) {
                			subList[j].checked = false;     // if parent node is not checked, children are not either
                			subList[j].disabled = true;     // if parent node is not checked, children can not be checked
            			}
            			else{
                			subList[j].disabled = false;    // if parent node is checked, children are enabled for selecting
            			}
            			stack.push(subList[j].parentNode.id);      // push all the children into stack
        			}
        			if(currentNode.checked == true) {
            			if(! first) {
                			result.value += ',';        // if some node has already been checked, separate following nodes with ','
            			}
            			else{
                			first = false;              // find first checked node, next time need a ',' to separate nodes
            			}
            			result.value += currentNode.nextSibling.innerHTML; // record the id of this checked node in the result text field
        			}
    			}
			}
			
			function insertChild(id){					// insert a option to the radio group whose name is current id
				var parent = document.getElementById(id);
				var children = document.getElementsByName(id);
				var seq = id +''+ (children.length+1);
				if(children.length<9){					// only 9 options allowed for each group
					var name = prompt("Name of the new option :", "");		// user input option name
					var radioHtml = "<li id='" + seq + "'><input type='radio' name='" + id + "' value='"+name+"' onchange='refresh()'><b> "+name+" </b><i class='insert' onclick='insertChild(" + seq+")'> + </i></li>";
					if(children.length === 0) {
						var ul = document.createElement('ul');				// no child yet, insert ul first
						parent.appendChild(ul);
						ul.innerHTML = radioHtml;							// insert as the first child
					}
					else {
						children[0].parentNode.parentNode.innerHTML += radioHtml;	// insert as the last child
					}	
				}
				else {
					alert('can not insert more than 9 items to each radio group.');
				}
			}
		</script>
	</body>
</html>
```

四、总体架构的思考
==

近几年因为HTML5，CSS3的出现并逐渐占据主流位置，web前端开发的整体格局已经有了一个巨大的变化。比如说原先要通过jQuery渲染的一些动画效果，现在用CSS3 animation就轻松搞定了，Drag & Drop这类功能也成为了HTML5的标配。

我觉得总体趋势是JS的角色要往后退，主要承担前端逻辑控制和与后端交互的作用，CSS成为前端渲染效果的核心。最近出现的一些前端MVC框架，比如AngularJS，就已经体现了这一趋势。


### 前端渲染效果

下面拿jQuery UI的Tabs作为一个例子。它提供了一个mouseover自动切换Tab内容的演示，地址是：http://jqueryui.com/tabs/#mouseover

源码如下：
```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>jQuery UI Tabs - Open on mouseover</title>
  <link rel="stylesheet" href="//code.jquery.com/ui/1.11.1/themes/smoothness/jquery-ui.css">
  <script src="//code.jquery.com/jquery-1.10.2.js"></script>
  <script src="//code.jquery.com/ui/1.11.1/jquery-ui.js"></script>
  <link rel="stylesheet" href="/resources/demos/style.css">
  <script>
  $(function() {
    $( "#tabs" ).tabs({
      event: "mouseover"
    });
  });
  </script>
</head>
<body>
 
  <div id="tabs">
    <ul>
      <li><a href="#tabs-1">Nunc tincidunt</a></li>
      <li><a href="#tabs-2">Proin dolor</a></li>
      <li><a href="#tabs-3">Aenean lacinia</a></li>
    </ul>
    <div id="tabs-1">
      <p>Proin elit arcu, rutrum commodo, vehicula tempus, commodo a, risus. Curabitur nec arcu. Donec sollicitudin mi sit amet mauris. Nam elementum quam ullamcorper ante. Etiam aliquet massa et lorem. Mauris dapibus lacus auctor risus. Aenean tempor ullamcorper leo. Vivamus sed magna quis ligula eleifend adipiscing. Duis orci. Aliquam sodales tortor vitae ipsum. Aliquam nulla. Duis aliquam molestie erat. Ut et mauris vel pede varius sollicitudin. Sed ut dolor nec orci tincidunt interdum. Phasellus ipsum. Nunc tristique tempus lectus.</p>
    </div>
    <div id="tabs-2">
      <p>Morbi tincidunt, dui sit amet facilisis feugiat, odio metus gravida ante, ut pharetra massa metus id nunc. Duis scelerisque molestie turpis. Sed fringilla, massa eget luctus malesuada, metus eros molestie lectus, ut tempus eros massa ut dolor. Aenean aliquet fringilla sem. Suspendisse sed ligula in ligula suscipit aliquam. Praesent in eros vestibulum mi adipiscing adipiscing. Morbi facilisis. Curabitur ornare consequat nunc. Aenean vel metus. Ut posuere viverra nulla. Aliquam erat volutpat. Pellentesque convallis. Maecenas feugiat, tellus pellentesque pretium posuere, felis lorem euismod felis, eu ornare leo nisi vel felis. Mauris consectetur tortor et purus.</p>
    </div>
    <div id="tabs-3">
      <p>Mauris eleifend est et turpis. Duis id erat. Suspendisse potenti. Aliquam vulputate, pede vel vehicula accumsan, mi neque rutrum erat, eu congue orci lorem eget lorem. Vestibulum non ante. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Fusce sodales. Quisque eu urna vel enim commodo pellentesque. Praesent eu risus hendrerit ligula tempus pretium. Curabitur lorem enim, pretium nec, feugiat nec, luctus a, lacus.</p>
      <p>Duis cursus. Maecenas ligula eros, blandit nec, pharetra at, semper at, magna. Nullam ac lacus. Nulla facilisi. Praesent viverra justo vitae neque. Praesent blandit adipiscing velit. Suspendisse potenti. Donec mattis, pede vel pharetra blandit, magna ligula faucibus eros, id euismod lacus dolor eget odio. Nam scelerisque. Donec non libero sed nulla mattis commodo. Ut sagittis. Donec nisi lectus, feugiat porttitor, tempor ac, tempor vitae, pede. Aenean vehicula velit eu tellus interdum rutrum. Maecenas commodo. Pellentesque nec elit. Fusce in lacus. Vivamus a libero vitae lectus hendrerit hendrerit.</p>
    </div>
  </div>
</body>
</html>
```

可以看到这个效果需要jQuery和jQuery UI的JS库，jQuery UI的CSS，还另外加载了一个演示用的style.css。其实，只需要用CSS加上两句原生JS就很容易实现这个效果。（其实我一直想怎么不用JS实现这个效果，还没想出可行的办法，先将就一下好了。）


下面是我的实现方法：

```html
<!DOCTYPE html>
<html>
	<head>
		<style>
			div.menu {
				border: 1px solid gray;
				border-top: 1px solid transparent;
				width: 600px;
				min-height: 400px;
				margin-top: -1px;
				padding: 0 19px 0 19px;
			}
			div.menu > p {
				display: none;
			}
			ul {
				width: 600px;
				border: none;
				border-radius: 8px 8px 0 0;
				padding-top: 10px;
				margin-bottom: 0;
				background: linear-gradient(black, gray) no-repeat;
			}
			li {
				display: inline-block;
				border: 1px solid gray;
				border-radius: 5px 5px 0 0;
				background-color: darkgray;
				color: white;
				padding: 2px 5px 0 5px;
			}
			li:hover{
				border-bottom: 1px solid white;
				background-color: white;
				color: black;
			}
		</style>
	</head>
	<body>
  		<ul>
    		<li onmouseover="show('p1')" onmouseout="hide('p1')">Nunc tincidunt</li>
			  <li onmouseover="show('p2')" onmouseout="hide('p2')">Proin dolor</li>
    		<li onmouseover="show('p3')" onmouseout="hide('p3')">Aenean lacinia</li>
  		</ul>	
  		<div class="menu">
   			<p id="p1">Proin elit arcu, rutrum commodo, vehicula tempus, commodo a, risus. Curabitur nec arcu. Donec sollicitudin mi sit amet mauris. Nam elementum quam ullamcorper ante. Etiam aliquet massa et lorem. Mauris dapibus lacus auctor risus. Aenean tempor ullamcorper leo. Vivamus sed magna quis ligula eleifend adipiscing. Duis orci. Aliquam sodales tortor vitae ipsum. Aliquam nulla. Duis aliquam molestie erat. Ut et mauris vel pede varius sollicitudin. Sed ut dolor nec orci tincidunt interdum. Phasellus ipsum. Nunc tristique tempus lectus.</p>
    		<p id="p2">Morbi tincidunt, dui sit amet facilisis feugiat, odio metus gravida ante, ut pharetra massa metus id nunc. Duis scelerisque molestie turpis. Sed fringilla, massa eget luctus malesuada, metus eros molestie lectus, ut tempus eros massa ut dolor. Aenean aliquet fringilla sem. Suspendisse sed ligula in ligula suscipit aliquam. Praesent in eros vestibulum mi adipiscing adipiscing. Morbi facilisis. Curabitur ornare consequat nunc. Aenean vel metus. Ut posuere viverra nulla. Aliquam erat volutpat. Pellentesque convallis. Maecenas feugiat, tellus pellentesque pretium posuere, felis lorem euismod felis, eu ornare leo nisi vel felis. Mauris consectetur tortor et purus.</p>
    		<p id="p3">Mauris eleifend est et turpis. Duis id erat. Suspendisse potenti. Aliquam vulputate, pede vel vehicula accumsan, mi neque rutrum erat, eu congue orci lorem eget lorem. Vestibulum non ante. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Fusce sodales. Quisque eu urna vel enim commodo pellentesque. Praesent eu risus hendrerit ligula tempus pretium. Curabitur lorem enim, pretium nec, feugiat nec, luctus a, lacus.
    			<br><br>Duis cursus. Maecenas ligula eros, blandit nec, pharetra at, semper at, magna. Nullam ac lacus. Nulla facilisi. Praesent viverra justo vitae neque. Praesent blandit adipiscing velit. Suspendisse potenti. Donec mattis, pede vel pharetra blandit, magna ligula faucibus eros, id euismod lacus dolor eget odio. Nam scelerisque. Donec non libero sed nulla mattis commodo. Ut sagittis. Donec nisi lectus, feugiat porttitor, tempor ac, tempor vitae, pede. Aenean vehicula velit eu tellus interdum rutrum. Maecenas commodo. Pellentesque nec elit. Fusce in lacus. Vivamus a libero vitae lectus hendrerit hendrerit.<br>
    		</p>
  		</div>
		
		<script>			
			function show(id){
				document.getElementById(id).style.display = 'block';
			}
			function hide(id){
				document.getElementById(id).style.display = 'none';
			}
		</script>
	</body>
</html>
```

其实这里都没有用到CSS3和HTML5。类似的，jQuery UI里边好多效果都可以用更简单的方法实现。另外的一些对应关系例子如下：
```
Accordian  -- HTML5 details + CSS
Droppable、Draggable --  HTML5 Drag and Drop
Datepicker  --  HTML5 <input type="date" name="bday">
Menu  --  HTML5 nav + CSS
Progressbar  --  HTML5 meter, progress 
Selectmenu  --  HTML5 datalist + CSS
Effects / jQuery .animate  --  CSS3 animate
```

感兴趣的同学可以自己在里边找一个例子实现一下。


### 前端逻辑控制

现在前端交互方式的趋势是局部刷新，单页面应用逐渐会成为web开发的主流方式。在这种情况下，前端的控制逻辑变得越来越复杂，JS的作用在这个领域就变得非常关键了。前面提到，由于HTML5和CSS3提供了非常强大的前端渲染功能，所以从架构的角度来说，能通过HTML和CSS解决的问题就不必惊动JS他老人家了，他有更重要的工作要做。

例如AngularJS在前端逻辑控制中提供了一套Route机制，根据url的变化动态加载相应的控制逻辑和html片段，如果去查看它的源代码里的browser.js，就可以发现这套机制的核心是针对hashchange和popstate事件来进行处理的（这样也就理解了为什么在html5Mode == false的时候，angurlajs应用所有的url前面都会带一个'/#'了)。那么，利用原生JS也可以实现类似的功能。


下面的例子构造了三个链接，点击后分别加载不同的html片段放入div#demo中。演示链接：https://coderlmn.github.io/frontEndCourse/ctrlDemo.html

```html
<!DOCTYPE html>
<html>
	<body onhashchange="changeUrl()">
		<a href="#home">home</a>
		<a href="#one">one</a>
		<a href="#two">two</a>
		
		<div id="demo" style="border: 1px solid gray; min-height: 100px; min-width: 400px;"></div>

		<script>
		// Using the location.hash property to request html partial
			function changeUrl() {
			    document.getElementById("demo").innerHTML = loadPage(location.hash.replace('#','') + '.html');
			}

			function loadPage(href) {
		        var xmlhttp = new XMLHttpRequest();
    			xmlhttp.open("GET", href, false);
		        xmlhttp.send();
        		return xmlhttp.responseText;
    		}
		</script>
	</body>
</html>
```



### 前后端交互

JS还有一项重要职能，就是负责与后端服务器的交互。具体说就是解析前端url然后向后端发送Ajax请求，后端返回响应后再解析返回的数据并更新DOM相应的元素。大部分JS库都提供了Ajax访问的方法，但是我们也可以直接利用XMLHttpRequest来获取后端的资源。下面就是一个获取github上emoji表情图片集合的例子。


```html
<!DOCTYPE html>
<html>
    <body onhashchange="changeUrl()">
        <a href="#home">home</a>
        <a href="#one">one</a>
        <a href="#two">two</a>
        <a href="#emojis" id="temp">github emojis</a>
        <div id="demo" style="border: 1px solid gray; min-height: 100px; min-width: 400px; display:none;"></div>

        <script>
            var divDemo = document.getElementById("demo");
            function changeUrl() {
                var url = location.hash.replace('#','');
                if(url == 'emojis'){
                    remoteApi('https://api.github.com/emojis');
                }
                else{
                    localPartial(url + '.html');
                }
            }

            function remoteApi(url) {
                var apiMap = JSON.parse(loadPage(url));
                var inner = '';
                for(var key in apiMap) {
                    inner += "<figure style='display: inline-block;'><img src='" + apiMap[key] + "' width='100' height='100'><figcaption>" + key + "</figcaption></figure>";
                }
                divDemo.innerHTML =  inner;
                divDemo.style.display = 'block';
            }
			
            function localPartial(partial) {
                divDemo.innerHTML = loadPage(partial);
                divDemo.style.display = 'block';
            }
			
            function loadPage(href) {
                var xmlhttp = new XMLHttpRequest();
                xmlhttp.open("GET", href, false);
                xmlhttp.send();
                return xmlhttp.responseText;
            }
        </script>
    </body>
</html>
```

这里图片的显示用到了HTML5的figure和figcaption标签，它可以把图片和标注放在一起，当然咱们也可以进一步用CSS对它进行美化。


五、有关前端核心技术的思考:
==

与后端开发的MVC模式类似，前端开发也需要合理划分内容、样式和控制，这分别是HTML、CSS和JS的任务。


### HTML5

HTML5提供了很多革命性的特性，除了Drag & Drop、Video、SVG等新的标签丰富了前端元素之外，还有一系列新的event，以及local storage，Speech Synthesis、app Cache等超级强大的基础功能，让开发者能够控制更多的本地资源，做出原来只有本地应用才能实现的功能。

这里有个IndexedDB内嵌数据库的例子：

演示：https://coderlmn.github.io/offlineDB/


### CSS3

CSS3的出现也大大地简化了前端渲染的工作，它推出的text-shadow、@keyframes animation、attribute Selectors等都使得样式的定义和控制更为简单，效果更为丰富。

这里有个3D Transform的例子：

演示：https://coderlmn.github.io/CSS3dTimeMachine/


### SVG

HTML5支持内嵌SVG，SVG又支持嵌入CSS和JS，使得SVG成为了极其强大的渲染工具。比如，你可以用SVG绘制一张地图，并按照用户给出的起始点绘出最佳路线，或者在HTML5视频中加上各种效果的字幕（关于HTML5视频与SVG的配合方面，firefox目前是支持得最好的，safari也有自己定义的一套方法，不过总体来说还不是很成熟，不同浏览器的支持差别比较大）。

这里有个SVG动画和根据结构化数据动态绘制SVG图的例子：

演示： https://coderlmn.github.io/frontEndCourse/mask.html

### JS

JS主要是融入在前面三部分内容中，另外我觉得DOM树结构及其访问方式比较重要，尤其是树结构及其核心算法。


六、后端RESTful接口和前端的配合
==


web开发一共就那么些事，既然我们说前端干的活多了，那后端就能相对省点事。现在流行的前后端通过JSON来交换数据，后端不再需要弄个像JSP那样的东西来负责渲染页面，就可以专注于数据持久化和权限管理这些真正后端的工作。

具体地说，后端主要用来处理数据CRUD等请求、定时任务、数据分析统计等等。对于处理的请求中需要权限的操作（比如发布和删除），会事先检查用户身份，如用户未登录或权限不足，则返回401(Unauthorized)，前端可以用个interceptor抓取它并转到相应的提示页面。

举个例子，一个RESTful的接口是这么定义的（以Node.js后端为例）：

```javascript
	app.get('/detail/:id', function (req, res) {
    	var id = req.params.id;
    	db.collection('article').findAndModify({_id: new ObjectID(id)}, [], {$inc: {'readCount': 1}}, {}, function (err, data) {
        	if (err) {
            	console.log(err);
        	}
        	res.setHeader('Content-Type', 'application/json; charset="utf-8"');
        	res.end(JSON.stringify(data));
    	});
	});
```


前端发送的请求例子：

```javascript
	var getJson = JSON.parse(getPage(url));
	......
	function getPage(href) {
        var xmlhttp = new XMLHttpRequest();
        xmlhttp.open("GET", href, false);
        xmlhttp.send();
        return xmlhttp.responseText;
    }
```


从前面的例子可以看出，后端api的参数是和前端的XMLHttpRequest.open()调用参数一一对应的。例如在前端的调用：

```javascript
	var getJson = JSON.parse(getPage('/detail/' + id));
```
	
	
对应的就是后端的这个方法：

```javascript
	app.get('/detail/:id', function (req, res) {...}
```


在这个过程中，前端的id作为动态的文章id被加在'/detail/'的后面传递给后端，后端的get('/detail/:id'）函数匹配了这个请求，并取得id去查找mongodb里对应的记录并包装成json返回给前端，前端的回调函数取得json数据赋值给apiJson然后进行下一步的处理。


对于某些需要权限的操作，例如删除文章的函数：

```javascript
	app.get('/remove/:id', authenticated, function (req, res) {...}
```


在参数和回调函数之间加入了一个中间件authenticated，这个中间件会先执行，如果用户没有登录则直接返回401给前端，从而触发前端转向login页面提示用户登录。


演示地址
==

以上就是我目前总结的一些体会，相关的演示都在 https://coderlmn.github.io/frontEndCourse/ 里可以看到。推荐用 Chorme 浏览器，因为这些演示代码我主要是在它上面测试的。


另外，对于无框架单页面应用开发，最近我又整理了自己的一些体会，放在单独的一个项目里：https://github.com/coderLMN/framework-free-single-page-app ，供参考。
