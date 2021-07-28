# 서블릿 기초

## 1.서블릿의 세 가지 기본 기능

### 1. 서블릿 기본 기능 수행 과정
- 클라이언트로부터 요청을 받는다.
- 데이터베이스 연동과 같은 비즈니스 로직을 처리한다.
- 처리된 결과를 클라이언트에 돌려준다.

### 2. 서블릿 응답과 요청 수행 API 기능
- 요청과 관련된 API:javax.servlet.http.httpServletRequest 클래스
- 응답과 관련된 API:javax.servlet.http.HttpServeltResponse 클래스


## 2.\<form>태그 이용해 서블릿에 요청하기

### 1.\<form>태그로 서블릿에 요청하는 과정
- 서블릿과 JSP는 HTML,CSS,자바스크립트와 연동하여 동작한다.
- 사용자가 입력한 데이터가 서블릿으로 컨테이너에 전송. 서블릿은 여러가지 메서드를 이용해서 전송된 데이터를 받는다.
### 2.\<form>태그의 여러 가지 속성
  - name속성:\<form>태그의 이름을 지정,여러 개의 form이 존재할 경우 구분하는 역할, 자바스크립트에서\<form>태그에 접근할 때 사용.
  - method속성:\<form> 태그 안에서 데이터를 전송할 때 전송 방법을 지정.
  - action속성:\<form> 태그에서 데이터를 전송할 서블릿이나 JSP를 지정, 서블릿으로 전송할 때는 매핑 이름을 사용.
  - encType속성:\<form> 태그에서 전송할 데이터의 encoding 타입을 지정.

## 3.서블릿에서 클라이언트의 요청을 얻는 방법
메서드|기능
|--|--|
String getParameter(String name)|name의 값을 알고 있을 때 그리고 name에 대한 전송된 값을 받아오는 데 사용.|
String getParameterValues(String name)|같은 name에 대해 여러 개의 값을 얻을 때 사용.|
Enumeration getParameterNames()|name 값을 모를 때 사용.|

## 4.서블릿의 응답 처리 방법
- doGet()이나 doPost() 메서드 안에서 처리.
- javax.servlet.http.HttpServletResponse 객체를 이용.
- setContentType()을 이용해 클라이언트에게 전송할 데이터 종류(MIME-TYPE)를 지정.
- 클라이언트(웹브라우저)와 서블릿의 통신은 자바 I/O의 스트림을 이용.
- #서블릿이 클라이언트에 응답하는 과정#
  - setContentType()을 이용해 MIME-TYPE을 지정.
  - 데이터를 출력할 PrintWriter 객체를 생성.
  - 출력 데이터를 HTML 형식으로 만든다.
  - PrintWriter의 print()나 println()을 이용해 데이터를 출력.

### 1.MIME-TYPE
- 서버(서블릿)에서 웹 브라우저로 데이터를 전송할 때 톰캣 컨테이너에서 미리 제공하는 여러 가지 전송 데이터 종류 중 하나를 지정해서 전송.
- 톰캣 컨테이너에서 미리 설정해 놓은 데이터 종류들을 MIME-TYPE이라고 한다.
- HTML로 전송:text/html
- 일반 텍스트로 전송:text/plain
- XML 데이터로 전송:application/xml
 

  
