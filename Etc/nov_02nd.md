# Velocity
Velocity는 자바 기반의 템플릿 엔진이다.

Velocity는 웹 페이지 디자이너들이 자바 코드안에서 정의된 메소들에 접근하는 것을 도와준다. 이것은 웹 페이지 디자이너들이 자바 개발자들과 함께 Model-View-Controller(MVC) 아키텍쳐에 따른 웹 사이트를 각자의 영역에서 최선의 결과를 가져오도록 도와준다는 것을 의미한다.

벨로시티는 웹 페이지와 자바 코드를 분리하여, 장기적인 측면에서 볼 때 웹 사이트를 손쉽게 유지보수할 수 있도록 하고, 자바 서버 페이지 (JSP) 또는 PHP를 대체할 수 있는 방안을 제시한다.

# Spring MVC Architecture

Model, View, Controller를 분리한 디자인 패턴 (개발자가 직접 구현해야 하는 것)

## Model
* 애플리케이션의 상태(data)를 나타낸다.
* 일반적으로 POJO로 구성된다.
* Java Beans

## View
* 디스플레이 데이터 또는 프리젠테이션
* Model data의 렌더링을 담당하며, HTML ouput을 생성한다.
* JSP (JSP 이외에도 Thymeleaf, Groovy, Freemarker 등 여러 Template Engine이 있다.)

## Controller
* View와 Model 사이의 인터페이스 역할
* Model/View에 대한 사용자 입력 및 요청을 수신하여 그에 따라 적절한 결과를 Model에 담아 View에 전달한다.
* 즉, Model Object와 이 Model을 화면에 출력할 View Name을 반환한다.
* Controller ?> Service ?> Dao ?> DB
* Servlet
// Servlet : 자바를 사용하여 웹을 만들기 위해 필요한 기술.
// 좀 더 들어가서 설명하자면  클라이언트가 어떠한 요청을 하면 그에 대한 결과를 다시 전송해주어야 하는데, 이러한 역할을 하는 자바 프로그램 

Spring Framework가 제공하는 Class

## DispatcherServlet
* Spring Framework가 제공하는 Servlet 클래스
* 사용자의 요청을 받는다.
* Dispatcher가 받은 요청은 HandlerMapping으로 넘어간다.

## HandlerMapping
* 사용자의 요청을 처리할 Controller를 찾는다. (Controller URL Mapping)
* 요청 url에 해당하는 Controller 정보를 저장하는 table을 가진다.
* 즉, 클래스에 @RequestMapping(“/url”) annotaion을 명시하면 해당 URL에 대한 요청이 들어왔을 때 table에 저장된 정보에 따라 해당 클래스 또는 메서드에 Mapping한다.

## ViewResolver
* Controller가 반환한 View Name(the logical names)에 prefix, suffix를 적용하여 View Object(the physical view files)를 반환한다.
* 예를 들어 view name: home, prefix: /WEB-INF/views/, suffix: .jsp는 “/WEB-INF/views/home.jsp”라는 위치의 View(JSP)에 Controller에게 받은 Model을 전달한다.
* 이 후에 해당 View에서 이 Model data를 이용하여 적절한 페이지를 만들어 사용자에게 보여준다.

출처 : https://gmlwjd9405.github.io/2018/12/20/spring-mvc-framework.html