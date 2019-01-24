<h1>hosting func (함수의 호출)

```javascript
function sum(arg1, arg2){
  return arg1 + arg2;
}
console.log(sum(1,2)) // --> 3
console.log(sum.apply[null, [1,2]]); // --> 3
//call과 apply는 같은 취지이지만, 사용방법이 다르다.
```



```javascript
o1 = {val1:1, val2:2, val3:3}
o2 = {v1:10, v2:50, v3:100, v4:25}

function sum(){
    var _sum = 0;
    for(name in this){
        _sum += this[name];
    }
    return _sum;
}
console.log(sum.apply(o1)) // --> 6
console.log(sum.apply(o2)) // --> 185
```

**Arguments**가 단순히 숫자일 경우에는,  그냥 **Parameter**값에 대입해여 함수를 실행시켜도 되지만, typeof Argements가 '**object**'의 형태라면 **apply** 를 사용하여 해결할 수 있다.



```javascript
o1 = {val1:1, val2:2, val3:3, sum:sum}
o2 = {v1:10, v2:50, v3:100, v4:25, sum:sum}

function sum(){
    var _sum = 0;
  for(name in this){    
    if(typeof this[name] !== 'function'){
      _sum += this[name];
    }
}
    return _sum;
}
console.log(o1.sum()) // --> 6
console.log(o2.sum()) // --> 185
```

**apply** 를 사용하지 않기 위해서는 객체안에 함수명 자체를 저장시켜서 해결 할 수 있다.