# 협상 (Content negotiation)

### 클라이언트가 선호하는 표현 요청


클라이언트-서버가 있을 때 클라이언트가 원하는 우선순위대로 최대한 노력해서 표현 데이터를 만들어줄게~ 이런 의미로 생각하자

- **Accept: 클라이언트가 선호하는 미디어 타입 전달**
- **Accept-Charset: 클라이언트가 선호하는 문자 인코딩**
- **Accept-Encoding: 클라이언트가 선호하는 압축 인코딩**
- **Accept-Language: 클라이언트가 선호하는 자연 언어**

협상 헤더는 요청시에만 사용한다.

### Accept-Language 적용 전


내가 한국어 브라우저를 사용한다고 했을 때

외국의 이벤트사이트로 들어갔는데 이 서버는 다중 언어를 지원한다. (기본 영어, 한국어 지원하는 경우)

클라이언트가 요청을 할 때 서버는 기본값인 영어로 응답해준다.

### Content negotiation (Accept-Language) 적용하면


클라이언트가 서버에 요청을 보낼때 Accept-Language: ko를 포함해서 보내면 한국어를 지원하는 서버라면 실제 메시지 바디에 한국어를 적용해서 응답해준다.

### Accept-Language 복잡한 예시


다중 언어 지원 서버인데 기본 독일어, 영어만 지원하는 경우

클라이언트는 한국어를 원하는데 서버에서 한국어지원 안할 경우에는 독일어보단 영어를 원한다고 했을 때 서버는 클라이언트가 독일어보다 영어를 원해도 기본 언어인 독일어를 보낸다.

이를 해결위해 **우선순위가 필요하다**

### 1. 협상과 우선순위1 - Quality Values(q)


- Quality Values(q) 값을 사용
- 0~1, 클수록 높은 우선순위를 뜻하고 생략하면 1이다.
- ex) Accept-Language: ko-KR, ko;q=0.9, en-US;q=0.8,en;q=0.7

Accept-Language: ko-KR, ko;q=0.9, en-US;q=0.8,en;q=0.7 이렇게 해서 서버로 보내면

서버는 기본은 독일어지만 우선순위가 영어임을 알고 영어로 응답해준다.


### 2. 협상과 우선순위2 - Quality Values(q)

- 구체적인 것이 우선선택된다.
- Accept: text/*, text/plain, text/plain;format=flowed
    1. text/plain;format=flowed
    2. text/plain
    3. text/*

### 3. 협상과 우선순위3 - Quality Values(q)

- 구체적인 것을 기준으로 미디어 타입을 맞춘다.