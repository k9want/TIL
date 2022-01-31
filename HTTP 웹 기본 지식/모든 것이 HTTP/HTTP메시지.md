
**HTTP 요청 메시지와 응답 메시지는 다르다.**


### HTTP 메시지 구조

우선 HTTP 메시지 구조를 보면



- **시작라인**
- **헤더**
- **공백라인 (공백 무조건 있어야한다)**
- **message body**

## 시작 라인

### **요청 메시지**


시작라인은 크게 request-line / status- line으로 되어있다.

**요청 메시지에서는  request-line 이다.**

**request-line = method  request-tareget HTTP-version**

- HTTP 메서드 ( 조회 : GET)
    - 종류 : GET, POST, PUT, DELETE
    - 서버가 수행해야 할 동작 지정
        - GET : 리소스 조회
        - POST : 요청 내역 처리


- 요청 대상 ( /search?q=hi)

  보통 절대경로로 시작해서 쿼리를 합친다.


- HTTP Version



### 응답 메시지


응답은 status-line이다

**status=line = HTTP-version  status-code  reason-pharse**

- HTTP 버전
- HTTP 상태 코드(status-code) : 요청 성공, 실패를 나타낸다.
    - 200 : 성공
    - 400 : 클라이언트 요청 오류
    - 500 : 서버 내부 오류
- 이유 문구 : 사람이 이해할 수 있는 짧은 상태 코드 설명 글

## HTTP 헤더


header-field = field-name “:” OWS(띄어쓰기 허용) field-value OWS

file-name은 대소문자 구문 없다.

### HTTP 헤더 (용도)

- HTTP 전송에 필요한 모든 부가정보가 다 들어있다.
- 메시지 바디의 내용, 크기, 압축, 인증, 캐시 관리 정보 등등...


## HTTP 메시지 바디

### 용도

- 실제 전송할 데이터가 들어있다. (byte로 표현할 수 있는 모든 데이터 전송가능하다.)

