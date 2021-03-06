TCP/IP 연결인 경우에는 기본적으로 연결을 유지한다.

그렇기 때문에 다른 클라이언트와도 새로 연결을 해도 기본 연결은 계속 유지한다.

계속 서버 자원 소모된다.




## 비연결성

요청에 대한 응답만 하고  서버는 연결 유지하지 않는다면,

최소한의 자원으로 서버 유지가 가능하다.


- HTTP는 기본이 연결을 유지하지 않는 모델이다.
- 초 단위의 이하의 빠른 속도로 응답
- 서버 자원을 매우 효율적으로 사용할 수 있다.

### 한계

- TCP/IP 연결을 새로 맺어야 한다. - 3 way handshake 시간이 다시 추가된다.
- 웹 브라우저로 사이트를 요청하면 수 많은 자원이 함께 다운로드하는데 연결을 끊고 다시 받으면 비효율적이다.

### 극복

- 현재는 **HTTP 지속 연결 (Persistent Connections)**로 문제 해
- HTTP/2, HTTP/3에서 더 많이 최적화되었다.

- **HTTP 초기 - 연결하고 바로 종료**


- **HTTP 지속 연결 (Persistent Connections)**

  **: HTTP/1.0에서 TCP 연결문제 해결을 위해 등장한 기술**

    - **지속연결의 특징은 어느 한쪽에 명시적으로 연결을 종료하지 않으면 TCP 연결을 계속 유지한다.**
    - 지속연결의 이점은 TCP 커넥션의 연결과 종료를 반복되는 오버헤드를 줄여주어 서버 부담이 줄어든다.
    - 오버헤드를 줄인만큼 Request/Response가 빨라진다.
    - HTTP의 default mode는 파이프라이닝을 이용한 지속연결이고, 비지속 연결은 TCP연결이 다른 객체를 전송하기 위해 유지 되지 않는 연결방식.
        - 즉 한개의 TCP연결은 하나의 요청메시지와 하나의 응답메시지만 전송가능
        - 그래서 웹페이지에 다양한 객체가 포함되어 있다면 객체의 수만큼 TCP연결이 필요함.
        - 즉 사용자수만큼 서버의 쓰레드 생성이 필요한데 서버 동시접속자 10만명이라면, 서버는 10만개의 쓰레드가 필요함
    - **지속연결은 서버가 클라이언트의 요청의 대해서 응답한 후 TCP연결을 유지하는 방식으로, 같은 클라이언트-서버간의 요청-응답이 동일한 TCP연결을 통해 이루어지는 연결방식.**

### 스테이스리스한 방식으로 설계해야한다.

서버 개발자들이 어려워하는 업무
- 같은 시간에 딱 맞추어 발생하는 대용량 트래픽
    - ex) 선착순 이벤트, 명절 KTX 예약, 학과 수업 등록
    - ex) 저녁 7시에 선착순 1000명 치킨 할인 이벤트 → 수만명 동시 요청
        - 해결 예시) 정적인 페이지를 만들어서 한번은 거기서 텀을 주도록 해서 유도하는 방법도 있고 등등.,,,