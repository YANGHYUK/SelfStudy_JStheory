<h1> 함수의 생성자 & new

생성자(constructor) : 객체를 만드는 역할을 하는 함수.

1. 함수를 생성한다.
2. 생성한 함수에 new를 붙인다. --> 함수는 객체로 변신!

```javascript
function Person(){}
var p = new Person();   // 이 줄에서 Person을 '생성자'라고 함.
p.name = 'egoing';
p.introduce = function(){
    return 'My name is '+ this.name; 
}
document.write(p.introduce());
```



```javascript
function Person(name){
    this.name = name;
    this.introduce = function(){       
        return 'My name is '+this.name; 
    }   
}
var p1 = new Person('egoing');
document.write(p1.introduce()+"<br />");
 
var p2 = new Person('leezche');
document.write(p2.introduce());
```

생성자 함수안에 작성함으로써, 지속적으로 초기화 (initialize) 할 수 있다. 

--> 코드의 재사용성이 대폭 높아짐