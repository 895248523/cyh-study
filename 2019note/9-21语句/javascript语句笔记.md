# 第五章 Javascript 语句
###5.1 分支语句
5.1.1 if语句

		var a = 10;
		//小括号里一定要是true
		if (a<20) {
			alert('yes');
		}

5.1.2 if....else语句
	
		var a = 10;
		if(a<10){
				alert('yes')
			}else{
				alert('no');
		}

5.1.3 if ...else if语句

switch小括号中一般情况是一个变量名,这个变量可能会有不同的取值.所有的case都是"或"的关系,case后面的值会与变量值作比对,满足后就执行case后面的代码



		if(a<10){
			alert('yes')
		}else if(a>20){
			alert('no');
		}else{
			alert("重新来")
		}

5.1.4 switch语句

	<script type="text/javascript">
		var a = 10;
		//将判断的内容写在括号里
		switch(a){
			case 值1;
			//执行代码
			break;
			case 值2;
			//执行代码
			break;
			case 值3;
			//执行代码
			break;
			default:
			//执行代码
	}


###5.2 循环语句
5.2.1 while 循环    
while语句是一种前测试语句(先判断一下在执行);循环的目的是为了反复执行语句或代码块,只要表达式为true就继续循环,一旦为假的时候,循环退出.

5.2.2 do...while循环
do.while循环      
do.while语句是一种后测试语句,就是在循环体中的代码执行之后.才开始判断条件,也就是说,在表达式判断之前,循环体内的代码至少会被执行一次

		var a = 0;
		do{
			alert('你好');
			a++;
		}while(a<5);

5.2.3 for 循环

for语句是一种前测试语句,一般情况下,有三个基础表达式语句,每一个都要用分号隔开
		
	    //初始化    判断 		更新
	for(var x = 0; x < y ; x++){
		//执行循环体
		alert(x);
	}
	//顺序为:初始化--->判断--->执行循环体---->更新		
	

##练习
需求:   
1做一个1+2+3+4+5+6+7+8+9+10的和

##作业

1.只做一个模拟的银行取款机    
2.设置一个银行卡号/密码和金额
3.用户输入密码后输入要取得金额.
4.前提不能大于卡内余额.
5.取完后显示去后余额.