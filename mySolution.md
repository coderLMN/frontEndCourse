1⃣️ 三张图片居左、居中、居右

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


2⃣️ 4行x3列的表格

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


3⃣️图片被点击后，顺序顺时针移动

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


4⃣️ 可定制多级联动单选

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
