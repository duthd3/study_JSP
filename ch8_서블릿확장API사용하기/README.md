# 8.1서블릿 포워드 기능 사용하기
## 8.1.1 포워드기능
- 하나의 서블릿에서 다른 서블릿이나 JSP와 연동하는 방법을 포워드라고 한다.
  - 요청에 대한 추가 작업을 다른 서블릿에게 수행하게 한다.
  - 요청에 포함된 정보를 다른 서블릿이나 JSP와 공유할 수 있다.
  - 요청에 정보를 포함시켜 다른 서블릿에 전달할 수 있다.
  - 모델2 개발 시 서블릿에서 JSP로 데이터를 전달하는데 사용된다.

# 8.2서블릿의 여러가지 포워드 방법
- 1.redirect방법
  - HttpServletResponse 객체의 sendRedirect() 메서드를 이용.
  - 웹 브라우저에 재요청하는 방식.
  - 형식:sendRedirect("포워드할 서블릿 또는 JSP");

- 2.Refresh방법
  - HttpServletRespoonse 객체의 addHeader() 메서드를 이용.
  - 웹 브라우저에 재요청하는 방식.
  - 형식:response.addHeader("Refresh", "경과시간(초); url=요청할 서블릿 또는 JSP");

- 3.location방법
  - 자바스크립트 location 객체의 href속성을 이용.
  - 자바스크립트에서 재요청하는 방식.
  - 형식:locatio.href='요청할 서블릿 또는 JSP';

- 4.dispatch방법
  - 일반적으로 포워딩 기능을 지칭.
  - 서블릿이 직접 요청하는 방법.
  - RequestDispatcher 클래스의 forward() 메서드를 이용.
  - 형식:RequestDispatcher dis = request.getRequestDispatcher("포워드할 서블릿 또는 JSP");
         dis.forward(request, response);

# 8.3dispatch를 이용한 포워드 방법
- dispatch를 이용한 포워딩 과정이 redirect방법과 다른 점은 클라이언트의 웹 브라우저를 거치지 않고 바로 서버에서 포워딩이 진행된다는 점이다.
- 웹 브라우저의 주소창의 URL이 변경되지 않는다. 즉, 클라이언트 측에서는 포워드가 진행되었는지 알 수 없다.

# 8.4바인딩

