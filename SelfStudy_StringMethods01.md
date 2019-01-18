<h1> String, Number/Math, Array Methods

**결론:** 모든 String Methods 는  ***Immutable***



1.String Methods 정리

```javascript
1. str.trim() // 호출 문자열 양 끝에서 공백을 제거한 새로운 문자열
2. str.concat(str2, str3..) // 인자로 주어진 배열이나 값들을 기존 배열에 합쳐 새 배열을 반환
3. str.indexOf(searchValue) // 찾고자 하는 문자열의 index를 반환
4. str.split(seperator) // seperator(arguments)를 분리 기준으로 하여 문자열 반환
5. str.substring(start, end) // [start, end](arguments) start시점에서 end시점 전까지의 문자열 반환
6. str.match(words) // 해당 words가 str에 있다면 해당 words를 반환
					// 단!, if words === Infinity && str에 Infinity 가 존재할 경우 Infinity의   
					// 타입은 number이므로 +Infinity로 입력해서 찾아야만 된다.
7. sentence.replace(str1, str2) // sentence내에 str1이 존재한다면 이 문자를 str2로 바꾸어 준다.
```





2. Number/Math Methods 정리 

   ```javascript
   1. Number.isInteger(value) // value가 정수인지, 아닌지 여부 검사
   2. parseInt(value) // value값의 소수를 다 버리고 정수값만 출력
   		- parseInt('101',2)  //--> 5 [2진법수 101을 10진법수 5로 출력]  	
   3. parseFloat(value) // value값 그대로를 출력한다. 
   4. num.toFixed(digits) // num의 소수값을 digits번째까지만 출력한다.
   5. Math.min(num1, num2, num3) // 가장 최소값의 num을 출력한다.
   6. Math.max(num1, num2, num3) // 가장 최대값의 num을 출력한다.
   7. Math.floor(num) // num값을 내림한 값
   8. Math.round(num) // num값을 반올림한 값
   9. Math.random(num) // 0~1사이의 값을 랜덤하게 뽑아낸 값
   10. Math.abs(num) // num의 절대값을 반환
   11. Math.sqrt(num, ~제곱근) // ex) Math.sqrt(100,2) --> 100의 제곱근 = 10
   12. Math.pow(num, ~제곱) // ex) Math.por(10,2) --> 100
   
   ```

   

3. Array Methods 정리

   ```javascript
   1. arr.length // arr의 길이를 반환
   2. Array.isArray(obj) // obj가 배열이면 true반환 아니면 false를 반환
   3. arr.forEach(callback) // Immutable,  예제를 보는 것이 빠르다
      ex:
   ->	function printArray(currentElement, index, array) {
     	  console.log(index + ': ' + currentElement);
   	}
   
   	['hello', 3, 5].forEach(printArray);
   	// 0: hello
   	// 1: 3
   	// 2: 5
   4. arr.map(callback) // arr의 각 요소마다 callback을 적용함
      ex:
   ->  [1, 3, 5].map(function(currentElement, index, array) {
      return currentElement * 2;
      });
      // [2, 6, 10]
   5. arr.filter(callback)// arr내의 요소들이 callback의 조건을 통과한 것들을 반환
      ex:
   -> [1, 3, 5].filter(function(currentElement, index, array) {
      return currentElement > 1
      });
      // [3, 5]
   6. arr.push(newElement) // arr의 마지막 index에 newElement를 추가.
      ex:
   -> ['code', 'states'].push('course'); // ['code', 'states', 'course']
      [1, 3, 5].push(7, 9); // [1, 3, 5, 7, 9]
   7. arr.pop() // arr의 마지막 index제거
      ex:
   -> var arr = ['code', 'states', 'course'];
      arr.pop(); // 'course'
      console.log(arr); // ['code', 'states'];
   8. arr.slice([begin[, end]]) // arr의 begin번째부터 end전 까지를 복사하여 반환
   9. arr.splice(start, deletecount, ~) // immutable, 복사&삭제 가능
      ex:
   -> var myFish = ['angel', 'clown', 'mandarin', 'sturgeon'];
      myFish.splice(2, 0, 'drum'); // 'drum'을 두번째 인덱스에 삽입
      // ["angel", "clown", "drum", "mandarin", "sturgeon"]
   
      myFish.splice(2, 1); // 두번째 인덱스에서 하나의 항목('drum')을 삭제
      // ["angel", "clown", "mandarin", "sturgeon"]
   10. arr.reduce(callback[, initialValue]) // immutable, 
       ex: 
    -> var myArray = [1,2,3,4,5];
       myArray.reduce(function(accumulator, currentValue) {
       return accumulator + currentValue;
       })
      // 15
   11. arr.join(); // 배열값들을 ()으로 접합하여 string으로 출력
   12. arr.split(); // ()안의 요소로 분리하여 배열값으로 출력
   13. arr.indexOf(searchElement) // arr내에서 searchElement의 index를 출력
   14. arr.shift(); // arr의 첫 요소를 삭제 
   15. arr.unshift(); // immutable, arr의 마지막 요소를 출력  
   16. arr.reverse(); // arr의 요소를 역순으로 출력
   17. arr.sort(); // arr의 요소의 첫 글자 순서를 토대로, 작은 것부터 나열
       ex:
    -> var months = ['March', 'Jan', 'Feb', 'Dec'];
       months.sort();
       console.log(months);
       // expected output: Array ["Dec", "Feb", "Jan", "March"]
   
       var array1 = [1, 30, 4, 21];
       array1.sort();
       console.log(array1);
       // expected output: Array [1, 21, 30, 4]
   
   
   ```
