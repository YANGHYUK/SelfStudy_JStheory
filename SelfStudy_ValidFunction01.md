<h1>함수</h1>



함수의 유효범위

- javascript는 함수에 대한 유효범위만을 제공한다.  // --> 범위는 함수안 or 함수밖으로만 구분되어진다.

```javascript
var vscope = 'global';
function fscope(){
		var vscope = 'local';
		console.log(vscope);
}

fscope(); // --> 실행결과는 'local'
console.log(vscope); //--> 실행결과는 'global'
```

**결론:** 함수내 **var** 로 표시된 변수는 그 함수 안에서만 접근할 수 있다. 이는 함수**안**(=지역)에서만 실행가능하다는 의미로 '**지역변수**'라 말한다. 





```javascript
var vscope = 'global';
function fscope(){
		vscope = 'local';
    	console.log(vscope);
}

console.log(vscope); // --> 실행결과는 'global' [함수 실행 전]
fscope(); // --> 실행결과는 'local'[함수 실행 후]

```

**결론:** 함수 내 **var**로 표시되지 않은 변수는 그 함수 밖에까지 접근할 수 있다. 이는 함수**밖**(=전역)에서도 실행가능하다는 의미로 '**전역변수**'라 말한다.

즉,

 함수 실행 전, console.log(vscope)의 값과 함수 실행 후, console.log(vscope)의 값이 다름을 이해하는 것이 중요하다. 





```javascript
var vscope = 'global';
function fscope(){
		var vscope = 'local';
		vscope = 'local';
    	console.log(vscope);
}

fscope(); // --> 실행결과는 'local'
console.log(vscope); // --> 실행결과는 'global'

```

**결론:** 함수내에 **var** vscope 가 한번 등록되었다면, 같은 함수내에서 **var** 없이 vscope를 사용하더라도 이는 **지역변수**로써 쓰이게 된다. 
즉, 

함수 실행했을 때의 fscope(); 값과 함수 실행 전 console.log(vscope)의 값은 다르지만, 

함수 실행 전 console.log(vscope)의 값과 함수 완전히 실행된 후의 console.log(vscope) 입력 값이 같음을 이해하는 것이 중요하다.   





+bonus 익명함수

```javascript
(function(){
	var MYAPP = {}
	MYAPP.calculator = {
		'left' : null,
		'right' : null
	}
	MYAPP.calculator.left = 10;
	MYAPP.calculator.right = 20;
    
    function sum(){
		return MYAPP.calculator.left + MYAPP.calculator.right;
	}
	console.log(sum()); // --> 실행결과는 '30'
})()

```

**결론:** 위의 함수는 이름조차 없는 **익명함수**다. 함수의 이름을 붙이는 것 조차 변수를 생성하는 것이다. 변수생성을 하고 싶지 않은 상황에서 함수를 만들고자 하면 다음과 같이 하면 된다.
(function(){}) + () 

이는 익명의 함수를 만들고 그 함수의 전체를 바로 실행시키게 한다. 



