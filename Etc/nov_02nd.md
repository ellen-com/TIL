# Velocity
Velocity�� �ڹ� ����� ���ø� �����̴�.

Velocity�� �� ������ �����̳ʵ��� �ڹ� �ڵ�ȿ��� ���ǵ� �޼ҵ鿡 �����ϴ� ���� �����ش�. �̰��� �� ������ �����̳ʵ��� �ڹ� �����ڵ�� �Բ� Model-View-Controller(MVC) ��Ű���Ŀ� ���� �� ����Ʈ�� ������ �������� �ּ��� ����� ���������� �����شٴ� ���� �ǹ��Ѵ�.

���ν�Ƽ�� �� �������� �ڹ� �ڵ带 �и��Ͽ�, ������� ���鿡�� �� �� �� ����Ʈ�� �ս��� ���������� �� �ֵ��� �ϰ�, �ڹ� ���� ������ (JSP) �Ǵ� PHP�� ��ü�� �� �ִ� ����� �����Ѵ�.

# Spring MVC Architecture

Model, View, Controller�� �и��� ������ ���� (�����ڰ� ���� �����ؾ� �ϴ� ��)

## Model
* ���ø����̼��� ����(data)�� ��Ÿ����.
* �Ϲ������� POJO�� �����ȴ�.
* Java Beans

## View
* ���÷��� ������ �Ǵ� ���������̼�
* Model data�� �������� ����ϸ�, HTML ouput�� �����Ѵ�.
* JSP (JSP �̿ܿ��� Thymeleaf, Groovy, Freemarker �� ���� Template Engine�� �ִ�.)

## Controller
* View�� Model ������ �������̽� ����
* Model/View�� ���� ����� �Է� �� ��û�� �����Ͽ� �׿� ���� ������ ����� Model�� ��� View�� �����Ѵ�.
* ��, Model Object�� �� Model�� ȭ�鿡 ����� View Name�� ��ȯ�Ѵ�.
* Controller ?> Service ?> Dao ?> DB
* Servlet
// Servlet : �ڹٸ� ����Ͽ� ���� ����� ���� �ʿ��� ���.
// �� �� ���� �������ڸ�  Ŭ���̾�Ʈ�� ��� ��û�� �ϸ� �׿� ���� ����� �ٽ� �������־�� �ϴµ�, �̷��� ������ �ϴ� �ڹ� ���α׷� 

Spring Framework�� �����ϴ� Class

## DispatcherServlet
* Spring Framework�� �����ϴ� Servlet Ŭ����
* ������� ��û�� �޴´�.
* Dispatcher�� ���� ��û�� HandlerMapping���� �Ѿ��.

## HandlerMapping
* ������� ��û�� ó���� Controller�� ã�´�. (Controller URL Mapping)
* ��û url�� �ش��ϴ� Controller ������ �����ϴ� table�� ������.
* ��, Ŭ������ @RequestMapping(��/url��) annotaion�� ����ϸ� �ش� URL�� ���� ��û�� ������ �� table�� ����� ������ ���� �ش� Ŭ���� �Ǵ� �޼��忡 Mapping�Ѵ�.

## ViewResolver
* Controller�� ��ȯ�� View Name(the logical names)�� prefix, suffix�� �����Ͽ� View Object(the physical view files)�� ��ȯ�Ѵ�.
* ���� ��� view name: home, prefix: /WEB-INF/views/, suffix: .jsp�� ��/WEB-INF/views/home.jsp����� ��ġ�� View(JSP)�� Controller���� ���� Model�� �����Ѵ�.
* �� �Ŀ� �ش� View���� �� Model data�� �̿��Ͽ� ������ �������� ����� ����ڿ��� �����ش�.

��ó : https://gmlwjd9405.github.io/2018/12/20/spring-mvc-framework.html