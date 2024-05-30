https://blog.naver.com/rlagudndjs95/223454471300






ORM 이란?
애플리케이션 Class와 RDB(Relational DataBase)의 테이블을 매핑하는 개념으로, 기술적으로는 애플리케이션의 객체를 코드를 사용하여 RDB 테이블에 자동으로 영속화 해주는 것입니다.

JPA(Java Persistence API)이란?
자바 객체를 관계형 데이터베이스의 테이블에 매핑하는 표준 인터페이스를 제공하는 자바의 사양입니다. JPA는 객체지향 프로그래밍의 장점을 데이터베이스와의 상호작용에 활용할 수 있게 해줍니다.


※ ORM(Object-Relational Mapping) VS JPA(Java Persistence API)

ORM(Object-Relational Mapping)과 JPA(Java Persistence API)는 둘 다 객체지향 프로그래밍과 관계형 데이터베이스 사이의 불일치를 해결하는 데 사용되는 기술입니다. 하지만, 이 둘은 다소 다른 개념을 나타냅니다..

*ORM은 일반적인 개념입니다. 객체 지향 프로그래밍 언어에서 사용되는 객체와 관계형 데이터베이스의 테이블 간의 매핑을 관리하는 기법입니다. 이를 통해 개발자는 데이터베이스와 상호작용할 때 SQL 쿼리를 직접 작성하지 않고도 객체 지향 언어의 문법을 사용할 수 있습니다.
주요 특징
추상화: 데이터베이스 테이블을 객체로, 테이블의 행을 객체의 인스턴스로 매핑합니다.
데이터베이스 독립성: 데이터베이스에 종속적이지 않은 코드 작성이 가능합니다.
생산성 향상: SQL 쿼리를 직접 작성하지 않아도 되므로 개발 생산성이 향상됩니다.
유지보수성: 데이터베이스 구조가 변경되더라도 객체 모델만 수정하면 되므로 유지보수가 쉽습니다.


*JPA는 자바에서 ORM을 구현하기 위한 표준 명세(specification)입니다. JPA는 Java EE의 일부로서, 자바 애플리케이션이 ORM을 사용할 수 있게 합니다. JPA 자체는 인터페이스와 어노테이션으로 구성된 명세일 뿐, 실제 구현체는 아닙니다.
주요 특징
표준화: JPA는 자바의 ORM을 위한 표준 인터페이스를 정의합니다.
구현체: JPA 명세를 구현한 여러 라이브러리(구현체)가 있습니다. 대표적인 구현체로는 Hibernate, EclipseLink, OpenJPA 등이 있습니다.
POJO: JPA 엔티티는 일반적인 자바 객체(POJO, Plain Old Java Object)로 정의됩니다.
어노테이션: 엔티티 클래스와 그 속성에 어노테이션을 사용하여 매핑을 정의합니다.
쿼리 언어: JPA는 JPQL(Java Persistence Query Language)이라는 객체 지향 쿼리 언어를 제공합니다.

비교표
특징
ORM
JPA
개념
객체-관계 매핑을 위한 일반적인 기법, 방법론
자바의 ORM을 위한 표준 명세
표준 여부
특정 언어나 플랫폼에 종속되지 않음
자바 EE의 표준 명세
기능 제공
객체와 데이터베이스 테이블 간 매핑 관리
ORM을 위한 표준 인터페이스, 어노테이션, JPQL 등
구현체
-
Hibernate, EclipseLink, OpenJPA 등의 JPA 구현체
어노테이션 사용
특정 프레임워크에 따라 다름
@Entity, @Table, @Id, @Column 등의 어노테이션 사용
쿼리 언어
SQL 사용 또는 프레임워크 특정 쿼리 언어 사용 가능
JPQL 제공



요약

ORM은 객체와 관계형 데이터베이스 간의 매핑을 관리하는 일반적인 기술 개념입니다.
JPA는 자바에서 ORM을 구현하기 위한 표준 명세로, ORM 기술을 자바에서 표준화하고 이를 위한 인터페이스와 어노테이션을 정의합니다.
결론적으로, JPA는 자바 언어를 위한 ORM의 표준을 정의한 것이고, ORM은 그 표준을 포함한 더 넓은 개념입니다. JPA를 사용함으로써 자바 개발자는 ORM을 위한 표준화된 접근 방식을 사용할 수 있게 됩니다.









※ JPA 주요 개념


1. 엔티티(Entity):
JPA에서 엔티티는 데이터베이스 테이블에 매핑되는 클래스입니다. 각 엔티티 인스턴스는 테이블의 한 행(row)에 해당합니다.
엔티티 클래스는 @Entity 어노테이션으로 표시됩니다.

2. 엔티티 매니저(Entity Manager):
엔티티를 생성, 읽기, 업데이트, 삭제(CRUD)하는 데 사용되는 인터페이스입니다.
EntityManager는 javax.persistence.EntityManager 인터페이스를 통해 제공됩니다.

3. 영속성 컨텍스트(Persistence Context):
엔티티 매니저가 관리하는 엔티티 객체들의 집합입니다. 이는 특정 시점에 데이터베이스와 동기화된 엔티티 객체의 스냅샷을 유지합니다.
영속성 컨텍스트 내의 엔티티들은 관리 상태에 있다고 하며, 변경사항은 자동으로 데이터베이스에 반영됩니다.

4. JPQL(Java Persistence Query Language):
객체지향 쿼리 언어로, SQL과 유사하지만 엔티티 객체를 대상으로 쿼리를 수행합니다.
JPQL은 엔티티와 속성에 대해 질의하고 조작할 수 있습니다.


사진 설명을 입력하세요.





주요 어노테이션
@Entity: 클래스가 엔티티임을 나타냅니다.
@Id: 엔티티의 기본 키를 나타냅니다.
@GeneratedValue: 기본 키의 생성 전략을 지정합니다.
@Table: 엔티티가 매핑될 테이블 정보를 지정합니다.
@Column: 엔티티의 속성이 매핑될 테이블의 컬럼을 지정합니다.
@OneToOne, @OneToMany, @ManyToOne, @ManyToMany: 엔티티 간의 관계를 나타냅니다.


JPA의 장점
객체-관계 매핑(ORM):
개발자는 데이터베이스 테이블과 직접 상호작용하지 않고 객체를 통해 데이터베이스 작업을 할 수 있습니다.
객체지향적인 코드 작성이 가능해집니다.
표준화:
JPA는 자바 EE의 표준 사양이므로 다양한 구현체에서 호환성을 제공합니다.
대표적인 JPA 구현체로는 Hibernate, EclipseLink, OpenJPA 등이 있습니다.
생산성:
데이터베이스 작업을 추상화하여 코드의 양을 줄이고, 유지보수를 쉽게 합니다.
복잡한 SQL 쿼리를 작성하지 않아도 되므로 개발 생산성이 향상됩니다.




예제코드

프로젝트 설정
Spring Initializr를 사용하여 Spring Boot 프로젝트를 생성합니다. 필요한 종속성은 다음과 같습니다:
Spring Web
hibernate - JPA
Spring Data JPA
H2 Database (또는 다른 데이터베이스)

build.gradle 파일
plugins {
    id 'org.springframework.boot' version '2.7.4'
    id 'io.spring.dependency-management' version '1.0.13.RELEASE'
    id 'java'
}

group = 'com.example'
version = '0.0.1-SNAPSHOT'
sourceCompatibility = '11'

repositories {
    mavenCentral()
}

dependencies {
    implementation 'org.springframework.boot:spring-boot-starter-data-jpa'
    implementation 'org.springframework.boot:spring-boot-starter-web'
    runtimeOnly 'com.h2database:h2'
    testImplementation 'org.springframework.boot:spring-boot-starter-test'
}

test {
    useJUnitPlatform()
}

application.properties 파일
spring.datasource.url=jdbc:h2:mem:testdb
spring.datasource.driverClassName=org.h2.Driver
spring.datasource.username=sa
spring.datasource.password=password
spring.jpa.database-platform=org.hibernate.dialect.H2Dialect
spring.h2.console.enabled=true
spring.h2.console.path=/h2-console

엔티티 클래스 (User.java)
package com.example.demo.entity;

import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;

@Entity
public class User {
    
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String name;
    private String email;
    private String password;

    // Getters and Setters

    public Long getId() {
        return id;
    }

    public void setId(Long id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getEmail() {
        return email;
    }

    public void setEmail(String email) {
        this.email = email;
    }

    public String getPassword() {
        return password;
    }

    public void setPassword(String password) {
        this.password = password;
    }
}

레포지토리 인터페이스 (UserRepository.java)
package com.example.demo.repository;

import org.springframework.data.jpa.repository.JpaRepository;
import com.example.demo.entity.User;

public interface UserRepository extends JpaRepository<User, Long> {
}

* JapRepository 인터페이스에 상속받으면 기본 CRUD 함수 제공

◆저장 및 업데이트
save(S entity):
엔티티를 저장하거나 업데이트합니다. 엔티티가 이미 존재하면 업데이트하고, 존재하지 않으면 새로 저장합니다.

◆조회
findById(ID id):
기본 키로 엔티티를 조회합니다. 존재하지 않으면 Optional.empty()를 반환합니다.
findAll():
모든 엔티티를 조회하여 리스트로 반환합니다.
findAllById(Iterable<ID> ids):
주어진 ID 목록에 해당하는 모든 엔티티를 조회하여 리스트로 반환합니다.
findAll(Sort sort):
모든 엔티티를 정렬된 순서로 조회하여 리스트로 반환합니다.
findAll(Pageable pageable):
페이지네이션을 적용하여 엔티티를 조회합니다. Pageable 객체를 사용하여 페이지 번호와 크기, 정렬 등을 지정할 수 있습니다.

◆삭제
deleteById(ID id):
기본 키로 엔티티를 삭제합니다.
delete(T entity):
주어진 엔티티를 삭제합니다.
deleteAll(Iterable<? extends T> entities):
주어진 엔티티 목록을 모두 삭제합니다.
deleteAll():
모든 엔티티를 삭제합니다.

◆존재 여부 확인
existsById(ID id):
주어진 ID에 해당하는 엔티티가 존재하는지 확인합니다.


* repository에서 커스텀으로 사용자 함수 만들기
Spring Data JPA에서 기본 제공되는 JpaRepository 인터페이스의 메서드 외에도, 사용자 정의 메서드를 추가로 구현할 수 있습니다. 사용자 정의 메서드를 구현하는 방법은 크게 두 가지로 나눌 수 있습니다.

쿼리 메서드(Query Method) 사용
사용자 정의 리포지토리(Custom Repository) 구현
구현법은 글 최하단에 따로 설명



서비스 클래스 (UserService.java)
package com.example.demo.service;

import java.util.List;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Service;

import com.example.demo.entity.User;
import com.example.demo.repository.UserRepository;

@Service
public class UserService {

    @Autowired
    private UserRepository userRepository;

    public User saveUser(User user) {
        return userRepository.save(user);
    }

    public List<User> getAllUsers() {
        return userRepository.findAll();
    }

    public User getUserById(Long id) {
        return userRepository.findById(id).orElse(null);
    }

    public User updateUser(Long id, User userDetails) {
        User user = userRepository.findById(id).orElse(null);
        if (user != null) {
            user.setName(userDetails.getName());
            user.setEmail(userDetails.getEmail());
            user.setPassword(userDetails.getPassword());
            return userRepository.save(user);
        }
        return null;
    }

    public void deleteUser(Long id) {
        userRepository.deleteById(id);
    }
}

컨트롤러 클래스 (UserController.java)
package com.example.demo.controller;

import java.util.List;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.*;

import com.example.demo.entity.User;
import com.example.demo.service.UserService;

@RestController
@RequestMapping("/api/users")
public class UserController {

    @Autowired
    private UserService userService;

    @PostMapping
    public ResponseEntity<User> createUser(@RequestBody User user) {
        return ResponseEntity.ok(userService.saveUser(user));
    }

    @GetMapping
    public ResponseEntity<List<User>> getAllUsers() {
        return ResponseEntity.ok(userService.getAllUsers());
    }

    @GetMapping("/{id}")
    public ResponseEntity<User> getUserById(@PathVariable Long id) {
        User user = userService.getUserById(id);
        if (user != null) {
            return ResponseEntity.ok(user);
        }
        return ResponseEntity.notFound().build();
    }

    @PutMapping("/{id}")
    public ResponseEntity<User> updateUser(@PathVariable Long id, @RequestBody User userDetails) {
        User updatedUser = userService.updateUser(id, userDetails);
        if (updatedUser != null) {
            return ResponseEntity.ok(updatedUser);
        }
        return ResponseEntity.notFound().build();
    }

    @DeleteMapping("/{id}")
    public ResponseEntity<Void> deleteUser(@PathVariable Long id) {
        userService.deleteUser(id);
        return ResponseEntity.noContent().build();
    }
}

애플리케이션 클래스 (DemoApplication.java)
package com.example.demo;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class DemoApplication {

    public static void main(String[] args) {
        SpringApplication.run(DemoApplication.class, args);
    }
}













*사용자 정의 레포지토리, 쿼리메소드 구현

1. 쿼리 메서드(Query Method) 사용
Spring Data JPA는 메서드 이름을 분석하여 자동으로 쿼리를 생성해주는 기능을 제공합니다. 이를 쿼리 메서드(Query Method)라고 합니다. 예를 들어, User 엔티티에 대해 이메일로 사용자를 찾는 메서드를 구현해보겠습니다.


User 엔티티
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;

@Entity
public class User {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String name;
    private String email;

    // Getters and Setters
}

UserRepository 인터페이스
import org.springframework.data.jpa.repository.JpaRepository;

public interface UserRepository extends JpaRepository<User, Long> {
    User findByEmail(String email);
}

위 코드에서 findByEmail 메서드는 메서드 이름을 기반으로 이메일로 사용자를 검색하는 쿼리를 자동으로 생성합니다. Spring Data JPA는 메서드 이름의 findBy 뒤에 오는 속성 이름(Email)을 기반으로 쿼리를 작성합니다.




2. 사용자 정의 리포지토리(Custom Repository) 구현
쿼리 메서드로 해결할 수 없는 복잡한 쿼리나 특정 로직이 필요한 경우, 사용자 정의 리포지토리를 구현할 수 있습니다. 이를 위해서는 두 가지 인터페이스를 정의하고, 이를 구현해야 합니다.

1. 사용자 정의 인터페이스 정의
먼저 사용자 정의 인터페이스를 정의합니다. 이 인터페이스에는 사용자 정의 메서드를 선언합니다.

public interface UserRepositoryCustom {
    User findUserCustomMethod(Long id);
}

2. 사용자 정의 인터페이스 구현
다음으로, 이 인터페이스를 구현하는 클래스를 작성합니다. 여기서 사용자 정의 메서드의 실제 구현을 작성합니다.

import javax.persistence.EntityManager;
import javax.persistence.PersistenceContext;
import javax.persistence.TypedQuery;

public class UserRepositoryCustomImpl implements UserRepositoryCustom {

    @PersistenceContext
    private EntityManager entityManager;

    @Override
    public User findUserCustomMethod(Long id) {
        TypedQuery<User> query = entityManager.createQuery(
            "SELECT u FROM User u WHERE u.id = :id", User.class);
        query.setParameter("id", id);
        return query.getSingleResult();
    }
}

3. 기본 리포지토리에 사용자 정의 인터페이스 상속
마지막으로, 기본 리포지토리에 사용자 정의 인터페이스를 상속받아 확장합니다.
import org.springframework.data.jpa.repository.JpaRepository;

public interface UserRepository extends JpaRepository<User, Long>, UserRepositoryCustom {
}







출처: 구글, 챗지피티
