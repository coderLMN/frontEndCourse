后端RESTful接口和前端的配合
===


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


