<h1> Arguments(인자)

</h1>



```javascript
function sum(){
    var i, _sum = 0;    
    for(i = 0; i < arguments.length; i++){
        document.write(i+' : '+arguments[i]+'<br />');
        _sum += arguments[i];
    }   
    return _sum;
}
document.write('result : ' + sum(1,2,3,4));
```

시작전 주의! : **parameter**(매개변수)의 갯수와 **arguments**(인자)의 갯수가 달라도 에러를 일으키지는 않는다.

 i 는 iteration을 위한 변수이다.
**arguments**는 javascript안에서 약속되어 있는 단어이며, **인자**를 접근하기 위한 것.



```javascript
function zero(){
    console.log(
        'zero.length', zero.length,
        'arguments', arguments.length
    );
}
zero() // --> zero.length : 0, arguments : 0

function one(arg1){
    console.log(
        'one.length', one.length,
        'arguments', arguments.length
    );
}
one('val1', 'val2') // --> one.length : 1, arguments : 2

function two(arg1, arg2){
    console.log(
        'two.length', two.length,
        'arguments', arguments.length
    );
}
two('val1') // --> two.length : 2, arguments :1



```

위의 내용이 뭐가 중요한가 하면, 

우리가 의도적으로 **parameter** 와 **arguments** 의 갯수가 같도록 함수를 만들려고 했지만, 실수로 인해 **parameter** 와 **arguments** 의 갯수를 다르게 만들었다. 

​                         이때, 자비로우신 javascript님께서는 이를 허용해주신다. 

이 실수를 잡아내기 위해서는 **(함수의 parameter).length**와 **arguments.length**를 비교해볼 필요가 있다.