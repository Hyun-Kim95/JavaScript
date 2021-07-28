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
  * 증감 연산자
