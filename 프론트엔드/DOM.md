# DOM

### DOM - Document Object Model

문서객체모델 - 객체 지향 모델로써 구조화된 문서를 표현하는 방식(트리 구조)

- XML, HTML문서의 프로그래밍 인터페이스
- 문서의 구조화된 표현을 제공하여 프로그래밍 언어가 문서구조, 스타일, 내용 등을 변경할 수 있도록 한다.

### HTML DOM

- HTML 문서를 조작하고 접근하는 표준화된 방법
- 모든 HTML 요소는 HTML DOM을 통해 접근 가능하다.

### Document 객체

- 웹 페이지를 의미
- 웹 페이지에 존재하는 **HTML 요소에  접근**하려면 **반드시 Document객체부터 시작해야한다.**
- HTML 요소와 관련된 작업을 도와주는 다양한 메소드 제공
    - HTML 요소 선택
        - document.get~~~, document.querySelector~~
    - HTML 요소 생성
        - document.createElement( ) - HTML Object를 넘긴다.
        - document.write( ) - 단지 TEXT만
    - HTML 이벤트 핸들러 추가
        - 요소.onclick  =fucntion()
    - HTML 객체의 선택