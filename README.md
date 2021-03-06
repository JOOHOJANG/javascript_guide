# 자바스크립트 완벽가이드 정리

## 1. 자바스크립트 소개

## 2. 어휘구조

1. 코드를 2개의 줄로 나눌 때 앞줄이 온전한 문장이라면 자동으로 세미콜론을 삽입해준다.

   1. ex ) return

    true; 는 잘못된 표현임 -> return ; true; 로 인식함.

2. 자바스크립트는 Unicode 문자 집합을 사용하여 작성됨. (16비트)

3. 리터럴 :

   1. 리터럴은 프로그램에 직접 나타나는 데이터 값임.
   2. ex) 10, 1.0, "hello", true, /jooho/ 등

## 3. 타입 값, 변수

1. 자바스크립트의 타입은 크게 원시 타입, 객체 타입으로 나뉨.
2. 원시타입의 값은 변경되지 않는다.
3. null, undefined는 원시 타입이지만 숫자도 문자도 불리언도 아니다.
4. 자바스크립트에서는 함수도 특별한 객체이다. 함수는 값이고, 자바스크립트 프로그램은 함수를 보통 객체처럼 다룰 수 있음.
5. 자바스크립트 인터프리터는 메모리 관리를 위해 자동으로 가비지 컬렉션을 수행한다.
6. 자바스크립트에서 모든 숫자는 실수로 포현한다.
7. 0으로 나누는 연산은 에러가 아님. -Infinity, Infinity를 반환함. 0을 0으로 나눌때는 NaN이라는 값을 반환하는데 여기서 NaN은 값이 같은지 다른지 비교할수 없는 특별한 값.
8. 자바스크립트에서 문자열은 변경되지 않는다.
9. null 은 typeof(null)을 하면 object를 반환함. 즉, 객체가 없음을 나타내는 특수한 객체값.
10. undefined는 초기화가 안된 변수나, 존재하지 않은 객체 프로퍼티, 배열의 원소 등에 접근했을때 반환되는 값이다.
11. wrapper객체
    1. 자바스크립트 객체는 복합적인 값이다. 객체는 프로퍼티 또는 이름 있는 값들의 집합이다. 프로퍼티의 값이 함수일 때, 그 함수를 메서드라 부른다.
    2. 문자열의 프로퍼티를 참조하려 할 때, 자바스크립트는 new String()를 호출한 것처럼 문자열 값을 객체로 변환함.
    3. 값을 할당하는 것은 임시 객체에서 수행되며, 지속되지 않는다.
12. 자바스크립트는 값의 타입을 유연하게 변화시킬 수 있음.

## 4. 표현식과 연산자

1. 기본 표현식 

   1. 상수, 리터럴 값, 특정 키워드, 변수 참조를 뜻함. 
   2. this는 프로그램 내에서의 위치에 따라 다른 값으로 평가된다.
   3. 전역객체의 경우 window로 표시되며, 메서드 안에서는 메서드를 호출한 객체로 표시된다.

2. 프로퍼티 접근 표현식

   1. .(점) 혹은 ([]) 대괄호 표현식이 먼저 평가된다. 만약 값이 null 혹은 undefined이면 TypeError 예외가 발생된다. 
   2. .(점) 문법은 프로그램을 작성할때 그 식별자를 알고 있어야 사용이 가능하며, 만약 프로퍼티 이름이 예약어이거나, 구두점 문자, 숫자일 경우 대괄호를 사용해야한다. 

3. 호출 표현식

   1. 자바스크립트는 값을 표현한다.
   2. 함수의 경우 값을 반환하지 않는다면 함수 표현식의 값은 undefined가 된다.

4. 객체 생성 표현식

   1. 생성자 함수를 통해서 객체의 프로퍼티들을 초기화 시킨다. 
   2. 빈 객체(Object)를 생성하고 전달받은 parameter들과 생성자를 호출함. 
   3. 생성자 함수는 this 키워드를 사용해 새로 생성된 객체의 프로퍼티들을 초기화 시킴. 

5. 산술 표현식

   1. 비교, 평가가 불가능한 값은 NaN으로 반환되며, 연산자 중에서 하나라도 NaN인 경우 결과도 NaN이 된다. 

   2. 0으로 나누는 경우도 Infinity, -Infinity로 표현된다. 

   3. 자바스크립트의 모든 숫자는 부동소수점으로 표현된다.

   4. 

      1. ``` javascript
         2 + 2                   // => 4: 좌, 우 모두 Number 타입이므로 더하기 
         "1" + "2"               // => "12" : 좌, 우 모두 문자열이므로 문자열 합치기
         "1" + 2                 // => "12" : 우측의 숫자 2를 문자열로 바꾼 후 문자열 합치기
         1 + {?}                 // => "1[object Object]": 객체를 문자열로 바꾼 후 합치기
         true + true             // => 2: 좌, 우의 bool 값을 숫자(1)로 바꾼 후 더하기
         2 + null                // => 2: null 값을 0으로 바꾼 후 더하기
         2 + undefined           // => NaN: undefined를 NaN으로 바꾼 후 더하기
         ```

   5. 관계형 표현식 

      1. ==, === 은 같음을 표현하는데 쓰이지만 정의가 다르다. 

         1. ==는 동치, ===는 일치 임. 

         2. ``` javascript
            console.log(1=="1") // true
            console.log(1==="1") // false
            ```

6. 비교 연산자.

   1. 피연산자 타입에 제한은 없지만, 숫자와 문자열만 비교가 가능하기때문에 숫자나 문자열이 아닌 피연산자는 먼저 반환됨.

7. in 연산자

   1. 좌변의 피연산자로 문자열로 반환될 수 있는 것을 받는다.
   2. 우변의 피연산자로 객체나 배열을 받는다. 
   3. 좌변이 우변의 프로퍼티에 해당할 경우 true를 return 받는다. 

## 5. 문장

1. 표현문

   1. 자바스크립트의 문장 중에서 가장 간단한 형태는 부수 효과가 있는 표현문이다. 

   2. ``` javascript
      greeting = "hello" + name;
      i+=1;
      ```

2. 복합문, 빈 문장

   1. 자바스크립트는 블록 단위 scope가 존재하지 않기 때문에 블록 내부에 선언된 변수는 블록 바깥에서도 접근이 가능하다.

   2. 빈 문장을 사용할 경우에는 주석을 달아서 설명을 남겨주는것이 좋다. 

      1. ``` javascript
         for(i = 0 ; i <100; arr[i++] = 0); //배열 초기화용
         ```

3. 선언문

   1. var
      1. 한 개 이상의 변수를 선언한다. 변수의 초기값을 설정하지 않으면 변수는 undefined 값을 갖는다. 
      2. 스크립트 혹은 함수 안에서 선언된 변수의 경우 해당 함수 전체에 걸쳐서 유효하지만 초기화는 선언된 시점과 다르게 발생할 수도 있기 때문에 초기화 전까지 변수는 undefined 값을 갖는다. 
   2. function
      1. 함수가 다른 함수 내에서 선언될 경우, 중첩된 함수 내에서 최상위 단계에 위치해야한다. 
         1. 즉, if, while등 조건문 안에서 선언될 수 없다.
      2. 함수 선언문은 함수 표현식과는 엄연히 다르다. 앞서 공부했던 hoisting을 생각하면 된다. 

4. 조건문

   1. if/else, switch 가 존재한다. 

5. 루프

   1. while, do/while, for, for in 이 있다. 

   2. for in

      1. ``` javascript
         for (변수 in 객체)
           문장
           
         for(a in obj){
           console.log(obj[a]);
         }
         ```

      2. 위 형식으로 작성하며, for in 을 사용하기 위해서는 자바스크립트 인터프리터는 먼저 객체 표현식을 확인한다. 

      3. null 혹은 undefined 로 확인되면 인터프리터는 for 문 실행을 멈추고 다음 문장을 실행한다.

6. 점프문

   1. return 
      1. 함수 호출은 표현식이고 모든 포현식은 값을 가진다. 
      2. return은 함수 내부에만 존재할 수 있다. 
      3. return이 존재하지 않는다면 함수의 끝까지 수행한 후 호출 지점으로 돌아간다. 이 경우 해당 함수의 값은 undefined 이다.
   2. throw
      1. 자바스크립트는 런타임 에러가 발생할때마다 Error 객체를 통해서 에러를 전달한다. 
      2. call stack을 따라서 상위 예외가 올라가는데, 만약 상위 호출자를 찾을 수 없다면 해당 예외는 에러로 간주되어 사용자에게 전달된다. 
   3. try, catch, finally
      1. try : 예외가 발생할지도 모르는 코드블록
      2. catch : try 블록 내부에서 예외가 발생할 경우 수행되는 코드블록
      3. finally : try블록에서 예외가 발생하더라도 항상 실행이 보장되어야하는 코드블록
      4. 정상적이라면 try블록 끝까지 수행된 후 finally 블록으로 이동해서 나머지 수행이 되어야한다. 
      5. 만약 중간에 return, continue, break 등 제어문을 만나 try 블록의 수행이 중단된다면, 새로운 지점으로 이동하기 전에 finally 블록을 수행하고 이동한다. 
      6. 만약 예외를 처리할 수 있는 catch블록이 없다면 상위 블록으로 예외를 전파한다. 

## 6. 객체

1. 자바스크립트의 기본 데이터타입은 객체다. 

2. 객체는 프로퍼티를 동적으로 추가하고 제거할 수 있다.

3. 자바스크립트에서 숫자, 문자열, bool, null, undefined를 제외한 나머지는 모두 객체다. 

4. 3개 부류의 자바스크립트 객체

   1. 네이티브 객체 : ECMAScript에 명세에 정의된 객체. Array, Date, Function, 정규 표현식
   2. 호스트 객체 : 브라우저같이 자바스크립트 인터프리터가 내장된 호스트 환경에 정의된 객체
   3. 사용자 정의 객체 : 자바스크립트 코드의 실행으로 생성된 객체 

5. 2개 종류의 프로퍼티

   1. 고유 프로퍼티 : 객체에 직접 정의된 프로퍼티
   2. 상속 프로퍼티 : 객체의 프로토타입 객체가 정의한 프로퍼티

6. 객체 생성

   1. 객체 리터털, new 키워드, Object.create()로 생성할 수 있다. 

   2. 프로토타입

      1. 객체는 프로토타입으로부터 프로퍼티를 상속받는다. 자세한 내용은 블로그 Day2 게시물 참고. 

   3. 프로퍼티 접근 및 설정

      1. 연관 배열로서의 객체
         1. 4장 내용의 연장선. 프로퍼티는 .(점), ([]) 배열로 접근이 가능하다. 
         2. 배열로 접근을 해야할 수 밖에 없는 상황이 존재한다. 가령 프로그램 수행 중 동적으로 프로퍼티를 할당하고 해당 프로퍼티에 접근해야 하는 경우, .(점)으로는 접근이 불가능하다. 
      2. 상속
         1. 객체의 프로토타입은 프로퍼티가 상속되는 chain을 유지하고 있다. 
            1. 프로토타입 chain을 따라서 해당 프로퍼티 혹은 메서드가 존재하는지 확인한다. 
               1. (이 내용 또한 블로그 Day2 참고, 상수시간에 찾을수 있음.)
      3. 삭제
         1. 상속받은 프로퍼티는 삭제가 불가능하다. 
         2. 고유 프로퍼티만 삭제가 가능하다. 
         3. delete 연산자를 통해 객체의 프로퍼티 삭제가 가능하다. 

   4. 프로퍼티 검사

      1. in, hasOwnProperty() 를 통해서 프로퍼티가 존재하는지, 만약 존재한다면 상속받은 프로퍼티인지 확인할 수 있다.

      2. ```javascript
         var obj = {x:1};
         console.log("x" in obj) // true
         console.log("y" in obj) // false
         
         console.log(obj.hasOwnProperty("x")) //true
         console.log(obj.hasOwnProperty("toString")) // false : 상속받은 프로퍼티
         ```

   5. 프로퍼티 Getter, Setter

      1. 프로퍼티의 값은 getter/setter 메서드로 대체할 수 있다. 이렇게 정의된 프로퍼티는 단순히 값을 갖는게 아닌 '접근자 프로퍼티' 라고 한다. 

      2. 프로그램이 객체의 접근자 프로퍼티 값에 접근하면 자바스크립트 엔진은 getter 메서드를 parameter 없이 호출하고 반환 값은 프로퍼티의 접근 표현식의 값이 된다. 

      3. 프로퍼티의 값을 변경할때는 자바스크립트 엔진이 setter 메서드를 호출하고 할당자 = 오른쪽에 있는 값을 새로운 값으로 설정하는 것으로 받아들인다. 

      4. 프로퍼티가 writable 속성을 갖는 반면에 접근자 프로퍼티는 쓰기 속성이 없다. 만약 프로퍼티가 getter/setter 메서드를 둘 다 갖고있다면 읽기/쓰기 모두 가능한 프로퍼티이며 getter만 갖고있다면 읽기 전용 프로퍼티인것이다.

      5. setter method만 갖고있는 프로퍼티를 읽으려고 한다면 undefined가 반환된다. 

      6. ```javascript
         var o = {
           // 데이터 프로퍼티
           data_prop: value,
           // 한 쌍의 함수로 정의된 접근자 프로퍼티
           get accessor_prop() { },
           set accessor_prop(value) { },
         }
         ```

   6. 프로퍼티 속성

      1. 프로퍼티로 할 수 있는 작업을 결정하는 세가지 속성이 존재한다. 

         1. Writable : 프로퍼티 값이 변경 가능한지 여부
         2. Enumerable : 프로퍼티가 열거될 수 있는지 여부
         3. Configurable : configurable 속성뿐 아니라 writable 속성과 enumerable 속성 값의 변경 가능 여부

      2. ```javascript
         Object.defineProperty(Object.prototype,
           "extend",       // Object.prototype.extend를 정의한다.
           {
             writable: true,
             enumerable: false,      // 열거 불가능
             configurable: true,
             value: function(o) {
               // Object.prototype.extend 메서드의 값은 함수다.
               // 열거되지 않는 프로퍼티들을 포함한 고유 프로퍼티에 대해
               var names = Object.getOwnPropertyNames(o);
               for(var i = 0; i < names.length; i ++) {
                 // this 객체에 이미 같은 이름의 프로퍼티가 존재하면 건너뛴다.
                 if (names[i] in this) continue;
                 // 객체 o의 프로퍼티 디스크립터를 가져온다.
                 var desc = Object.getOwnPropertyDescriptor(o, names[i]);
                 // this 객체에 프로퍼티를 생성할 때 앞에서 가져온 디스크립터 객체를 사용한다.
                 Object.defineProperty(this, name[i], desc);
               }
             }
           }
         );
         ```

   7. 객체 속성

      1. 프로토타입 속성
      2. class 속성
         1. 객체의 class 속성은 객체의 타입에 대한 정보를 담고 있는 문자열이다.
         2. Object.prototype으로부터 상속되는 toString() 메서드는 객체의 타입을 아래 형태의 문자열로 반환한다.

      3. extensible 속성
         1. 객체에 새 프로퍼티를 추가할 수 있는지 결정한다. 
         2. 목적은 '잠겨있는' 객체를 고정하고 외부에서 변경하는것을 막기 위함이다. 

   8. 직렬화

      1. 객체의 상태를 문자열로 변환하는 것을 의미한다. 
      2. JSON(JavaScript Object Notation), JSON.stringfy() 메서드를 통해 객체를 직렬화하고 JSON.parse()메서드를 통해 복원할 수 있다. 
      3. JSON.stringify()는 객체가 가진 열거 가능한 프로퍼티만 직렬화 할 수 있다. 

## 7. 배열

1. 자바스크립트에서 배열의 값은 고정되어있지 않다. 같은 배열에있는 원소 값의 타입은 다를 수 있다. 

2. 자바스크립트의 배열은 동적이다. 필요에 따라서 크기가 커지거나 작아질 수 있다. 

3. 자바스크립트 배열은 자바스크립트 객체의 특별한 형태이며, 배열의 인덱스는 프로퍼티의 정수형 이름이다. 

4. 배열은 Array.protorype의 프로퍼티를 상속받는다. 

5. ```javascript
   var arr =[1,2,3];
   var arr = new Array();
   var arr = new Array(10);
   var arr = new Array(1, 2, 3, 4, 5, "str")
   ```

6. 희소배열

   1. 배열에 속한 원소의 위치가 연속적이지 않은 배열을 말한다.

   2. 일반적으로 length는 배열에 속한 원소의 갯수를 뜻하지만, 희소배열에서는 length가 원소의 갯수보다 크다,. 

   3. ```javascript
      var a = new Array(5);      // a의 length는 5이지만 원소는 없다. 
      var a = [];               // length 값이 0인 빈 배열을 생성한다.
      var a[1000] = 0;           // 하나의 원소를 할당했지만, length 값은 1001이 된다.
      ```

7. 배열에 원소 추가/삭제

   1. 새 인덱스 값을 할당한다

   2. Push()메서드를 사용해서 배열의 뒤에 새로운 원소 삽입

   3. unshift()메서드를 사용해서 배열의 앞에 새로운 원소 삽입

      1. ```javascript
         var arr = [1,2,3,4,5]; 
         console.log(arr)  // 1,2,3,4,5
         arr.unshift(2);
         console.log(arr) // 2,1,2,3,4,5
         ```

   4. delete 연산자를 사용해서 배열의 원소 삭제. (길이는 줄어들지 않는다)

   5. pop()메서드를 사용해서 배열의 맨 뒤 원소를 삭제. 

   6. 배열의 원소를 삭제하는건 undefined 값을 할당하는것과 같다. 배열의 길이는 줄어들지 않고 배열은 희소배열이 된다. 

8. 배열 메서드

   1. sort()

   2. reverse()

   3. join()

      1. join()은 배열의 모든 원소를 문자열로 변환하고 해당 문자열을 이어붙인 결과를 반환한다. 

      2. 별도의 구분자 문자열을 입력하지 않으면 ,(쉼표)가 기본 구분자가 되어 문자열을 반환한다. 

      3. ```javascript
         var arr = [1, 2, 3];
         console.log(arr.join()) // 1,2,3
         console.log(arr.join(" ")); // 1 2 3
         console.log(arr.join("/")); // 1/2/3
         ```

   4. concat()

   5. slice()

   6. splice()

   7. push(), pop()  : 배열의 맨 뒤 원소를 추가 / 삭제

   8. shift(), unshift() : 배열의 맨 앞 원소를 추가 / 삭제

   9. toString()

9. ECMAScript 5 배열 메서드

   1. ECMAScript 5는 배열을 순회, 매핑, 필터링, 검색, 테스팅, 감소하기 위한 9가지 새로운 메서드를 정의한다. 

   2. 위 메서드들은 배열의 각 원소마다 한번씩 수행하거나 일부 원소들에 한해서 수행된다. 

   3. forEach()

      1. 배열을 순회하는 메서드이다. 각 인자는 배열의 원소 값, 원소의 인덱스 값, 배열 이다 

      2. 위 메서드는 배열을 모두 순회하기 전에는 종료되지 않는다. 

      3. ```javascript
         var arr = [1,2,3,4,5];
         var sum = 0;
         arr.forEach(function(val){
           sum+=val;
         })
         console.log(sum) // 15
         
         arr.forEach(function(val, i, arr){
           arr[i] = val+1;
         })
         console.log(arr) // [2,3,4,5,6]
         ```

   4. map()

      1. 배열의 각 원소를 지정한 함수로 전달하고 해당 함수의 반환값을 배열의 원소로 저장한다.

      2. ````javascript
         var arr = [1, 2, 3];
         var b = arr.map(function(x){
           return x*x;
         })
         console.log(b) // [1, 4, 9]
         ````

   5. filter()

      1. 주어진 조건에 맞는 배열의 일부를 반환한다. 이를 전달하는 함수는 조건자 함수 즉, true 나 false 를 항상 반환해야한다. 

      2. ```javascript
         var arr = [1,2,3,4,5]
         var small = arr.filter(function(x){
           return x>3;
         })
         console.log(small)  // [4, 5]
         ```

   6. every(), some()

      1. 위 두 메서드는 조건자 함수이다. 
      2. every()는 배열의 모든 원소가 해당 조건을 만족하면 true, 아니면 false 를 반환한다. 
      3. some()은 배열의 어떤 원소가 해당 조건을 만족하면 true, 아니면 false 를 반환한다. 
      4. 메서드의 반환값이 결정되면 해당 함수는 수행을 중단한다.

10. 문자열을 배열처럼 사용

    1. 문자열은 읽기 전용 배열처럼 나타난다. 대괄호([]) 를 사용해서 접근할 수 있지만 값은 바꿀 수 없다. 
    2. push(), sort(), reverse(), splice()는 배열을 직접 수정하므로 문자열에서는 사용할 수 없다. 

## 8. 함수

1. 함수 호출에는 parameter 이외에 호출 컨텍스트가 포함되는데, this 가 호출 컨텍스트이다. 

2. 어떤 객에의 프로퍼티로 할당된 함수를 메서드라고 한다. 

3. 자바스크립트는 nested subprogram 구성이 가능하다 즉, 함수 안에 함수를 정의해서 사용할 수 있다. 

4. 함수 정의

   1. 함수는 function 키워드에 의해서 정의되며 function 키워드는 함수 표현식 또는 함수 선언문에서 사용된다. 

5. 함수 호출

   1. 일반적인 호출
   2. 메서드 호출
   3. 생성자 호출
   4. 간접 호출
      1. 자바스크립트의 함수는 객체이므로 함수에도 메서드가 존재한다. 
      2. 이 메서드중 call(), apply()는 함수를 간접적으로 호출한다. 

6. 함수 전달인자와 매개변수

   1. 정의된 parameter보다 적은 갯수가 넘어오면, 나머지는 undefined로 간주된다. 

   2. 전달 인자의 갯수보다 더 많은 인자가 넘어올 경우 arguments객체를 통해 참조가 가능하다. 

      1. arguments 객체는 유사 배열 객체

      2. ````javascript
         function f(a, b, c){
           var len = arguments.length;
           for(var i = 0; i<len; ++i){
             console.log(arguments[i]) // 1, 2, 3, 4, 5, 6
           }
           return a+b+c;
         }
         
         var a = f(1, 2, 3, 4, 5, 6);
         
         console.log(a); // 6
         ````

7. 값으로서의 함수

   1. 자바스크립트 함수는 값이다. 즉 변수에 할당될 수 있고 객체의 프로퍼티나 배열 원소로 저장될 수 있으며 다른 함수의 인자로도 전달될 수 있으며 기타 여러 방식으로 사용될 수 있다는 뜻이다. 

   2. 자신만의 함수 프로퍼티 정의하기 

      1. ```javascript
         function factorial(n){
           if(isFinite(n) && n>0 && n==Math.round(n)){
             if(!(n in factorial))
               factorial[n] = n*factorial(n-1);
             return factorial[n]
           }
           else return NaN
         }
         factorial[1] = 1;
         
         //앞서 계산한 결과를 캐시하도록 자신의 프로퍼티를 사용하는 함수
         ```

8. 네임스페이스로서의 함수

   1. 자바스크립트는 함수단위 유효범위를 가진다. 

9. 클로저

   1. 두둥등장

   2. 자바스크립트는 lexical scoping (어휘적 유효범위)를 사용한다. 함수를 호출하는 시점에서의 변수 유효범위가 아닌 함수가 정의된 시점에서의 유효범위를 사용하여 함수가 사용된다는 뜻.

   3. 함수 객체와 함수의 변수가 해석되는 유효범위(변수 바인딩의 집합)를 아울러 컴퓨터 과학 문헌에서는 클로저 라고 부른다.

   4. 자바스크립트 함수는 클로저이다. 함수는 객체이고 함수 자신과 관련된 유효범위 체인을 가지고 있기 때문이다. 

   5. ````javascript
      var scope = "global";
      function checkscope(){
        var scope = "local";
        function f(){return scope;}
        return f();
      }
      checkscope(); // local
      ````

      ````javascript
      var scope = "global";
      function checkscope(){
        var scope = "local";
        function f(){return scope;}
        return f;
      }
      checkscope()(); // local
      ````

      클로저는 자신을 정의한 바깥쪽 함수에 바인딩된 지역 변수를 포착한다. 

   6. 

      ````javascript
      function constfuncs() {
          var funcs = [];
          for(var i = 0; i < 10; i++){
            funcs[i] = function(){return i};
          }
          return funcs;
      }
      
      var funcs = constfuncs();
      funcs[5]()         // 10이 반환된다. 클로저는 자신이 선언된 어휘적 환경을 기억한다. 즉, for문은 i가 10이 되면 종료되고, 생성된 10개의 클로저는 i = 10의 값을 기억한다.
      
      
      
      function constfuncs() {
          var funcs = [];
          for(var i = 0; i < 10; i++)(function (j){
            funcs[j] = function(){
              return j
            }
          })(i);
          return funcs;
      }
      
      var funcs = constfuncs();
      funcs[5]()         // 5가 반환된다. 클로저는 자신이 선언된 어휘적 환경을 기억한다. 익명함수를 통해서 감싸져있는 클로저는 자신이 선언된 어휘적 환경 즉, j값을 기억하고 5를 반환한다. 
      									 
      ````

   7. 클로저를 작성할때 주의해야할 사항은, this 는 자바스크립트 키워드이지 변수가 아니다. 따라서 모든 함수 호출에는 this 값이 있고, 바깥쪽 함수가 this 값을 별도의 변수로 저장하지 않으면 클로저는 바깥족 함수의 this값에 접근할 수 없다. 

10. 함수, 프로퍼티, 메서드 생성자

    1. call(), apply() 메서드
       1. 어떤 함수를 다른 객체의 메서드처럼 간접적으로 호출할 수 있도록 한다. 
       2. 엄격 모드에서 call(), apply()의 첫 번째 인자는 함수 내에서 this의 값이 되는데, 그 값이 원시 값, null, undefined 무엇이든 상관없다. 
    2. 호출 가능한 객체
       1. 모든 함수는 호출 가능한 객체지만, 모든 객체가 호출 가능한 함수는 아니다. 

11. 함수형 프로그래밍

    1. 함수로 배열 처리하기 ex)

       1. ````javascript
          var data = [1,1,3,5,5];
          var total = 0;
          
          for(var i = 0 ; i < data.length ; total+=data[i++]);
          var mean = total/data.length;
          
          total = 0;
          for(var i =0 ; i<data.length ; i++){
            var deviation = data[i] - mean;
            total+= deviation * deviation;
          }
          var standard_deviation = Math.sqrt(total/(data.length-1));
          
          
          표준편차를 구하는 위 코드를 아래처럼 바꿀 수 있다. 
          
          
          var sum = function(x, y){return x+y;}
          var square = function(x){return x*x;}
          
          var data = [1,1,3,5,5]
          var mean = data.reduce(sum)/data.length;
          var deviations = data.map(function(x){return x-mean;})
          var standard_deviation = Math.sqrt(deviations.map(square).reduce(sum)/(data.length-1))
          ````

(내용 더 추가할 예정)

## 9. 클래스와 모듈

1. 클래스와 프로토타입
   1. 자바스크립트 클래스는 같은 프로토타입 객체로부터 프로퍼티를 상속받은 객체의 집합이다. 따라서 프로토타입 객체는 클래스의 핵심이다. 
2. 클래스와 생성자
   1. 생성자는 새로 생성된 객체를 초기화하는 용도로 사용되는 함수다.
   2. 생성자는 new 키워드를 사용해서 호출한다.
   3. 생성자 호출의 핵심적인 특징은 생성자의 prototype 프로퍼티가 새 객체의 프로토타입으로 사용된다는 것이다. 즉, 같은 생성자를 통해 생성된 객체는 같은 객체를 상속하고, 같은 클래스의 멤버임을 뜻한다. 
   4. 
