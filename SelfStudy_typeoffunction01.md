<h1> Callback 함수의 여러 유형

자바스크립트에서 **함수**는 fitst - class - object(= **변수**, **매개변수**, **리턴값**, **배열**)로 사용 되어질 수 있음. 



```javascript
function a(){}  // --> a()

a= {			
	b:function(){  // --> a라는 객체 안에 b라는 함수를 저장하였다.
    }
};
```

b라고 하는 것은 a라는 객체 안에 어떤 **변수**라 할 수 있다. 왜냐하면 function을 저장해놓았기 때문.

이때, b라는 것을 '**객체(Property)**'라 하며, 이렇게 객체의 속성 값으로 담겨진 함수를 '**Method**'라 함.

정리

1. function a() {} // --> 그냥 function
2. b: function (){} // --> Method



```javascript

function cal(func, num){
  return func(num)
}
function increase(num){
 num += 1; 
 return num
}

function decrease(num){
 return num -1;
}
```

함수는 값이기 때문에  다른 함수의 **인자**(**매개변수**)로 전달 될 수 있다.



```javascript
function cal(what){
  var funcs = {
    'plus' : function(first, second){return first + second},
    'minus' : function (first, second){return first + second}
  }
  return funcs[what]
}

console.log(cal('plus')(1,4)) // --> 5
```

함수는 함수의 **리턴 값**으로도 사용할 수 있다.





```javascript
var process = [
  function(input){ return input + 10;},
  function(input){ return input * input;},
  function(input){ return input / 2;}
];

var input = 1;
for(var i = 0; i < process.length; i++){
    input = process[i](input);
}
console.log(input) // --> 60.5
```

함수는 배열의 값으로도 사용할 수 있다.

