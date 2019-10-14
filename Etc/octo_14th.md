# SQL Mapper와 ORM

Persistence Framework는 SQL Mapper와 ORM으로 나눌 수 있다.

	- ORM은 데이터베이스 객체를 자바 객체로 매핑함으로써 객체 간의 관계를 바탕으로 SQL을 자동으로 생성
	- SQL Mapper는 SQL을 명시해줘야 한다.


	• ORM은 관계형 데이터베이스의 ‘관계’를 Object에 반영하자는 것이 목적
	• SQL Mapper는 단순히 필드를 매핑시키는 것이 목적이라는 점에서 지향점의 차이가 있다.


## SQL Mapper
	• SQL <—매핑—> Object 필드
	• SQL Mapper는 SQL 문장으로 직접 데이터베이스 데이터를 다룬다.
		○ 즉, SQL Mapper는 SQL을 명시해줘야 한다.
		○ Ex) Mybatis, JdbcTempletes 등

## ORM(Object-Relational Mapping), 객체-관계 매핑
	• 데이터베이스 데이터 <—매핑—> Object 필드
		○ 객체를 통해 간접적으로 데이터베이스 데이터를 다룬다.
	• 객체와 관계형 데이터베이스의 데이터를 자동으로 매핑(연결)해주는 것을 말한다.
		○ ORM을 이용하면 SQL Query가 아닌 직관적인 코드(메서드)로 데이터를 조작할 수 있다.
		○ 객체 간의 관계를 바탕으로 SQL을 자동으로 생성한다.
	• Persistant API라고도 할 수 있다.
	    ○ Ex) JPA, Hibernate 등
