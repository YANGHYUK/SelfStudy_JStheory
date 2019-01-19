<h1> Dot Notation VS Bracket Notation</h1>

객체(Object)의 Property값에 접근하기 위해서는 2가지 방법이 있다.

바로,

1. Dot Notation	

   ```javascript
   ex) 
   var obj = {
     cat: 'meow',
     dog: 'Bow'
   };
   var sound = obj.cat;
   console.log(sound);
   // meow
   ```

   Object뒤에 점(.) + key갑을 붙이는 것만으로 value값을 출력할 수 있다.

   Property값으로  변수(variable)값이 될 수 없다. 

   단, Dot Notation에서는 Object뒤의 점(.) 의 key값으로 숫자(number)가 올 수 없다. 

   

   Yes

   - obj.prop_1
   - obj.prop$

   No

   - obj.1prop 
   - obj.prop name

   



2. Bracket Notation

   ```javascript
   ex)
   var obj = {
     cat: 'meow',
     dog: 'woof'
   };
   var sound = var['cat'];
   console.log(sound);
   // meow
   ```

   Object뒤 [ ] 안에 'key' 값을 입력하여 value값을 출력할 수 있다. (''안에 띄어쓰기 )

   단,  Bracket Notation에서는 [ ] 안에 넣을 key값의 형태가 string이면 'string'의 형태로 넣어주어야 한다.

   

   Yes

   - obj.['1prop']
   - obj.[prop name] 

   