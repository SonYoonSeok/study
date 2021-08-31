## 🍴 ORM 도구의 활용

> ORM(Object Relational Mapping)이란, Object와 Relation 간의 불일치 문제를 해결하기 위한 도구이다.

* ORM 도구를 사용하는 이유 : JDBC API를 이용해서 개발하면 로직 처리를 SQL로 하게 되고, 자바를 사용하지만 자바의 언어적인 기능을 사용하기보다는 쿼리와 결과를 매핑하는 용도로 사용하게 되기 때문이다.

* 추상화 계층 없이 직접적으로 SQL 통해 제어하면 빠르게 개발이 가능하지만 상태 변화가 객체가 아니라 데이터베이스 상에서 일어나므로 상태를 제어하기 위해서는 데이터베이스를 제어할 수 있는 SQL을 수행하는 코드를 반복적으로 사용해야 한다.

  => ORM을 사용하여 코드의 반복을 줄이고 객체 중심의 설계에 집중하여 개발할 수 있다.



## ⚡ Spring Data JPA

### JPA

* JPA 스펙을 만들었을 당시에는 NoSQL이 존재하지 않았다.
* Spring 개발팀은 Spring one에서 NoSQL 유형 중 하나인 NEO4j를 스프링에 포함시키기 위한 시도를 하면서 NoSQL을 포함한 새로운 스펙을 재정하였다. **(Spring Data)**
* 개발자가 JPA를 사용하면, JPA 내부에서 JDBC API를 사용하여 SQL을 호출하여 DB와 통신한다.

### Spring Data

* NoSQL 또는 RDBMS 어느 한쪽만을 목표로 하지 않는다.
* 추상화 인터페이스를 통해 MySQL, Redis 등 다양한 저장소를 활용할 수 있다.

### Hibernate

* JPA 구현체의 한 종류이다.
* DB와 자바 객체를 매핑하기 위한 인터페이스(API)를 제공하고 JPA 구현체는 이 인터페이스를 구현한 것이다.
* Hibernate 내부에는 JDBC API가 동작하고 있으며, 개발자가 직접 SQL을 작성하지 않는다.
* HQL(Hibernate Query Language)라는 쿼리 언어를 포함하고 있다.
  * SQL과 매우 비슷하며 추가적인 컨벤션을 정의할 수 있다.
  * 객체 지향적이며 상속, 다향성, 관계등의 객체지향의 장점을 가진다.
  * SQL에서는 지원하지 않는 페이지네이션이나 동적 프로파일링 같은 향상된 기능을 제공한다.
  * 여러 테이블을 작업할 때 JOIN을 요구하지 않는다.

### 🍭 JPA를 사용하는 이유

* SQL 중심적인 개발에서 객체 중심적인 개발이 가능하다.
  * SQL 코드의 반복, 객체지향과 관계지향 데이터베이스의 패러다임 불일치
* 생산성 증가
  * 간단한 메소드로 CRUD가 가능하다.
* 간편한 유지보수
  * 기존 : 필드 변경 시 모든 SQL을 수정해야 한다.
  * JPA : 필드만 추가하면 된다. SQL은 JPA가 처리해준다.
* Object와 RDB 간의 패러다임 불일치 해결



## 🦴 영속성

> 데이터를 생성한 프로그램이 종료되어도 사라지지 않는 데이터의 특성을 말한다.
> 데이터를 파일이나 DB에 영구 저장함으로써 데이터에 영속성을 부여한다.

### Persistance Layer

* 프로그램의 아키텍처에서 데이터에 영속성을 부여해주는 계층

![img](https://media.vlpt.us/images/adam2/post/c97f8a01-68e6-4027-b45d-ece8f458d13c/Untitled%207.png)

### JPA에서의 영속성

![img](https://media.vlpt.us/images/adam2/post/8c9be8ab-a3eb-41aa-912d-a26209fc6134/Untitled%208.png)



* JPA의 엔티티 매니저가 활성화된 상태로 트랜잭션 안에서 DB에서 데이터를 가져오면 이 데이터는 영속성 컨텍스트가 유지된 상태이다.
* 해당 데이터 값을 변경하면 트랜잭션이 끝나는 시점에 해당 테이블에 변경 내용을 반영한다.
* 엔티티 객체의 필드 값만 변경해주면 update를 해줄 필요가 없다.

## 🌈 데이터베이스와 객체 매핑

### Entity 클래스 설정

* 데이터베이스 스키마의 내용을 자바 클래스로 표현할 수 있는 대상을 Entity 클래스라고 한다.
* @Entity 어노테이션을 선언하는 것으로 엔티티 매니저가 관리해야할 대상임을 인식시킬 수 있다.

| 전략                    | 개념                                                         |
| ----------------------- | ------------------------------------------------------------ |
| GenerationType.IDENTITY | id 값을 null로 하면 DB가 알아서 AUTO_INCREMENT 해준다.       |
| GenerationType.SEQUENCE | 유일한 값을 순서대로 생성하는 특별한 데이터베이스 오브젝트이다. |
| GenerationType.TABLE    | 키 생성 전용 테이블을 하나 만들어서 시퀀스를 흉내내는 전략이다. |
| GenerationType.AUTO     | 기본 설정 값, 세 가지 전략을 자동으로 지정한다.              |
