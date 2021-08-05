* 주석
  * `<!--주석내용-->`
  * // 한 줄 주석
  * /* 여러 줄 주석 */ 

* 출력
  * alert('안녕')
    * 경고창을 출력
  * console.log('안녕')
    * 콘솔에 출력

* 문자열
  * 따옴표로 감싸면 됨(큰따옴표, 작은따옴표 구분 안함)
  * 문자열 안에 문자열을 입력할 때 따옴표 종류를 다르게 해주거나, 역슬래시를 붙혀서 만듬
  * 처리
    * 문자열 연결 연산: 문자열 + 문자열
    * 문자 선택 연산: 문자열[인덱스] -> 문자 하나
    * 문자열의 길이: 문자열.length -> 문자 개수
  
* 숫자
  * 숫자로 시작하는 모든 것을 숫자로 인식함

* 불

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

* typeof
  * 대상의 타입을 문자열로 출력
  * 예제
    * typeof(2)
  
* 템플릿 문자열
  * 표현식을 내부에 넣을 수 있게 만든 것
  * \`17+23의 값은 ${17+23}입니다.\`
    * 역틱으로 만듬
  * 기존 표현 방식
    * '17+23의 값은 ' + (17+23) + '입니다.'
  
* 상수와 변수

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
  
* 문자열 입력: prompt()
  * prompt("메시지", "디폴트 값")
  * 이런 식의 창이 뜨고 확인을 누르면 콘솔에서 적어준 값을 확인 가능
  * ![prompt](https://user-images.githubusercontent.com/75933619/127536715-eb796945-5f39-4265-9afc-0cc5dc7a85f7.png)
  * 문자열로 리턴
  
* 불 입력: confirm()
  * const b = confirm("메시지")
  * 메시지 라고 적힌 창이 뜨고 확인을 누르면 true를 취소를 누르면 false를 리턴

* 자료형 변환

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
  
* 배열

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
  
* 스택(stack)

  * 기본 자료형의 값과 복합 자료형의 주소 등을 저장하는 메모리 공간
  * 잘 쌓는 공간

* 힙(heap)

  * 복합 자료형의 값을 저장하는 메모리 공간
  * 대충 큰 것들을 던져서 쌓은 공간

* 레퍼런스한다

  * 스택의 주소가 힙의 자료를 가리키는 것

* 레퍼런스 변수

  * 스택에 저장된 것 중에 주소가 저장된 변수

* const
  * 스택의 값 변경 불가
    * 스택에는 주소가 저장 돼있고 힙에 값이 저장돼있는 복합 자료형은 변경 가능( 배열 )

* 반복문
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

* 함수

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

* API

  * Application Programming Interface
    * 애플리케이션 프로그램을 만들 때의 약속

* 나머지 매개변수

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

* 가독성의 중요성

  * 기업 입장의 비용 절감
  * 프로그램이 너무 복잡해져서
  * 지원 도구의 활용

* 기본 매개변수

  ```javascript
  const isLeapYear = function(연도 = new Date().getFullYear()){	// 기본 매개변수
      console.log(`연도: ${연도}`)
      return (연도 % 4 === 0) && (연도 % 100 !== 0) || (연도 % 400 === 0)
  }
  
  console.log(isLeapYear())	// 매개변수를 안주면 올해가 윤년인지 확인 가능
  ```

  
