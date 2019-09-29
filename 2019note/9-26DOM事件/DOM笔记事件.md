#第七章 DOM事件
###7.1 鼠标和键盘事件
#####7.1.1 鼠标事件

单一作用于某个元素的事件



	<script type="text/javascript">
		var mydiv = document.getElementById("mydiv");
		//点击事件
		mydiv.onclick=function(){}
		//双击事件
		mydiv.ondblclick=function(){
			alert("双击事件");
		}
		//鼠标按下事件
		mydiv.onmousedown=function(){
			mydiv.innerHTML="按下事件";	
		}
		//鼠标抬起事件
		mydiv.onmouseup=function(){
			mydiv.innerHTML="";
		}
		//鼠标移动
		//需要注意的是只要鼠标移动就会触发
		document.onmousemove = function(){
			console.log('移动了');
		}
		mydiv.onmousemove=function(){
			console.log('div');
		}
		//鼠标移入
		//会触发冒泡(从内逐级向外依次触发)
		mydiv.onmouseover=function(){
			alert("移入了");
		}
		document.body.onmouseover=function(){
			console.log("aaa");
		}
		//鼠标移除
		mydiv.onmouseout=function(){
			alert("移出了");
		}
		//会触发多次,取决于嵌套和鼠标位置
		document.body.onmouseout=function(){}
		//鼠标移入，只能一次(没有事件冒泡这一说)
		mydiv.onmouseenter=function(){}
		//鼠标移入,只能一次（没有事件冒泡这一说）
		mydiv.onmouseleave=function(){}
	</script>

鼠标移入移出情况

(1)第一套移入移出会多次触发
	
	mydiv.onmouseover=function(){
		alert("移入了");
	}
	mydiv.onmouseout=function(){
		alert("移出了");
	}


(2)第二套移入移出不会多次触发
	//鼠标移入，只能一次(没有事件冒泡这一说)
	mydiv.onmouseenter=function(){}
	//鼠标移入,只能一次（没有事件冒泡这一说）
	//会触发多次,取决于嵌套和鼠标位置
	mydiv.onmouseleave=function(){}

#####7.1.2 键盘事件
键盘的按钮按下时会触发onkeydown事件,在函数中的e参数代表是哪一个事件触发的.

    document.onkeydown = function(e){
    	alert("按下");
    }

键盘的抬起会触发onkeyup事件它与onkeydown用法一样.

    document.onkeyup = function(e){
    	alert("抬起");
    }


###7.2 Event事件对象
#####7.2.1 Event事件对象的概念
Event对象代表事件的状态,比如事件在其中发生的元素,键盘按键的状态、鼠标的位置、鼠标按钮的状态等等等等。     

#####7.2.2 Event事件对象产生的时间
当用户单击某个元素的时候,我们给这个元素注册的事件就会触发,该事件的本质就是一个函数,而该函数的形参接收一个event对象.
事件通常与函数结合使用，函数不会在事件发生前被执行！


#####7.2.3 Event事件对象接受方式
通过事件触发时的函数,以参数的形式传递进该函数内,不用外部传参,也就是说event对象是事件触发时,调用函数时的第一个参数.

	//事件触发时,  	  调用的函数(event)
	document.onclick=function(event){
		console.log(event);
	}

#####7.2.4 event对象常用属性
鼠标的坐标值:

	e.clientX和e.clientY	
	
键盘的值:
	
	e.keyCode

#####7.2.5 event的兼容性
event对象根据不同浏览器他的获取是不同的方法,以下是针对获取event对象的兼容性写法:

	document.onclick=function(event){
		//		非IE  ||   低版本IE
		var e = event||window.event;
		console.log(e.clientX);
	}

###7.3 对象事件
#####7.3.1 页面(元素)加载完成后执行
window.onload是等待页面加载完成之后,执行函数的内容,当然函数没有重载也就是说window.onload只能写一次。

	//页面加载完成之后执行函数内的代码段
	window.onload=function(){
		var mydiv = document.getElementById("mydiv");
		mydiv.onclick=function(){
			alert(mydiv.tagName);
		}
	}


##练习
需求1：浏览器窗口变化随机变色      
1.缩放浏览器窗口触动事件
2.在窗口缩放的时候body随机改变自身颜色

需求2：     
1.做一个简单的注册界面     
2.要求用户名和密码必须写才可以提交,    
3.提交之后弹出注册成功.    
4.如果有没写的内容 进行提示    
5.用户准备填写时,在右侧提示该用户名是否可以注册.   
6.一个已经有的用户名库,可以用一个数组创建已有用户名    
7.已有用户名分别为"tom","jack","lili"