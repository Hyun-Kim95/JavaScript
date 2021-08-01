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
    <script>
      let a = prompt('첫 번째 숫자를 입력해 주세요.')	// const로하면 오류
      a = Number(a)									// 상수에 값을 또 할당하면 오류라서
    
      const b = Number(prompt('두 번째 숫자를 입력해 주세요.'))	// 이렇게 한번에 하면
      														// const로 선언 가능
      alert(`${a} + ${b} = ${a+b}`)
    </script>
    ```

* if 조건문

  ```javascript
  <script>
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
  </script>
  ```

* switch 조건문

  ```javascript
  <script>
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
  </script>
  ```

* 조건부 연산자(삼항 연산자)

  ```javascript
  <script>
    const x = Number(prompt('숫자를 입력해주세요',''))
    alert((x>=0)?'0 이상의 숫자입니다':'0보다 작은 숫자입니다')
  </script>
  ```

* 짧은 조건문(short circuit evaluation(단락 평가))

  * 많이 안씀

    ```javascript
    <script>
      alert('시작')
      true || alert('또는 연산자')	// 앞에 꺼 확인해서 true 면 뒤에꺼 확인 안함
    
      false && alert('그리고 연산자')
      alert('종료')
    </script>
    // 시작
    // 종료
    ```

* 예제 문제

  ```javascript
  <script>
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
  </script>
  ```

  * 짧은 코딩

  ```javascript
  <script>
    const 입력 = Number(prompt('태어난 해를 입력해주세요.','')) % 12
    const tti = '원숭이,닭,개,돼지,쥐,소,호랑이,토끼,용,뱀,말,양'.split(',')
    alert(`${tti[입력]}띠 입니다.`)
  </script>
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
      * for(const 요소 of 배열) { }
    * forin
      * for(const 인덱스 in 배열) { }
  * 그냥 범용적으로 사용(let 사용)
    * for
      * for(let i = 0; i < 5 ; i++) { }
