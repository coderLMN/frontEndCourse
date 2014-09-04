2、架构
===

近几年因为HTML5，CSS3的出现并逐渐占据主流位置，web前端开发的整体格局已经有了一个巨大的变化。比如说原先要通过jQuery渲染的一些动画效果，现在用CSS3 animation就轻松搞定了，Drag & Drop这类功能也成为了HTML5的标配。

总体趋势是JS的角色要往后退，主要承担前端逻辑控制和与后端交互的作用，CSS成为前端渲染效果的核心。最近出现的一些前端MVC框架，比如AngularJS，就已经体现了这一趋势。


###前端渲染效果

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


###前端逻辑控制

现在前端交互方式的趋势是局部刷新，单页面应用逐渐会成为web开发的主流方式。在这种情况下，前端的控制逻辑变得越来越复杂，JS的作用在这个领域就变得非常关键了。前面提到，由于HTML5和CSS3提供了非常强大的前端渲染功能，所以从架构的角度来说，能通过HTML和CSS解决的问题就不必惊动JS他老人家了，他有更重要的工作要做。

例如AngularJS在前端逻辑控制中提供了一套Route机制，根据url的变化动态加载相应的控制逻辑和html片段，如果去查看它的源代码里的browser.js，就可以发现这套机制的核心是针对hashchange和popstate事件来进行处理的（这样也就理解了为什么在html5Mode == false的时候，angurlajs应用所有的url前面都会带一个'/#'了)。那么，利用原生JS也可以实现类似的功能。


下面的例子构造了三个链接，点击后分别加载不同的html片段放入div#demo中。演示链接：http://coderlmn.github.io/frontEndCourse/ctrlDemo.html

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



###前后端交互

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
