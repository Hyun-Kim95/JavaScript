### 주석

* `<!--주석내용-->`
* // 한 줄 주석
* /* 여러 줄 주석 */ 

### 출력

* alert('안녕')
  * 경고창을 출력
* console.log('안녕')
  * 콘솔에 출력

### 문자열

* 따옴표로 감싸면 됨(큰따옴표, 작은따옴표 구분 안함)
* 문자열 안에 문자열을 입력할 때 따옴표 종류를 다르게 해주거나, 역슬래시를 붙혀서 만듬
* 처리
  * 문자열 연결 연산: 문자열 + 문자열
  * 문자 선택 연산: 문자열[인덱스] -> 문자 하나
  * 문자열의 길이: 문자열.length -> 문자 개수

### 숫자

* 숫자로 시작하는 모든 것을 숫자로 인식함

### 불

* true, false

* 비교 연산자

  | 연산자 |          설명           |
  | :----: | :---------------------: |
  |  ===   |       양쪽이 같다       |
  |  !==   |      양쪽이 다르다      |
  |   >    |     왼쪽이 더 크다      |
  |   <    |    오른쪽이 더 크다     |
  |   >=   |  왼쪽이 더 크거나 같다  |
  |   <=   | 오른쪽이 더 크거나 같다 |

  * == 랑 != 는 결과 예측이 쉽지 않고 코드에 오류가 생길 수 있으므로 사용해도는 되지만 자제됨

* 불 연산자

  * 논리 부정 연산자: !불, 단항 연산자
  * 논리 연산자
    * 논리 합 연산: ||(또는)
    * 논리 곱 연산: &&(그리고)

* 드모르간의 법칙

  * 앞에 논리 부정 연산자를 붙혔을 때 

    -> 부등식은 반대로, 논리곱 논리합 교체

  * 예제

  * !(12 <= 현재시각 && 현재시각 <= 13)

  * -> 12 > 현재시각 || 현재시각 > 13

### typeof

* 대상의 타입을 문자열로 출력
* 예제
  * typeof(2)

### 템플릿 문자열

* 표현식을 내부에 넣을 수 있게 만든 것
* \`17+23의 값은 ${17+23}입니다.\`
  * 역틱으로 만듬
* 기존 표현 방식
  * '17+23의 값은 ' + (17+23) + '입니다.'

### 상수와 변수

* 상수
  * 자료에 이름을 붙이는 것
  * const 식별자 = '자료'
  * 위 형태를 벗어나면 오류
  * 같은 이름으로 중복 선언 불가능
  * 상수는 값 변경 불가
* 변수
  * 변수 만들기
    * let 식별자
    * let 식별자 = 자료
  * 변수에 값 넣기
    * 변수 = 자료
  * 변수 사용하기
    * 변수
  * 같은 이름으로 중복 선언 불가능(콘솔 창은 편의상 오류가 발생하지 않음)
* 기본적으로 상수를 사용하고 값이 바뀔 때만 변수 사용

* 변수에 적용할 수 있는 연산자

  * 복합 대입 연산자
    * a += 100
  * 증감 연산자
    * a++

* undefined 자료형
  * 상수와 변수로 선언하지 않은 식별자
    * a의 선언 없이 typeof(a)
  * 값이 없는 변수
    * let b 후에 값 대입 없이 typeof(b)

### 문자열 입력: prompt()

* prompt("메시지", "디폴트 값")
* 이런 식의 창이 뜨고 확인을 누르면 콘솔에서 적어준 값을 확인 가능

  ![prompt](https://user-images.githubusercontent.com/75933619/127536715-eb796945-5f39-4265-9afc-0cc5dc7a85f7.png)
* 문자열로 리턴

### 불 입력: confirm()

* const b = confirm("메시지")
* 메시지 라고 적힌 창이 뜨고 확인을 누르면 true를 취소를 누르면 false를 리턴

### 자료형 변환

* Number(): 숫자로 변환
  * 숫자로 변환이 안되는 것에 사용하면 NaN : Not a Number
  * typeof(NaN) = "number"
* String(): 문자열로 변환
* Boolean(): 불로 변환
  * String(true) -> "true"
  * String(false) -> "false"
  * Number(true) -> 1
  * Number(false) -> 0
  * 다른 자료형 -> 불
    * false
      * 0, NaN, "", null, undefined
    * true
      * 나머지 전부

* 예제

  ```javascript
  let a = prompt('첫 번째 숫자를 입력해 주세요.')	// const로하면 오류
  a = Number(a)									// 상수에 값을 또 할당하면 오류라서
  
  const b = Number(prompt('두 번째 숫자를 입력해 주세요.'))	// 이렇게 한번에 하면
  // const로 선언 가능
  alert(`${a} + ${b} = ${a+b}`)
  ```

### 조건문

* if 조건문

```javascript
const date = new Date()	// 현재 날짜 관련 객체
const hours = date.getHours()	// 현시 시간을 구함
// const month = (new Date()).getMonth() + 1
// 위처럼 구할 수도 있음(월은 0~11로 나와서 +1을 적어줌)
if(hours < 10){
    alert('아침밥 먹을 시간입니다')
} else if(hours < 16){
    alert('점심밥 먹을 시간입니다')
} else{
    alert('저녁밥 먹을 시간입니다')
}
```

* switch 조건문

```javascript
const x = Number(prompt('숫자를 입력해 주세요',''))
switch(x){
    case 1:
        alert('입력한 값이 1입니다')
        break
    case 2:
        alert('입력한 값이 2입니다')
        break
    case 3:
        alert('입력한 값이 3입니다')
        break
    default:
        alert('입력한 값이 1~3이 아닙입니다')
}
```

* 조건부 연산자(삼항 연산자)

```javascript
const x = Number(prompt('숫자를 입력해주세요',''))
alert((x>=0)?'0 이상의 숫자입니다':'0보다 작은 숫자입니다')
```

* 짧은 조건문(short circuit evaluation(단락 평가))

  * 많이 안씀

    ```javascript
    alert('시작')
    true || alert('또는 연산자')	// 앞에 꺼 확인해서 true 면 뒤에꺼 확인 안함
    
    false && alert('그리고 연산자')
    alert('종료')
    // 시작
    // 종료
    ```

* 예제 문제

  ```javascript
  const rawInput = Number(prompt('태어난 해를 입력해주세요.',''))
  const year = Number(rawInput)
  
  let result1
  const e1 = year % 12
  if      (e1 === 0)  {result1 = '신'}
  else if (e1 === 1)  {result1 = '유'}
  else if (e1 === 2)  {result1 = '술'}
  else if (e1 === 3)  {result1 = '해'}
  else if (e1 === 4)  {result1 = '자'}
  else if (e1 === 5)  {result1 = '축'}
  else if (e1 === 6)  {result1 = '인'}
  else if (e1 === 7)  {result1 = '묘'}
  else if (e1 === 8)  {result1 = '진'}
  else if (e1 === 9)  {result1 = '사'}
  else if (e1 === 10)  {result1 = '오'}
  else if (e1 === 11)  {result1 = '미'}
  
  let result2
  const e2 = year % 10
  if      (e2 === 0)  {result2 = '경'}
  else if (e2 === 1)  {result2 = '신'}
  else if (e2 === 2)  {result2 = '임'}
  else if (e2 === 3)  {result2 = '계'}
  else if (e2 === 4)  {result2 = '갑'}
  else if (e2 === 5)  {result2 = '을'}
  else if (e2 === 6)  {result2 = '병'}
  else if (e2 === 7)  {result2 = '정'}
  else if (e2 === 8)  {result2 = '무'}
  else if (e2 === 9)  {result2 = '기'}
  
  alert(`${year}년은 ${result1}${result2}입니다.`)
  ```

  * 짧은 코딩

  ```javascript
  const 입력 = Number(prompt('태어난 해를 입력해주세요.','')) % 12
  const tti = '원숭이,닭,개,돼지,쥐,소,호랑이,토끼,용,뱀,말,양'.split(',')
  alert(`${tti[입력]}띠 입니다.`)
  ```

### 배열

* 생성 방법
  * const a = ['여러가지', 10, true, 1]
* 메서드
  * push(요소): 배열 뒤에 요소 추가
    * a.push(100)
  * splice(인덱스, 0, 요소): 배열 중간에 요소 추가
    * a.splice(1, 0, '추가'): 1번 인덱스에 '추가'라는 요소를 추가
  * splice(인덱스, 1): 인덱스로 배열의 요소 제거
    * a.splice(0, 1): 0번 인덱스 삭제
  * indexof(요소): 배열 내부에서 값의 위치 찾기
    * a.indexof('안녕'): 있으면 위치 반환, 없으면 -1 반환
  * indexof() + splice() 활용: 값으로 배열의 요소 제거
    * a.splice(a.indexOf('안녕'), 1)

### 스택(stack)

* 기본 자료형의 값과 복합 자료형의 주소 등을 저장하는 메모리 공간
* 잘 쌓는 공간

### 힙(heap)

* 복합 자료형의 값을 저장하는 메모리 공간
* 대충 큰 것들을 던져서 쌓은 공간
* 레퍼런스한다

  * 스택의 주소가 힙의 자료를 가리키는 것

* 레퍼런스 변수

  * 스택에 저장된 것 중에 주소가 저장된 변수

* const
  * 스택의 값 변경 불가
    * 스택에는 주소가 저장 돼있고 힙에 값이 저장돼있는 복합 자료형은 변경 가능( 배열 )

### 반복문

* 배열 등과 함께 사용(const 사용)
  * forof
    * for(const **요소** of 배열) { }
  * forin
    * for(const **인덱스** in 배열) { }
  
* 그냥 범용적으로 사용(let 사용)
  * for
    * for(let i = 0; i < 5 ; i++) { }
  
* while

  ```javascript
  let i = 0
  while (confirm('계속 진행하시겠습니까?')){
      alert(`${i}번째 반복입니다.`)
      i++
  }
  ```

* 별 출력 예제

  ```javascript
  let output = ''
  for (let i = 0; i < 9; i++) {
      if (i < 5) {
          for (let k = 0; k < 4 - i; k++) {
              output += ' '
          }
          for (let j = 0; j < i*2+1; j++) {
              output += '*'
          }
      } else{
          for (let k = 0; k < i - 4; k++) {
              output += ' '
          }
          for (let j = 0; j < (9-i)*2-1 ; j++) {
              output += '*'
          }
      }
      output += '\n'
  }
  console.log(output)
  // 결과
  //    *
  //   ***
  //  *****
  // *******
  //*********
  // *******
  //  *****
  //   ***
  //    *
  ```

* 햇갈린 예제

  ```javascript
  const array = [1,2,3,4]
  console.log(array.push(8))
  // 결과
  // 5
  // array.push는 파괴적 함수, 새로운 배열인 [1,2,3,4,8]을 출력하지 않음, 배열의 요소 개수를 반환
  ```

### 함수

* 사용 이유

  * 코드의 재사용

* 만드는 법

  * 익명 함수(보통 이걸로 만듬)

    * const f = function (매개변수) {

      ​	return 리턴값

      }

  * 선언적 함수(알아는 두기)

    * function f (매개변수){

      ​	return 리턴값

      }

* 호출

  * f(매개변수)

* 점프

  * 호출 위치에서 함수 본문으로 이동하는 것

* 리턴

  * 함수 본문에서 호출 위치로 나오는 것

* 예제

  * 윤년찾기

    ```javascript
    const f = function(year){
    	return year % 400 === 0 || (year % 4 === 0 && year % 100 !== 0)
    }
    const a = prompt('해를 입력하세요','')
    console.log(`${a}년은 윤년인가요? === ${f(a)}`)
    ```

  * 최대, 최소 구하기

    ```javascript
    const min = function(x){
        let a = x[0]
        for (const value of x) {
            if(a > value){
                a = value
            }
        }
        return a
    }
    const max = function(x){
        let a = x[0]
        for (const value of x) {
            if(a < value){
                a = value
            }
        }
        return a
    }
    const a = [52,273,32,103,275,24,57]
    console.log(`배열의 최소값은 ${min(a)}`)
    console.log(`배열의 최대값은 ${max(a)}`)
    ```

### API

* Application Programming Interface
  * 애플리케이션 프로그램을 만들 때의 약속

### 나머지 매개변수

```javascript
const 함수 = function(a,b,...매개변수){
    console.log(a,b,매개변수)
}

함수()
함수(1)
함수(1,2)
함수(1,2,3)
함수(1,2,3,4)	// 이렇게 사용하는 매개변수
```

* 일반 매개변수와 같이 사용할 수 있음
* 무조건 가장 뒤쪽에 나와야함
* 나머지 매개변수는 배열로 들어감
* 일반 매개변수와 같이 사용하는데 그 갯수를 못맞추면 undefind 나옴

* 전개 연산자: 함수 호출

  ```javascript
  const 함수 = function(a,b,c){
      console.log(a,b,c)
  }
  
  const a = [1,2,3]
  함수(a[0],a[1],a[2])
  함수(...a)	// 위 아래는 완전히 같은 코드
  ```

### 가독성의 중요성

* 기업 입장의 비용 절감
* 프로그램이 너무 복잡해져서
* 지원 도구의 활용

### 기본 매개변수

```javascript
const isLeapYear = function(연도 = new Date().getFullYear()){	// 기본 매개변수
    console.log(`연도: ${연도}`)
    return (연도 % 4 === 0) && (연도 % 100 !== 0) || (연도 % 400 === 0)
}

console.log(isLeapYear())	// 매개변수를 안주면 올해가 윤년인지 확인 가능
```

### 콜백함수

* 함수내부에서 함수 호출

* forEach

  ```javascript
  const 배열 = [273,52,103,32,57]
  배열.forEach(function(value,index,array){
      consol.log(value,index,array)
  })
  // 배열의 값이 하나씩 함수로 들어감(array는 생략 가능(잘 안씀))
  ```

* filter

  ```javascript
  let 배열 = [273,52,103,32,57]
  배열 = 배열.filter(function (value,index){	// 비파괴적 함수라서
      return value % 2 === 0	// true , false
  })
  console.log(배열)
  ```

* map

  ```javascript
  let 배열 = [273,52,103,32,57]
  배열 = 배열.map(function (value,index){	// 새로운 배열을 만듬
      return value + "!!"	
  })
  console.log(배열)
  ```


### 화살표 함수

* (매개변수) => {본문}
* 함수가 리턴 하나뿐인 함수이면 return 과 중괄호도 생략 가능

```javascript
let 배열 = [273,52,103,32,57]
배열 = 배열.map((value,index) => value + "!!")
console.log(배열)
```

### 타이머 함수

* setTimeout()

  * 일정 시간 후에 실행

    ```javascript
    setTimeout(function(){
        console.log('setTimeout 함수 입니다!')
    },1000)	// 1초 후에 함수 실행
    ```

* setInterval()

  * 일정 시간마다 실행

    ```javascript
    setInterval(function(){
        console.log('setInterval 함수 입니다!')
    },1000)
    ```

* clearTimeout(), clearInterval()

  * 타이머 함수의 취소

    ```javascript
    const a = setTimeout(function(){
        console.log('setTimeout 함수 입니다!')
    },1000)
    
    clearTimeout(a)
    ```

### 즉시 호출 함수

* 함수를 만들자마자 호출

* 상수명 변수명 등의 중복 가능성을 없애줌

  ```javascript
  (function(){
      
  })()
  ```

### 엄격모드

* 명확하게 선언해야 실행되도록 제한하는 기능

  ```html
  <script>
  	'use strict'	// 이걸 처음에 적어주면 됨
      a = 10			// 원래라면 오류없이 실행됨
      b = 20			// 엄격모드를 이용하면 오류 발생시켜서 const나 let을 붙혀야 실행됨
      console.log(a,b)
  </script>
  <script>
  	(function(){		// 다른 스크립트부분에 영향을 미치면 문제 발생 가능성이 있어서
          'use strict'	// 이렇게 즉시호출 함수 내부에서만 엄격모드를 사용하도록 많이 씀
          
      })()
  </script>
  ```

### 객체

* 키와 값을 가짐

  ```javascript
  const dog = {			 // 객체
        name: '구름',		// 키: name, 값: '구름'
        age: 7,
        bark: function () { // 함수도 속성으로 들어올 수 있음(객체안에 있는 함수 -> 메서드)
          console.log(`${dog.name}이/가 짖습니다!`)
          console.log(`${this.name}이/가 짖습니다!`)	// this 자기자신을 가리킴
        },
        sleep: () => {
          console.log(`${dog.name}이/가 잡니다!`)	// 화살표함수는 this 사용불가
        }
      }
  dog.bark()
  dog.sleep()
  console.log(dog.name)	// 이런식으로 접근 가능
  console.log(dog['name'])
  dog.name = '별'			// 변경 가능
  ```


### 키와 값을 처음 만들 때 같이 만들면 정적으로 생성, 나중에 만들면 동적으로 생성한다고 함

* 동적으로 속성 추가
  * 객체.속성 = 값
  * 객체['속성'] = 값
* 동적으로 속성 제거
  * delete 객체.속성

### 기본 자료형 -> 스택에 값을 저장

* 숫자, 문자열, 불

### 객체 자료형 -> 스택과 힙을 연결하여 속성과 메서드를 가질 수 있음

* 함수, 배열, 객체

### 자료형 확인하기

* const a = [ ]
* typeof(a) -> "object"
  * 객체라는 것 까지만 확인 가능
* Array.isArrsy(a) -> true
  * 배열이면 true 리턴
* const b = () => {}
* typeof(b) -> "function"
  * 함수는 그냥 함수라고 나옴
  * typeof(b) === 'function' -> true

#### 함수를 객체처럼 사용할 때 그 함수는 일급 객체(first-class object)라고 함

### 여러가지 메서드

* Number.toFixed()

  * 소수점 자르기(문자열 형태로 반환)

    ```javascript
    const a = 123.45678
    a.toFixed(2)	// "123.45"
    a.toFixed(3)	// "123.456"
    ```

* Number.isNaN()
  * NaN이 들어오면 true 출력

* 문자열.trim()
  * 앞 뒤 공백 제거

* 문자열.split(' ')
  * 문자열을 잘라서 배열로 만듬

* Math 객체
  * 여러가지 많음
  * Math.floor(Math.random() * 50)
    * 0~1 사이의 랜덤에 50을 곱하고 소수점 밑을 버려서 랜덤 정수를 만듬

### 외부 스크립트 파일 읽어들이기

* html 해드 부분에 <script\>내용</script\> 이렇게 하지 않고 js파일을 만들어서 거기에 코딩한 후

  <script src="b.js"\></script\> 이런 식으로 사용 가능

### Lodash 라이브러리

* https://lodash.com
* 유용한 함수가 많으므로 심심할 때 읽어보기
* 다운로드 부분에 파일을 다운 받아서 쓰거나 링크를 복사해서 사용 가능(둘 중 아무거나 해도 됨)
* 다운로드
  * Full build 클릭
  * 나온 화면에서 우 클릭 다른 이름으로 저장 선택
  * 사용할 폴더에 저장

* 링크 복사
  * CDN copies 클릭
    * CDN : 콘텐츠 전송 네트워크라는 의미
  * 중간 lodash 오른쪽에 Copy to Clipboard 클릭 후 Copy URL 선택
  * 복사된 링크를 스크립트의 src 부분에 넣어주면 사용 가능

* 사용법은 위쪽 Documentation 클릭하면 나옴
  * _.sortBy() : 정렬해줌
    * const output = _.sortBy(books, ['publisher','price'])
      * books 를 publisher를 기준으로 정렬한 후 price를 기준으로 정렬(하나만 써도 됨)

### 여러가지 라이브러리

* Luxon : 시간 관련
* Handsontable : 엑셀과 같은 스프레드시트를 만듬
* D3.js : 데이터 시각화

* Chart.js : 간단한 그래프 출력
* three.js : 3D 그래픽 다루기

### 객체의 기본 속성

```javascript
const test = function(object){
    return `${object.name} : ${object.age} : ${object.color} : ${object.status}`
}
console.log(test{
            name: '구름',
            age: 7,
            color: '갈색'
            })
```

* 위 상태에서 기본 매개변수 지정 방법

  * 과거(~ing)

    * object.status = object.status !== undefinde ? object.status : '이상 없음'
    * object.status = object.status ? object.status : '이상 없음'
    * object.status = object.status || '이상 없음'

  * 현대

    * object = { status: '이상 없음', ...object }

    * fun = function({name, age, color, status = '이상 없음'}) {

      ​	return \`${name} : ${age} : ${color} : ${status} `

      }

      밑에처럼 줄 바꿈 하여 가장 많이 사용함

      ```javascript
      fun = function({
          name,
          age,
          color,
          status = '이상 없음'
      }) {
      	return `${name} : ${age} : ${color} : ${status}`
      }
      ```

* 객체 속성 일괄 추출

  ```javascript
  const test = function(object) {
  	const { name, age, color, status } = { status: '이상 없음', ...object }
  	return `${name} : ${age} : ${color} : ${status}`
  }
  console.log(test({
      name: '구름',
      age: '7',
      color: '갈색'
  }))
  ```

  * 이렇게 사용하면 object.name 식으로 사용하지 않아도 됨(많이 사용함, nodejs 에서 특히 많이 사용)

### 라이브 서버

* 변경 사항을 바로 확인 가능

* 설치

  * vscode 의 왼쪽 확장 클릭 -> live server 검색 -> 설치 -> vscode 다시 시작

* 사용

  * 왼쪽 위 파일의 폴더 열기 클릭 -> 폴더 선택 클릭 -> 코드 작성 후

    -> 오른쪽 밑 Go Live 클릭 or `Alt`+`L` + `Alt`+`o`

    -> 오른쪽 밑에 버튼 다시 눌러서 종료

### DOMContentLoaded 이벤트

* DOM(Document Object Model)
  * 문서 객체 모델
    * HTML 요소를 조작하는 객체들의 집합

* head 부분에서 문서 객체를 조작 가능하게 하는 기능
* document.querySelector()
  * 여러가지 선택자를 읽어 들여서 조작 가능
  * 처음에 선택된 하나만 적용(여러개의 같은 이름이 있어도 처음것만 적용됨)
* document.querySelectorAll()
  * 같은 이름 여러개 한번에 적용 가능(보통 for문과 같이 사용)

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Document</title>
  <script>
    document.addEventListener('DOMContentLoaded', () => {
      // 태그 선택자
      document.querySelector('h1').style.color='red'
      // 아이디 선택자
      document.querySelector('#header').style.backgroundColor = 'orange'
      // 클래스 선택자
      document.querySelector('.center.head').style.textAlign = 'center'
      // 속성 선택자
      document.querySelector('[type=text]').style.borderRadius = '10px'
      // 후손 선택자
      document.querySelector('body input').style.backgroundColor = 'blue'
      // querySelectorAll()
      for(const element of document.querySelectorAll('input')){
        element.style.backgroundColor = 'red'
      }
    })
  </script>
</head>
<body>
  <h1 id="header" class="center head">안녕하세요</h1>
  <input type="text">
  <input>
</body>
</html>
```

* 문서 객체 조작

  * 글자 조작
    * querySelector로 읽어 들여서 값을 넣어주거나 추출 가능
      * textContent
        * 텍스트 형식으로 추출이나 변경
        * \<br> 을 사용하면 텍스트로 인식
      * innerHTML
        * \<br> 을 줄바꿈으로 인식
        * 보안 문제로 많이는 사용 안함
    
  * 속성 조작
    * const img = document.querySelector('img')
    * 표준 속성은 img.src = 'http://placekitten.com/200/200' 이런식으로 사용 가능
    * 표준 속성이 아닌값은
      * img.setAttribute('src','http://placekitten.com/200/200')
      * img.getAttribute('src')

  * 스타일 조작

    ```javascript
    const divs = document.querySelectorAll('div')
    div.forEach((div,key) => {
        div.style.backgroundColor = `rgb(${key*25}, ${key*25}, ${key*25})`
        div.style.height = '10px'
    })
    ```

### 문서 객체

* 생성

  * 밑에 순서대로 생성 가능

    ```javascript
    const header = document.createElement('h1')
    header.textContent = 'createElement로 만든 태그'
    header.style.color = 'red'
    // 위 코드는 만들어 주기만 하는 코드, 밑에서 적용시킴
    const body = document.querySelector('body')
    body.appendChild(header) // body 태그에 해더를 붙힘
    ```

* 제거

  * 위 코드 마지막에 body.removeChild(header)
  * header.parentNode.removeChild(header)
    * 위 코드보다는 이 코드를 더 많이 사용함

* 이동

  * appendChild( ) 이용

### 타이머 관련 테크닉

* 첫 번째 테크닉

```javascript
document.addEventListener('DOMContentLoaded', () => {
      const header = document.createElement('h2')
      header.textContent = '안녕하세요'

      const first = document.querySelector('.first')
      const second = document.querySelector('.second')
      first.appendChild(header)
      
      const toFirst = () => {
        first.appendChild(header)
        setTimeout(toSecond,1000)
      }
      const toSecond = () => {
        second.appendChild(header)
        setTimeout(toFirst,1000)
      }
      toFirst()	// 여기서 스타트를 끊고 1초마다 header가 first 클래스와 second 클래스를 이동
})
```

* 두 번째 테크닉

```javascript
document.addEventListener('DOMContentLoaded', () => {
      const header = document.createElement('h2')
      header.textContent = '안녕하세요'

      const array = [
        document.querySelector('.first'),
        document.querySelector('.second')
      ]
      let 카운터 = 0
      const fun = () => {
        array[카운터%2].appendChild(header)
        카운터++
      }
      fun()			// 일단 한번 실행해 줘야 위 코드처럼 처음에 first클래스에 붙어서 시작함
      setInterval(fun,1000)	// 바로 윗줄 없으면 1초 뒤부터 붙어서 이동 시작
})
```

* 응용

  ```javascript
  document.addEventListener('DOMContentLoaded', () => {
        const header = document.createElement('h2')
        header.textContent = '안녕하세요'
  
        const array = [
          document.querySelector('.first'),
          document.querySelector('.second')
        ]
        let 카운터 = 0
        const fun = () => {
          array[카운터%2].appendChild(header)
          카운터++
          setTimeout(fun,1000)	// 이걸 여기다 넣어도 같은 기능
        }
        fun()
  })
  ```

### 문서 객체 이벤트 기본

* document.on으로 시작하는 것들

* 이벤트 연결

  * connectButton.addEventListener('click', () => {

       header.addEventListener('click', listener)

      })

* 이벤트 해제

  * disconnectButton.addEventListener('click', () => {

       header.removeEventListener('click', listener)

      })

* 예제

  ```html
  <!DOCTYPE html>
  <html>
  <head>
    <meta charset="UTF-8">
    <title>Document</title>
  </head>
  <body>
    <script>
      let counter = 0										// 클릭 횟수 체크
      const listener = () => {
        header.textContent = `클릭 횟수: ${++counter}`  	// 클릭 횟수 출력
      }
  
      const header = document.createElement('h1')			// h1 태그 생성
      header.style.userSelect = 'none'					// h1 태그 선택시 효과없음
      header.textContent = `클릭 횟수: 0`					// h1 태그 초기 출력문자
  
      const p = document.createElement('p')				// p태그 생성
      p.style.userSelect = 'none'							// p태그 선택시 효과 없음
      p.textContent = `이벤트 연결 상태: 해제`					// p 태그 초기 문자
  
      const connectButton = document.createElement('button')	// button 태그 생성
      connectButton.textContent = '이벤트 연결 버튼'				// button 이름
      connectButton.addEventListener('click', () => {			// button 클릭시
        header.addEventListener('click', listener)			// listener 실행
        p.textContent = '이벤트 연결 상태: 연결'				// p 태그 문자 변경
      })
  
      const disconnectButton = document.createElement('button')	// button 태그 생성
      disconnectButton.textContent = '이벤트 해제 버튼'				// button 이름
      disconnectButton.addEventListener('click', () => {			// button 클릭시
        header.removeEventListener('click', listener)	// 클릭시 listener에 연결된 이벤트해제
        p.textContent = '이벤트 연결 상태: 해제'			// p 태그 문자 변경
      })
  
      document.body.appendChild(header)			// 각 태그들을 순서에 맞게 body에 붙힘
      document.body.appendChild(connectButton)
      document.body.appendChild(disconnectButton)
      document.body.appendChild(p)
    </script>
  </body>
  </html>
  ```

### 키보드 이벤트

* keyup, keydown, keypress 가 있음
  * keypress는 아시아계 문자에는 잘 안될 때가 많아서 잘 사용 안함
* document.addEventListener('keydown' , (event) => { }
  * 키를 누르는 이벤트
  * event에는 누른 키에 대한 정보가 들어감

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <script>
    document.addEventListener('DOMContentLoaded',()=>{
      const h1 = document.querySelector('h1')				// h1 태그 연결
      const textarea = document.querySelector('textarea')	// textarea 태그 연결
      textarea.addEventListener('keyup',()=>{				// textarea에 keyup 이벤트 발생
        h1.textContent = `글자 수: ${textarea.value.length}`	// 글자 수를 h1에 입력
      })
    })
  </script>
</head>
<body>
  <h1>글자 수: 0</h1>
  <textarea></textarea>
</body>
</html>
```

### 이벤트 발생 객체

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <script>
    document.addEventListener('DOMContentLoaded',()=>{
      const h1 = document.querySelector('h1')
      const textarea = document.querySelector('textarea')
      
      // 이벤트 발생 객체를 의미하는 세가지(많이 사용함)
      // textarea = 이벤트 발생 객체
      textarea.addEventListener('keyup',()=>{
        h1.textContent = `글자 수: ${textarea.value.length}`
      })
      // event.currentTarget = textarea = 이벤트 발생 객체	// 굳이 고르자면 얘를 기억해두면 좋음
      textarea.addEventListener('keyup',(event)=>{
        h1.textContent = `글자 수: ${event.currentTarget.value.length}`
      })
      // this = textarea = 이벤트 발생 객체, 화살표 함수 대신 function() 사용
      textarea.addEventListener('keyup',function(){
        h1.textContent = `글자 수: ${this.value.length}`
      })
        
    })
  </script>
</head>
<body>
  <h1>글자 수: 0</h1>
  <textarea></textarea>
</body>
</html>
```

### 기본 이벤트 막기

* preventDefault()

  ```html
  <!DOCTYPE html>
  <html>
  <head>
    <meta charset="UTF-8">
    <script>
      document.addEventListener('DOMContentLoaded',()=>{
        const a = document.querySelector('a')			// a태그 연결
        a.addEventListener('click',(event)=>{			// 클릭 이벤트 발생시
          event.preventDefault()						// 기본 이벤트 막음
        })
        a.addEventListener('contextmenu',(event)=>{	// 우클릭 이벤트 발생시
          event.preventDefault()						// 기본 이벤트 막음
        })
      })
    </script>
  </head>
  <body>
    <a href="https://www.naver.com">링크</a>
  </body>
  </html>
  ```

  
