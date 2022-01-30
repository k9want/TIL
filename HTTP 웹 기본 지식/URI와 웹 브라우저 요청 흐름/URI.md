## URI (Uniform Resource Identifier)

### URI, URL, URN

- **URI는 로케이터(locator) , 이름(name) 또는 둘다 추가로 분류될 수 있다.**
    

    URL - Resource Locator
    
    URN - Resource Name
    
    URN은 이름을 딱 부여하는 것 문제는 이름을 부여하면 거의 찾을 수가 없다. 
    중간에 이름을 쓰면 해당 리소스가 매핑이 되어야하는데 그러기 어렵다.
    이름만으로 실제 리소스를 찾을 수 있는 방법이 보편화 되지 않음 (잘 안 쓰인다.)
    

### URI

단어 뜻

- **Uniform** : 리소스 식별하는 통일된 방식
- **Resource** : 자원, URI로 식별할 수 있는 모든 것(제한 없음) - 우리가 구별할 수 있는 모든 것을 뜻한다.
- **Identifier** : 다른 항목과 구분하는데 필요한 정보


### URL, URN

단어 뜻

  - URL -  Locator : 리소스가 있는 위치를 지정한다.
  - URN - Name : 리소스에 이름을 부여하는 것
  

### URL 전체 문법


- **scheme**
    
    
    - 주로 프로토콜(어떤 방식으로 자원에 접근할 것인가 하는 약속 규칙) 사용
        - http, https, ftp 등등
    - http는 80포트, https는 443 포트를 주로 사용, 포트는 생략 가능
    - https는 http에 보안 추가한 것이다. (HTTP Secure)
    
- **userinfo**
    
    
    - URL에 사용자정보를 포함해서 인증하는데 거의 사용하지 않는다.
    
- **host**
    
    
    - 호스트명
    - 도메인명 or IP 주소 직접 사용가능하다.
    
- **PORT**
    
    
    - PORT 생략 가능
    - 접속 포트
    - 일반적으로 http - 80. https - 443
    
- **path**
    
    
    - 리소스가 있는 경로
    - 보통 계층적 구조

- **query**
    
    
    - key=value 형태
    - ?로 시작, &로 추가 가능
        - ?keyA=valueA&keyB=valueB
    - query parameter, query string으로 불린다.
        - 이유: 웹서버에서 제공하는 파라미터정보, 다 문자로 넘어가기 때문에 쿼리 스트링이라고도 불린다.
        
- fragment
    
    
    - html 내부 북마크 등으로 사용된다.
    - 서버에 전송되는 정보는 아니다.