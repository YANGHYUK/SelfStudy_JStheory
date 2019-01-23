<h1> Closure 함수
    
</h1>



Closure는 내부 함수가 외부함수에 접근할 수 있는 것을 가르킨다. (고난이도 테크닉임)

간단 예제를 통해 알아보자.

```javascript
function outter(){
    var title = 'coding everybody';  
    function inner(){        
        alert(title);
    }
    inner();
}
outter();
```

위의 예제를 보면 inner()함수가 실행됨과 동시에 alert(title)이 실행되는데 title은 inner()함수의 외부함수에서 가져다 오는 것이다.



고급 예제를 통해 생각해보자.

```javascript
var arr = []
for(var i = 0; i < 5; i++){
    arr[i] = function(){
        return i;
    }
}
for(var index in arr) {
    console.log(arr[index]());
}
```

위의 예제를 보면, 결국 arr [index] () 를 통해 함수가 실행되어도 결과 값이 5, 5, 5, 5, 5가 나온다.
이에 대한 원인을 찾아보자면, for(var i = 0; i < 5; i++)~~~가 실행될 때, arr[0], arr[1], arr[2], arr[3], arr[4]가 생겨나지만 arr[i] 와 같다고 생각하는 function()은 실행되지 않는다. 함수를 실행하는 명령어가 따로 없기 때문이다. 

현재, 가장 중요한 키포인트는 arr[0], arr[1], arr[2], arr[3], arr[4] 은 생겨났으며, 현재의 i 값은 **5** 라는 것이다. 

그렇기에,  arr [index] () 이 실행되자마자, arr[0], arr[1], arr[2], arr[3], arr[4] 의 return 값으로 i = 5가 부여되는 것이다.

이에 더하여 +

우리가 진정원했던 0, 1, 2, 3, 4 를 출력하려면 아래와 같은 코드를 짜야 한다.

```javascript
var arr = []
for(var i = 0; i < 5; i++){
    arr[i] = function(id) {
        return function(){
            return id;
        }
    }(i);
}
for(var index in arr) {
    console.log(arr[index]());
}
// 0
// 1
// 2
// 3
// 4
```

위를 보면 일반적으로 function은 하나의 return값을 갖는다. arr[0], arr[1], arr[2], arr[3], arr[4]의 각각의 값으로 0, 1, 2, 3, 4를 나타내기 위해서는 arr[i]의 값이 정해지자 마자 return 값이 출력되야 하므로 새로운 **클로저**함수를 추가하여 함수를 즉시 실행시킬 수 있게 한다. 



