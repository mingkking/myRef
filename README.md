# myRef
```
윤년
	y % 4 == 0 && y % 100 != 0 || y % 400 == 0
```
### lombok 롬복
```
	설치
		install software
			https://projectlombok.org/p2
```
### 1. jdk 환경변수 설정하는 법
 - 1.  JAVA_HOME
     jdk 파일 경로를 시스템 변수에 등록
 - 2. Path 새로만들기로 등록 후 제일 위로 올림 
     C:\Users\ict03_029\Downloads\jdk-11.0.22_windows-x64_bin\jdk-11.0.22\bin

### 2. 2차원 배열 예제
 - 1. 로또
```      
int[][] data = new int[5][6];
System.out.println(data.length);
// 값 지정
for (int i = 0; i < data.length; i++) {
	for (int j = 0; j < data[i].length; j++) {
	    data[i][j] = (int)(Math.random()*45) + 1;
	}
}
		
// 출력
for (int i = 0; i < data.length; i++) {
	for (int j = 0; j < data[i].length; j++) {
		System.out.print(data[i][j] + " ");
	}
	System.out.println();
}
```
  - 2. 로또 예제
```
int [][] lotto = new int[5][6];
// 로또 번호 생성
for (int i = 0; i < lotto.length; i++) {
	for (int j = 0; j < lotto[i].length; j++) {
		lotto[i][j] = (int)(Math.random()*45) + 1;
		// 중복 제거
		for (int j2 = 0; j2 < j; j2++) {
			if(lotto[i][j] == lotto[i][j2]) {
				j--;
			}
		}
		// 중복 제거
	}
}
// 로또 번호 생성
// 정렬
for (int i = 0; i < lotto.length; i++) {
	for (int j = 0; j < lotto[i].length; j++) {
		for (int k = 1; k < lotto[i].length-j; k++) {
			if(lotto[i][k-1] >= lotto[i][k]) {
				int  temp = lotto[i][k];
				lotto[i][k] = lotto[i][k-1];
				lotto[i][k-1] = temp;
			}
		}
	}
}
// 정렬
// 출력
for (int i = 0; i < lotto.length; i++) {
	for (int j = 0; j < lotto[i].length; j++) {
		if(j == 0) {
			System.out.print( (i+1) + "번째 로또번호: ");
		}
		System.out.print(lotto[i][j] + " ");
	}
	System.out.println();
}
```
### 3. 369게임 코드
```
/*
 * 1부터 50까지 숫자 중에서 3, 6, 9 게임처럼
 * 3, 6, 9 숫자를 포함하면 그 갯수만큼 "짝" 글자를 출력하고
 * 그렇지 않으면 그 숫자를 출력한다.
 */
for (int i = 1; i <= 50; i++) {
	int save = i;
	while(save != 0) {
		if( save % 10 == 3 || save % 10 == 6 || save % 10 == 9 ) { // 예) 33 은 짝 한번 출력 후 밑 save에 3이 저장 됨 후 짝 출력 후 0이라서 괄호 밖으로 빠짐
			System.out.print("짞 ");
		}
		save = save / 10;
	}
	
	System.out.println(i);
	
}
```
### 4. 오버로딩
```
/*
 * 오버로딩 (overloading)
 * 		- 여러개의 함수가 동일 함수명 사용
 * 		- 인자의 자료형과 갯수가 다름
 * [주의] 리턴형만 다른 것은 아님
 * 		void test(int a) {}
 * 		double test(int z) {}
 * 		char test(int h) {}
 * 
 */
```
### 5. 재귀호출
```
public static void main(String[] args) {
	/*
	 * 재귀호출 -함수가 자기 자신을 호출하는 것
	 */
	int sum = 0;
	sum = sumFunc(10);
	System.out.println("총합: " + sum);
}

static int sumFunc(int i) {
	if (i == 1) {
		return 1;
	}

	return i + sumFunc(i - 1);
}
```
### 6. CallByRef
```
/*
 * CallByRef
 * 		- 메소드의 인자가 참조형인 경우
 * 		주소복사가 되어서 원본에 영향이 있음
 */
```
### 7. Call by value
```
/*
 * Call by value
 * 		인자의 자료형이 기본형인 경우
 * 
 */
```

### 8. 생성자함수
```
/*
	 * 생성자함수 (constructor)
	 * 		- 클래스의 멤버값을 초기화 할 때 사용
	 * 		- 클래스가 객체화(인스턴스화)될 때 실행되는 함수 : new 사용시
	 * 		- 클래스명과 동일 이름이여야 함
	 * 		- return 이 없어야 함(void도 있으면 안됨)
	 * 		- 오버로딩 가능(overloading)
	 * 			-> 매개변수의 타입과 갯수가 다른 동일한 이름의 함수들
	 * 
	 * [참고]
	 * 		class A {
	 * 			int A = 10;
	 * 			void A() {일반함수}
	 * 			A(){생성자함수}
	 * 		}
	 * 
	 * [참고] 기본생성자함수 : default constructor
	 * 		- 생성자함수가 한개도 없는 경우 자동으로 기본생성자함수를 생성
	 * 		- 습관처럼 기본생성자함수를 만들어두면 됨
	 * 
	 * this : 객체의 멤버를 지칭하기 위해
	 * this() : 다른 생성자 호출
	 * this함수는 무조건 맨 첫 줄에 와야한다.
	 */
```
### 9. static
```
/*
 * static
 * 		- 각 객체들끼리 공유
 * 		- 메모리에 단 1개 생성
 * 		- 객체생성보다 먼저 생성 됨
 * 		- 클래스명으로 접근 가능
 */
```
### 10. 상속 (extends)
```
 /*
 * 클래스 상속관계
 * 		- 부모의 멤버를 사용
 * 		- 부모의 멤버가 없으면 그냥 추가해서 사용
 * 		- 부모의 멤버가 있는데 재정의(변경) (overriding)
 * 			-> 메소드명을 동일하게 구현
 * 				인자와 리턴형이 동일
 * 		- 부모의 메소드를 사용
 * 		- 상속관계끼리도 casting 가능 하지만 컴파일 에러가 남 사용 불가능
 * 		- 단일 상속
 * 		- 부모클래스 1개
 * 
 * [참고] overloading과 다름
 * 
 * [설계시 관점]
 * 		- 클래스의 공통부분을 부모클래스 만들기
 * 		- 클래스의 고유부분을 자식클래스 만들기
 * 
 * this : 현재객체의 래퍼런스
 * super : 부모객체의 래퍼런스
 * this() : 다른 생성자함수 호출할 때
 * super() : 부모의 다른 생성자함수 호출할 때
 * 
 * 다형성 - 함수는 1개인데 불려지는 객체에 따라 함수의 역할이 다 다르다
 * 
 * Item i = new Item(); 추상 클래스는 생성 안됨
 * 
 * 오버라이딩 강제성
 * 		-> 부모클래스에서 미완성함수 (abstract method)
 * 		-> 미완성함수를 가진 클래스는 미완성클래스
 * 		-> 미완성 클래스는 객체 생성 안됨
 * 		-> 미완성 클래스는 부모역할만 가능
 */
```
### 11. singleton
```
/*
 * 목적 : DBConnect 객체가 1개 공유 
 */
static DBConnect con = null;

private DBConnect() {
	System.out.println("DB 연동");
}

public static DBConnect getInstance() {
	if (con == null) {
		con = new DBConnect();
	}
	return con;
}

```
### 12. 접근지정자
```
/*
 * 접근지정자
 * private : 다른 클래스에서 접근 안됨
 * public : 다른 패키지에서도 접근 허용
 * default : 동일 패키지에서만 접근 허용
 * protected : 동일 패키지에서만 접근 허용
 * 				다른 패키지인 경우 자식 클래스에서만 접근 허용
 */
```
### 13. 참고
```
1 클래스 public default abstract final
2 변수 public default private protected static final
3 생성자 public default private protected
4 메소드 public default private protected static abstact final
```
### 14. 인터페이스 (implements)
```
인터페이스 : 다중상속
interface B{
	[public static final] int B;
	[public abstract] void B();
}
```
### 15. MySQL - cmd
```
1. bin 경로를 환경변수 path 쪽에 추가
	C:\Program Files\MySQL\MySQL Server 8.0\bin
2. cmd
	root계정으로 접속
		mysql -u root -p
	DB목록보기
		show databases;
	DB 생성
		create database basic;
	DB 접속
		use world;
	계정생성
		create user scott@'%' identified by 'tiger';
		create user jung@'%' identified by '1234';
		create user jungminki@'%' identified by 'admin1234';
	권한부여
		grant all on *.* to scott@'%' with grant option;
		grant all on *.* to jungminki@'%' with grant option;
		grant select, insert, update, delete on basic.* to jung@'%';
	테이블 목록
		show tables;
	SQL파일 실행
		source C:\downloads\db\scott_emp.sql	
```
### 16. MySQL - 명령어
```
1. 컬럼 추가
	alter table [테이블명] add ([컬럼명] [컬럼타입]);
2. 컬럼 삭제
	ALTER TABLE [테이블명] DROP COLUMN [컬럼명];
2. 컬럼 보기
	desc [테이블명];
3. 컬럼 지우기
	alter table [테이블명] drop column [컬럼명];
4. 컬럼 변경
	alter table [테이블명] change [컬럼명] [컬럼명] [데이타타입];
	alter table [테이블명] modify [컬럼명] [데이타타입]
5. 테이블 복사
	create table [복사할테이블명]
	as select [컬럼명], [컬럼명], ...deptno
	from [복사해서만들어질테이블명];
6. 컬럼 제약조건
	1. PK (프라이머리 키 - 중복X, 널값X)
		ALTER TABLE [테이블명] 
		ADD CONSTRAINT [테이블명]_[컬럼명]_pk PRIMARY KEY ([컬럼명]);
	2. UNIQUE (고유키 - 중복X, 널값 허용)
		ALTER TABLE [테이블명] 
		ADD CONSTRAINT [테이블명]_[컬럼명]_uq UNIQUE KEY ([컬럼명]);
  	3. CHECK
		ALTER TABLE [테이블명]
		ADD CONSTRAINT [테이블명]_[컬럼명]_ck CHECK ([컬럼명] IN('[값]', '[값]'));
	4. DEFAULT
		ALTER TABLE [테이블명] MODIFY [컬럼명] [타입] DEFAULT '[값]';
	5. FOREIGN KEY (외래키 - )
		ALTER TABLE [적용테이블명]
		ADD CONSTRAINT [적용테이블명]_[컬럼명]_fk FOREIGN KEY ([컬럼명]) REFERENCES [참조테이블명]([컬럼명])
	6. ON DELETE CASCADE(fk 뒤쪽에 쓰면 됨) - 외래키 삭제시 연쇄삭제
	7. ON DELETE SET NULL(fk 뒤쪽에 쓰면 됨) - 외래키 삭제시 연결되어 있는 곳 NULL 값 지정
7. auto_increment - sequence
8. mysql 계정 암호화 해제하기
	ALTER USER 'scott'@'%' IDENTIFIED WITH mysql_native_password BY 'tiger';
```
### 17. MySQL - 함수
```
1. LIKE
	이름이 두번째 문자가 L인 사원명 출력
	SELECT ename 
	FROM emp
	WHERE ename LIKE ('_L%');

	이름에 L이 두 번 이상 포함된 사원명 출력
	SELECT ename 
	FROM emp
	WHERE ename LIKE ('%L%L%');
2. ROUND (n ) - 숫자 n을 소숫점 반올림
3. CEILING (n) - 가장 큰 정수
4. FLOOR (n) - 가장 작은 정수
5. TRUNCATE(n, i) - 숫자 n에서 i번째 기준으로 자르기
6. MOD (n2, n1) - n2에서 n1을 나눈 나머지 연산
7. POW (n2, n1) - n2의 n1 제곱값
8. SQRT (n) - n의 제곱근의 값
9. LOWER (str) - 알파벳을 소문자로 변환
10. UPPER (str) - 알파벳을 대문자로 변환
11. CONCAT (str1, str2) - 두 문자열을 연결
12. SUBSTRING (str, i, n) - 문자열 중 i번째에서 n개의 일부 문자를 선택
13. LENGTH (str) - 문자열의 길이
14. LEFT(str, i) / RIGHT(str, i) - 문자열에서 i길이만큼 반환
15. LPAD / RPAD (str, n, ch) - n 자리수 만큼 확보 후 빈 공백에 특정 문자로 채움
16. TRIM / LTRIM / RTRIM - 문자를 제거  (*)양쪽 공백 제거에 사용
17. REPLACE ( column, str1, str2 ) - 문자열에서 str1을 str2로 대신
18. CURDATE() - 년-월-일
19. CURTIME() - 시:분:초
20. NOW() - 년-월-일 시:분:초
21. SYSDATE() - 년-월-일 시:분:초
22. ADDDATE(날짜, 차이) - 날짜 + 차이
23. SUBDATE(날짜, 차이) - 날짜 - 차이
24. DATEDIFF(날짜1, 날짜2) - 날짜1 – 날짜2
25. TIMEDIFF(시간1, 시간2) - 시간1 – 시간2
26. TIMEDIFF(날짜1, 시간2) - 날짜1 – 시간2
27. DAYOFWEEK(날짜) - 요일 ( 일요일 : 1 ~ )
28. MONTHNAME(날짜) - 월이름
29. LAST_DAY(날짜) - 해당 달의 마지막 날
30. TIMESTAMPDIFF( MONTH | WEEK | DAY , 날짜1, 날짜2 ) - 날짜1과 날짜2의 차이
31. if / case end
	SELECT name, jumin,
	if(substring(jumin,8,1)='1','남','여') AS gender
	FROM info_tab;
	
	SELECT name, jumin,
		CASE substring(jumin,8,1)
			WHEN '1' THEN '남자'
			WHEN '3' THEN '남자'
			ELSE '여자'
		END AS gender
	FROM info_tab;
```
### 18. DB연동 - mysql
```
// 0. 필요한 변수
String driver = "com.mysql.cj.jdbc.Driver";
String url = "jdbc:mysql://175.114.130.8:3306/basic";
String user = "scott";
String pass = "tiger";

try {
	// 1. 드라이버 메모리 로딩
	Class.forName(driver);
	System.out.println("Driver 성공");

	// 2. 연결객체 얻어오기
	Connection con = DriverManager.getConnection(url, user, pass);
	System.out.println("Con 성공");

	// 3. 사용자 입력값을 받는다고 가정
	int empno = 4331;
	String ename = "그루트2";
	String job = "개발";
	int sal = 10000;
	int mgr = 7788;
	int sdeptno = 30;

	// 4. SQL 문장 만들기
	String sql = "INSERT INTO emp(empno, ename, job, sal, mgr, deptno) VALUES (?, ?, ?, ?, ?, ?)";
	System.out.println("문장 작성");

	// 5. 전송객체 얻어오기
	/*
	 * 		- statement : 완성된 sql 문장을 전송할 때
	 * 		- PreparedStatement : 미완성된 sql 문장을 전송할 때 
	 * 		- CallableStatement : pl-sql(function/procedure) 호출 할 때
	 */
	PreparedStatement ps = con.prepareStatement(sql);
	System.out.println("전송객체");

	// 6. 전송
	/*
	 * 		- executeUpdate() : INSERT, UPDATE, DELETE
	 * 			reutrn 값이 int형
	 * 		- executeQuery() : SELECT
	 * 			return 값이 결과집합
	 */
		ps.setInt(1, i);
		ps.setString(2, ename);
		ps.setString(3, job);
		ps.setInt(4, sal);
		ps.setInt(5, mgr);
		ps.setInt(6, sdeptno);
		ps.executeUpdate();
		System.out.println("SQL 전송");

	// 7. 닫기
	ps.close();
	con.close();

} catch (Exception e) {
	System.out.println("DB연동 실패: " + e.getMessage());
}
```
### 19. 트랜잭션 - java
```
// tranjection을 위해 auto commit 풀기
con.setAutoCommit(false);
// 잘못되었을 경우 rollback
con.rollback();
// 잘되었을 경우 commit
con.commit();
```
### 자바 JPA 세팅(setting) Insert 입력
```
	ORM (Object Relational Mapping)
		Object = 자바클래스 (VO or DTO)
		Relatinal - RDBMS (mysql, mariadb, oracle...) 의 테이블 관계
		객체와 테이블을 자동으로 매핑해주는 프레임워크
		ORM 표준은 JPA (Java Persistence API)
		ORM 중 하나로 Hibernate
			JPA : 개념
			Hibernate : 구현된 거
	pom.xml
		<!-- ### Lombok ### -->
		<dependency>
			<groupId>org.projectlombok</groupId>
			<artifactId>lombok</artifactId>
			<version>1.18.24</version>
			<scope>provided</scope>
		</dependency>

		<!-- https://mvnrepository.com/artifact/org.hibernate/hibernate-entitymanager -->
		<dependency>
			<groupId>org.hibernate</groupId>
			<artifactId>hibernate-entitymanager</artifactId>
			<version>5.4.9.Final</version>
		</dependency>

		<!-- https://mvnrepository.com/artifact/org.mariadb.jdbc/mariadb-java-client -->
		<dependency>
			<groupId>org.mariadb.jdbc</groupId>
			<artifactId>mariadb-java-client</artifactId>
			<version>2.6.2</version>
		</dependency>
	리소스 xml 파일 생성
		META-INF
			persistence.xml
				<?xml version="1.0" encoding="UTF-8"?>

				<persistence version="2.1" xmlns="http://xmlns.jcp.org/xml/ns/persistence"
					xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
					xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/persistence
							http://xmlns.jcp.org/xml/ns/persistence/persistence_2_1.xsd">
				
					<!-- * 영속성 유닛 설정 : 여기 지정한 name값으로 찾음 -->
					<persistence-unit name="aBasic">
					
						<!-- JPA 속성 설정 -->
						<properties>
							
							<!-- 마리아디비 -->
							<property name="javax.persistence.jdbc.driver" value="org.mariadb.jdbc.Driver"/>
							<property name="javax.persistence.jdbc.user" value="scott"/>
							<property name="javax.persistence.jdbc.password" value="tiger"/>
							<property name="javax.persistence.jdbc.url" value="jdbc:mariadb://127.0.0.1:3306/basic"/>
							
							<!-- JPA 구현체 설정 -->
							<property name="hibernate.dialect" value="org.hibernate.dialect.MariaDB103Dialect"/>
							
							<!-- 옵션 sql문장 확인 -->
							<property name="hibernate.show_sql" value="true"/> <!-- 콘솔에 sql 문 확인 가능 -->
							<property name="hibernate.hbm2ddl.auto" value="update"/> <!-- 무조건 update 로 -->
							
							<!-- MySQL -->
							
						</properties>
				
					</persistence-unit>
				
				</persistence>
	EmpVO
		package com.javassem.domain;

		import java.util.Date;
		
		import javax.persistence.Column;
		import javax.persistence.Entity;
		import javax.persistence.GeneratedValue;
		import javax.persistence.GenerationType;
		import javax.persistence.Id;
		import javax.persistence.Table;
		
		import lombok.Data;
		
		@Data
		@Entity
		@Table(name = "emp_d")
		public class EmpVO3 {
			@Id
			@GeneratedValue(strategy = GenerationType.IDENTITY) // auto_increment
		//	@GeneratedValue(strategy = GenerationType.SEQUENCE) // emp_b_seq
			private Integer empNo;
			
			@Column(length = 30) // varChar(30)
			private String eName; 
			
			@Column(length = 50, nullable = true) // varChar(30) not null
			private String job;
			private Integer mgr;
			
			@Column(name = "hire_date") // 테이블 컬럼명
			private Date hiredate;
			private Integer comm;
			
			@Column(precision = 5)
			private Integer sal;
			
			private Integer deptNo;
		}
	main
		import java.util.Date;
		
		import javax.persistence.EntityManager;
		import javax.persistence.EntityManagerFactory;
		import javax.persistence.EntityTransaction;
		import javax.persistence.Persistence;
		
		import com.javassem.domain.EmpVO3;
		
		public class EmpMain2 {
			public static void main(String[] args) {
				// 1. 엔티티 매니저 팩토리 생성
				EntityManagerFactory emf = Persistence.createEntityManagerFactory("aBasic");
				
				// 2. 엔티티 매니저 생성
				EntityManager em = emf.createEntityManager();
				
				// 4. 엔티티 트랜잭션 생성
				EntityTransaction tx = em.getTransaction();
				
				try {
					
					// 3. 엔티티 생성
					EmpVO3 empVO = new EmpVO3();
					empVO.setEName("홍길순");
					empVO.setJob("개발자");
					empVO.setHiredate(new Date());
					empVO.setDeptNo(77);
					empVO.setSal(3000000);
					
					tx.begin();
					em.persist(empVO);
					tx.commit(); // 커밋
					
				} catch (Exception e) {
					tx.rollback(); // 롤백
					System.out.println("실패: " + e.getMessage());
				}
			}
		}

	
```
### 자바 JPA 머지(Merge) 없으면 입력 있으면 수정
```
	main
		import javax.persistence.EntityManager;
		import javax.persistence.EntityManagerFactory;
		import javax.persistence.EntityTransaction;
		import javax.persistence.Persistence;
		
		import com.javassem.domain.EmpVO;
		
		public class EmpMerge {
			public static void main(String[] args) {
				// 1. 엔티티 매니저 팩토리 생성
				EntityManagerFactory emf = Persistence.createEntityManagerFactory("bContextState");
				
				// 2. 엔티티 매니저 생성
				EntityManager em = emf.createEntityManager();
				
				// 4. 엔티티 트랜잭션 생성
				EntityTransaction tx = em.getTransaction();
				
				try {
					EmpVO emp = new EmpVO();
					emp.setEmpNo(6666);
					emp.setEName("홍설이");
					
					tx.begin();
					em.merge(emp);
					tx.commit();
					
				} catch (Exception e) {
					tx.rollback(); // 롤백
					System.out.println("실패: " + e.getMessage());
				}
			}
		}
```
### 자바 JPA 검색(Select)
```
	main
		import java.util.List;
		
		import javax.persistence.EntityManager;
		import javax.persistence.EntityManagerFactory;
		import javax.persistence.EntityTransaction;
		import javax.persistence.Persistence;
		
		import com.javassem.domain.EmpVO;
		
		public class EmpSelect {
			public static void main(String[] args) {
				// 1. 엔티티 매니저 팩토리 생성
				EntityManagerFactory emf = Persistence.createEntityManagerFactory("bContextState");
				
				// 2. 엔티티 매니저 생성
				EntityManager em = emf.createEntityManager();
				
				// 4. 엔티티 트랜잭션 생성
				EntityTransaction tx = em.getTransaction();
				
				try {
					// find() 검색
					EmpVO emp0 = em.find(EmpVO.class, 9999);
					System.out.println("검색결과: " + emp0.toString());
					System.out.println("============================");
					
		//			EmpVO emp1 = em.find(EmpVO.class, 3333);
		//			System.out.println("검색결과1: " + emp1.toString());
		//			System.out.println("============================");
					
					// getReference()
					EmpVO emp2 = em.getReference(EmpVO.class, 9999);
					System.out.println("검색결과2: " + emp2.toString());
					System.out.println("============================");
					
		//			EmpVO emp3 = em.getReference(EmpVO.class, 1212);
		//			System.out.println("검색결과3: " + emp3.toString());
		//			System.out.println("============================");
					
					// JPQL (Java Persistence Query Language)
					// SQL 문장이 아님
					//		테이블명이 아니라 클래스명(대소문자 구별)
					// SELECT * FROM emp_a ORDER BY empNo DESC
					String jpql = "SELECT empVO FROM EmpVO empVO ORDER BY empVO.empNo DESC";
					List<EmpVO> empList = em.createQuery(jpql, EmpVO.class).getResultList();
					
					for(EmpVO vo : empList) {
						System.out.println(">>> " + vo.toString());
					}
					
					
				} catch (Exception e) {
					tx.rollback(); // 롤백
					System.out.println("실패: " + e.getMessage());
				}
			}
		}
```
### 자바 JPA 수정(Update)
```
	main
		import javax.persistence.EntityManager;
		import javax.persistence.EntityManagerFactory;
		import javax.persistence.EntityTransaction;
		import javax.persistence.Persistence;
		
		import com.javassem.domain.EmpVO;
		
		public class EmpDetached {
			public static void main(String[] args) {
				// 1. 엔티티 매니저 팩토리 생성
				EntityManagerFactory emf = Persistence.createEntityManagerFactory("bContextState");
				
				// 2. 엔티티 매니저 생성
				EntityManager em = emf.createEntityManager();
				
				// 4. 엔티티 트랜잭션 생성
				EntityTransaction tx = em.getTransaction();
				
				try {
					// 엔티티 컨테이너에 있는 상태 (Managed 상태)
					EmpVO emp1 = em.find(EmpVO.class, 8888);
					System.out.println("검색결과1: " + emp1.toString());
					
					// 검색 후 수정 가능
					tx.begin();
					emp1.setEName("홍홍이변경2"); 
					tx.commit();
					
					tx.begin();
					em.detach(emp1); // 관리 벗어나기
					emp1.setEName("홍홍이"); 
					tx.commit();
				} catch (Exception e) {
					tx.rollback(); // 롤백
					System.out.println("실패: " + e.getMessage());
				}
			}
		}
```
### 자바 JPA 삭제(Delete)
```
	main
		import javax.persistence.EntityManager;
		import javax.persistence.EntityManagerFactory;
		import javax.persistence.EntityTransaction;
		import javax.persistence.Persistence;
		
		import com.javassem.domain.EmpVO;
		
		public class EmpDelete {
			public static void main(String[] args) {
				// 1. 엔티티 매니저 팩토리 생성
				EntityManagerFactory emf = Persistence.createEntityManagerFactory("bContextState");
				
				// 2. 엔티티 매니저 생성
				EntityManager em = emf.createEntityManager();
				
				// 4. 엔티티 트랜잭션 생성
				EntityTransaction tx = em.getTransaction();
				
				try {
					// 삭제를 위한 검색
					EmpVO emp = em.find(EmpVO.class, 9999);
					
					tx.begin();
					em.remove(emp); // 검색 후 삭제
					tx.commit();
				} catch (Exception e) {
					tx.rollback(); // 롤백
					System.out.println("실패: " + e.getMessage());
				}
			}
		}
```
### 자바 JPA BoardVO 숙제
```
	main
		import java.util.Date;
		import java.util.List;
		
		import javax.persistence.EntityManager;
		import javax.persistence.EntityManagerFactory;
		import javax.persistence.EntityTransaction;
		import javax.persistence.Persistence;
		import javax.persistence.TypedQuery;
		
		import jpaContextHomeWork.vo.BoardVO;
		
		public class Main {
		
			public static void main(String[] args) {
				EntityManagerFactory emf = Persistence.createEntityManagerFactory("board_homework");
				EntityManager em = emf.createEntityManager();
				EntityTransaction tx = em.getTransaction();
				
				try {
					// 입력
					BoardVO boardVO = new BoardVO();
					boardVO.setSeq(1);
					boardVO.setTitle("1");
					boardVO.setWriter("20");
					boardVO.setContent("1");
					boardVO.setRegDate(new Date());
					boardVO.setCnt(0);
					
					tx.begin();
		//			em.persist(boardVO); // 입력
					em.merge(boardVO); // 없으면 입력 있으면 수정
					tx.commit();
					
					// 1개검색
					boardVO = em.find(BoardVO.class, 1);
					System.out.println("1개 검색결과: " + boardVO.toString());
					
					// 전체검색
					String jpql = "SELECT boardVO FROM BoardVO boardVO ORDER BY boardVO.seq DESC";
					List<BoardVO> boardList = em.createQuery(jpql, BoardVO.class).getResultList();
					
					for (BoardVO vo : boardList) {
						System.out.println(vo.toString());
					}
					
					// 이름 검색
					String writer = "20";
					jpql = "SELECT boardVO FROM BoardVO boardVO WHERE boardVO.writer =?1";
					TypedQuery<BoardVO> query = em.createQuery(jpql, BoardVO.class);
					query.setParameter(1, writer);
					boardVO = query.getSingleResult();
					
					System.out.println("1개 검색결과2: " + boardVO.toString());
					
					
				} catch (Exception e) {
					System.out.println("실패: " + e.getMessage());
				}
			}
		
		}
```
### 자바 JAVA JPA
```
	Department
		package com.javassem.domain;

		import java.util.ArrayList;
		import java.util.List;
		
		import javax.persistence.CascadeType;
		import javax.persistence.Entity;
		import javax.persistence.Id;
		import javax.persistence.OneToMany;
		import javax.persistence.Table;
		
		import lombok.Data;
		
		@Data
		@Entity
		@Table(name = "dept")
		public class Department {
			@Id
			//@GeneratedValue(strategy = GenerationType.IDENTITY) // MYSQL, mariaDB
			//@GeneratedValue(strategy = GenerationType.SEQUENCE) // ORACLE
			private Integer deptNo;
			private String dName;
			private String loc;
			
			// 케스케이드 삭제
			@OneToMany(mappedBy = "dept", cascade = {CascadeType.PERSIST, CascadeType.REMOVE})
			private List<Employee> empList = new ArrayList<Employee>();
		}
	Employee
		package com.javassem.domain;

		import java.util.Date;
		
		import javax.persistence.Entity;
		import javax.persistence.Id;
		import javax.persistence.JoinColumn;
		import javax.persistence.ManyToOne;
		import javax.persistence.Table;
		
		import lombok.Data;
		
		@Data
		@Entity
		@Table(name = "emp")
		public class Employee {
			@Id
			private Integer empNo;
			private String eName;
			private String job;
			private Integer mgr;
			private Date hiredate;
			private Integer sal;
			private Integer comm;
			
			/*
			외래키 
			private Integer deptNo;
			*/
			@ManyToOne(optional = true) // INNER JOIN
			@JoinColumn(name = "deptNo") // 만일 이 코드 없으면 자동으로 테이블명_컬럼명에 해당하는 새로운 컬럼이 생성되고 그 컬럼과 조인함
			private Department dept;
			
		}
	Main
		import java.util.List;

		import javax.persistence.EntityManager;
		import javax.persistence.EntityManagerFactory;
		import javax.persistence.EntityTransaction;
		import javax.persistence.Persistence;
		
		import com.javassem.domain.Department;
		import com.javassem.domain.Employee;
		
		public class MainApp {
		
			public static void main(String[] args) {
				EntityManagerFactory emf = Persistence.createEntityManagerFactory("cReference");
				
				try {
					// 입력 함수
		//			insertData(emf);
					
					// 검색 함수
		//			selectData(emf);
					
					// 수정 함수
		//			modifyData(emf);
					
					// 삭제 함수
		//			deleteData(emf);
					
					// OneToMany 검색
					selectOneToMany(emf);
				} catch (Exception e) {
					System.out.println("실패: " + e.getMessage());
				}
			}
			
			static void insertData(EntityManagerFactory emf) {
				EntityManager em = emf.createEntityManager();
				EntityTransaction tx = em.getTransaction();
				
				tx.begin();
				
				// 사원 정보 입력 - 부서번호가 없는 경우
				Employee emp1 = new Employee(); // 객체 생성
				
		//		emp1.setEmpNo(101);
		//		emp1.setEName("정민기");
		//		emp1.setDeptNo(60);
		//		em.persist(emp1); // 입력
				
				// 부서번호입력 - 자동증가수
		//		Department dept1 = new Department();
		//		dept1.setDeptNo(70);
		//		dept1.setDName("운영팀");
		//		dept1.setLoc("신촌");
		//		em.persist(dept1);
		//		
		//		Employee emp2 = new Employee();
		//		emp2.setEmpNo(102);
		//		emp2.setEName("맹돌이");
		//		emp2.setDept(dept1);
		//		em.persist(emp2);
				
				// 기존에 40번부서의 직원으로 등록하려면????
				Department dept2 = em.find(Department.class, 40);
				System.out.println(dept2.toString());
				
				Employee emp3 = new Employee();
				emp3.setEmpNo(103);
				emp3.setEName("맹구");
				emp3.setDept(dept2);
				em.persist(emp3);
				
				tx.commit();
				em.close();
				
			}
			
			static void selectData(EntityManagerFactory emf) {
				EntityManager em = emf.createEntityManager();
				
				Employee emp1 = em.find(Employee.class, 5555);
				
				System.out.println(emp1.getEName() + "님 정보");
				System.out.println(emp1.getEName() + "님 부서는 " + emp1.getDept().getDName());
				
			}
			
			static void modifyData(EntityManagerFactory emf) {
				EntityManager em = emf.createEntityManager();
				EntityTransaction tx = em.getTransaction();
				
				tx.begin();
				
				// 3902 사원 정보
				Employee emp1 = em.find(Employee.class, 3902);
				System.out.println(emp1.toString());
				
				// 40번 부서로 변경하려면?
				Department dept1 = em.find(Department.class, 40);
				System.out.println(dept1.toString());
				
				emp1.setDept(dept1); // 수정
				System.out.println(emp1.toString());
				
				tx.commit();
			}
			
			static void deleteData(EntityManagerFactory emf) {
				EntityManager em = emf.createEntityManager();
				EntityTransaction tx = em.getTransaction();
				
				tx.begin();
				
				// 40번 부서를 삭제한다면?
		//		Department dept1 = em.find(Department.class, 40);
		//		System.out.println(dept1);
		//		em.remove(dept1);
				
				// 부서에 대한 참조를 제거 후 삭제
		//		Employee emp1 = em.find(Employee.class, 100);
		//		emp1.setDept(null);
		//		System.out.println(emp1.toString());
		//		
		//		Department dept2 = em.find(Department.class, 50);
		//		em.remove(dept2);
				
				// cascade : 영속성전이
				// 케스케이드 삭제
				Department dept3 = em.find(Department.class, 40);
				em.remove(dept3);
				
				tx.commit();
			}
			
			static void selectOneToMany(EntityManagerFactory emf) {
				EntityManager em = emf.createEntityManager();
				
				Department dept = em.find(Department.class, 30);
		//		System.out.println("부서명: " + dept.getDName());
				
				// toString() 사용 못함
		//		System.out.println("부서정보: " + dept.toString());
				
				List<Employee> emp_list = dept.getEmpList();
				for (Employee e : emp_list) {
					System.out.println("30번 부서 이름: " + e.getEName());
				}
				
				em.close();
			}
		}
```
### 20. HTML/CSS
```
웹에서 메소드 : 전송방식 (get/post)
	get : http(네트워크의 전송규칙)에 헤더부분에 url로 데이타를 전송
	post : http(네트워크의 전송규칙)에 바디부분으로 데이타를 전송
1. Text 꾸미기
	태그
	<br> - 개행
	<b>진하게</b><br/>
	<strong>중요한</strong><br/>
	<em>강조</em><br/>
	<i>이태릭체</i><br/>
	<b><i>이태릭체</i></b><br/>
	<mark>하이라이팅</mark><br/>
	보통문자 <small>한단계 작은 문자</small><br/>
	보통문자 <sub>아래 첨자</sub><br/>
	보통문자 <sup>윗첨자</sup><br/>
	<ins>추가문자</ins><br/>
	<del>삭제문자</del><br/>
	&nbsp; - 띄어쓰기
	<label> - user Interface의 제목 역
2. form
	method - get(url에 parameter가 보임), post(url에 parameter가 안 보임)
	target - _blank(새창에서 페이지를 띄움), _parent(부모의 창에서 페이지를 띄움)
	<form action="#" >
		날짜: <input type="date" min="2011-11-01" max="2011-12-31" step="1" value="2011-11-11"/> <br/>
		범위: <input type="range" min="0" max="100" step="1" value="50"/> <br/>
		숫자: <input type="number" min="0" max="100" step="1" value="50"/> <br/>
		검색: <input type="search"/> <br/>
		URL: <input type="url" list="url_list"/>	<br/>
		메일: <input type="email"/> <br/>
		힌트문자: <input type="text" placeholder="이름을 입력하세요"/> <br/>
		자동포커스: <input type="text" autofocus/> <br/>
		빈값검사: <input type="text" required/> <br/>
		정규표현식: <input type="text" pattern="(010|011)-\d{3,4}-\d{4}"/> <br/>
		<input type="submit" value="Submit"/> 
	</form>
3. 선택자
	E - 가중치 1
	E#idname - 가중치 100
	E.classname - 가중치 10
	input[type="text"] - input에서 text속성
	E F - (자손)
	E > F - (자식)
	E + F - (바로다음)
	E ~ F - (형제) 
	p:nth-of-type(2) - 부모로부터 2번째 <p>요소	
4. CSS
	overflow: auto - 보더 지정 후 텍스트 수가 그 칸을 벗어나면 스크롤이 생김
	position: absolute - 위치를 절대값으로 바꿔 줌
	position: fixed - 스크롤을 내려도 그 위치에 있음
	display: inline-block - 개행되지 않게 끔
	div:nth-of-type(odd):hover - hover 는 마우스가 올려져있을 때
	align-content: center - 위 아래 가운데 배치하기
	z-index: -4 - 그림이 앞쪽에 보이거나 뒤에 보이거나 순서를 정할 수 있음
	text-align - 글자 정렬
	text-decoration - <a>태그 밑줄 제거
	border-style - dotted, dashed, solid, double, groove, ridge, inset, outset, inherit
	border-width - 외곽선 두께
	opacity: 0.9 - 투명도 /* 0.0 ~ 1.0 */
	
	
<!-- 반응형 웹 원리 - 설정을 해줘야 함 -->
	header -
	left - float: left / 왼쪽 메뉴 영역
	right - float: right / 오른쪽 콘텐츠 영역
	footer - clear: both / 푸터 영역
	<style type="text/css" media="screen and (max-width: 500px)">
		#left{
			display: none;
		}
		
		#content {
			float: left;
		}
	</style>
	width: 50%;
	-webkit-transition-property: width;
	-webkit-transition-duration: 2s;
<!-- 프린트한다면 -->
<style type="text/css" media="print">
	#left, #footer, #header {
		display: none;
	}
	#content {
		float: left;
	}
</style>
```
### 21. JavaScript
```
[참고]
	변수를 설정해놓고 밑에서 또 선언해도 잘 작동함. - 그래서 최근에는 let(변수)으로 변수를 설정한다.
	자바와 다르게 들어가는 값에 따라서 자료형이 결정이 됨.
	const(상수)로 변수를 설정해도 배열안에 원소 값은 변경 가능
	if 안에서 0은 false 나머지 모든 숫자는 true
	문자열 비교할 때 자바와 다르게 값 그대로를 비교
	문자 "10" == 숫자 10 은 같음 / ===으로 비교하면 다름
	string == string 을 하면 주소 값이 아닌 값 자체를 비교함
	NaN(Not a Number)
	귀찮게 반복되는 멤버변수를 지정하고 싶을때는 myForm['txt'+i] 이용하기
		for (let i = 0; i < 4; i++) {
			document.myForm['txt'+i].value = "홍길동" + i;	
		}
[참고]
	자바 스크립트인 경우 소문자 대문자로 메소드와 클래스를 구별한다!
   	1. 함수
 			(1) 선언
 				function func(){}
 			(2) 호출
 				func();
 		2. 클래스
 			(1) 선언
 				function student(){}
 			(2) 객체 생성
 				var s = new Student();

1. 변수 설정 
	var byeunsu = "문자열";
	let byeunsu - 변수
	const byeunsu - 상수
2. for
	for(var i = 0; i < arr.length; i++)
	for(var i in arr) - i가 출력
	for(var i of arr) - 값이 출력
3. 함수
	console.log("변수의 값: " + byeunsu + "<br/>"); - 콘솔창 출력
	document.writeln("변수의 값: " + byeunsu); - 웹화면 출력
	location - url 이동
	alert - 경고 메세지
	confirm("이 페이지는 이사갑니다. 이동할까요?") - true, false 값을 받을 수 있음
	prompt("원하는 사이트를 입력하세요") - 값을 입력 받을 수 있음
	let userName = document.forms[0].username.value - form 태그로 찾기
	var userName = document.frm.username.value - 화면 form name속성으로 찾기
	
	arr.join('/') - /기호로 나누기
	arr.slice(3) - 자르기
	arr.reverse() - 순서 반대로
	arr.sort() - 오름차순정렬 / *문자만 정렬
	arr.concat(arrTemp) - 배열에도 콘캣함수가 적용되지만 원본에는 영향을 주지 않음
	arr.pop() - 스택 : 후입선출
	arr.shift() - 큐 : 선입선출
	arr.forEach( function(value, index) { - forEach 함수 문법 / 리턴 값이 없음
		document.write(index + " : " + value + "<br/>");
	});
	var result = arr.map(function(value, index) { - map 함수 문법 / 리턴 값이 있음
		return value * index;
	});
	
Map - 키, 발루
	for (let [key, v] of m) {
		/* document.write(`${key} : ${v} '<br/>'`); */
		if( key === inputId & v === inputPw){
			document.write(`<h1>로그인 성공</h1>`);
			break;
		}
	}
Set - 발루
	for (let v of s) {
		document.write(`${v} <br/>`);
	}
Date - 날짜
	var d = new Date('2023/08/15');
	document.writeln( d  + '<br/>');
	document.writeln( d.getYear()  + '<br/>');
	document.writeln( d.getFullYear()  + '<br/>');
	document.writeln( d.getMonth()  + '<br/>');
	document.writeln( d.getDate()  + '<br/>');
	document.writeln( d.getDay()  + '<br/>');
마지막 날짜
	d.setDate(0);
날짜 계산
	var diff = (eDate - sDate)/(1000*60*60*24); // 1000=초단위, 60=분단위, 60=시간단위, 24=일단위
패턴
	var p = /http(s)?:\/\/([\w-]+\.)+[\w-]+(\/[\w-.\/?%&=]*)?/gi;
	var result = str.match(p);
	for (var i = 0; i < result.length; i++) {
		document.write(`${result[i]}<br/>`);
	}

이벤트
	// [1] HTML에서 이벤트 함수를 호출
	function btn_click() {
		alert('이벤트발생');
	}
	// [2] 윈도우가 업로드 될 때까지 기다리고 이벤트 실행
	window.onload = function() {
		// [2] 이벤트 핸들러 방식 : html과 js 분리
		document.getElementById('btn').onclick = function() {
			alert(`이벤트2`);
		}	
	}
	// [3] 윈도우가 업로드 될 때까지 기다리고 이벤트 실행
	window.onload = function() {
		// [3] 이벤트 리스터 방식
		document.getElementById('btn').addEventListener('click', btn_click);
		
		function btn_click() {
			alert('이벤트3');
		}
	}
```
### 22. JQuery
$선택자로 가져와서 css 주기
```
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.7.1/jquery.min.js"></script>
<script type="text/javascript">
	$(function() {
		var h = $('#here');
		/*
		h.click(function() {
			h.text('클릭하면 글씨 변경');	
		});
		
		h.mouseenter(function() {
			h.text('마우스 들어감');
		});
		
		h.mouseleave(function() {
			h.text('마우스 나감');
		});
		
		h.hover(function() {
			h.css(
				{'background':'pink'}	
			);
		}, function() {
			h.css(
				{'background':'yellow'}	
			);
		})
		*/
		/* h.fadeOut(2000).fadeIn(2000); */
		h.slideUp(2000).slideDown(2000);
		
		let s = $('#student');
		var a = s.find('#age');
		a.css({'color':'#654321', 'font-size':'30px','background':'white'});
	});
```
```
	// 화면이 로딩 될 때까지 기다림
	$(function() {
		let man = $('.man'); // 화면에서 man이라는 클래스를 가진 태그를 가져옴
		// 가져온 태그의 글씨색깔을 분홍색으로 변경
		man.css( 
			{'color':'pink'}
		);
		// 가져온 태그의 글씨색깔을 분홍색으로 변경 끝
		// 위랑 같음
		let woman = $('.woman');
		woman.css(
			{'background':'yellow'}
		);
		// 위랑 같음 끝
		// 화면에 li태그를 클릭했을 때
		$('li').click(function(){
			alert($(this).text()); // 각 li에 해당하는 태그 안쪽 글자
			$(this).text("반갑습니다."); // 각 li에 해당하는 태그 안쪽 글자를 반갑습니다 로 변경
		});
		// 화면에 li태그를 클릭했을 때 끝
		
	});
	// 화면이 로딩 될 때까지 기다림 끝
	// 화면이 로딩 될 때까지 기다림
	$(function(){
		let redBox = $('.inputText'); // inputText 클래스를 가져옴
		// 포커싱이 되었을 때
		redBox.focus(function(e){
			$(this).addClass('active'); // 각 포커싱이 된 inputText에 속성 class="active" 를 추가
			/*alert('OK');
			e.preventDefault();*/
		});
		// 포커싱이 되었을 때 끝
		// 포커싱이 없어졌을 때
		redBox.blur(function(e){
			$(this).removeClass('active');
		});
		// 포커싱이 없어졌을 때 끝
	});
	// 화면이 로딩 될 때까지 기다림 끝
	// 화면이 로딩 될 때까지 기다림
	$(function(){
		$('#divText').click(function(){
			$('#divText').text('<img src="images/grim.jpg">');
		});
		$('#divHtml').click(function(){
			$('#divHtml').html('<img src="images/grim.jpg">');
		});
		$('#divEmpty').click(function(){
			$('#divEmpty').empty();
		});
		$('#changeGrim').click(function(){
			$('#changeGrim').attr('src', 'images/cat.jpg');
		});
		$('#changeGrim').click(function(){
			let src = $('#changeGrim').attr('src');
			$('#changeGrim').attr('src', src.replace('puppy', 'cat'));
			
		});
		
	});
	// 화면이 로딩 될 때까지 기다림 끝
	// 화면이 로딩 될 때까지 기다림
	$(function(){
		$('#check').click(function(){
			let name = $('#tf');
			let messege = $('#ta');
			let addr = $('#sel');
			let island = $('#sel_m option:selected');
			let islandStr = "";
			let gender = $('input[name=gender]:checked');
			let love = $('input[name=love]:checked');
			
			let result = $('#result');
			
			for(let i=0; i<island.length; i++){
				islandStr += island[i].value + " ";	
			}
			result.html("이름: " + name.val() + "<br/>메세지: " + messege.val() + "<br/>주소: " + addr.val() + "<br/>섬: " + islandStr + "<br/>성별: " + 				gender.val() + "<br/>애인: " + love.val());
			
		});
	});
	// 화면이 로딩 될 때까지 기다림 끝
	// 화면이 로딩 될 때까지 기다림 
	$(function(){
		$('#init').click(function(){ // 초기화 버튼을 클릭했을 때
			let name = $('#tf');
			let messege = $('#ta');
			let addr = $('#sel');
			let island = $('#sel_m');
			let gender = $('input[name=gender]');
			let love = $('input[name=love]');
			
			name.val('내 이름은 홍길동입니다.');
			messege.val('작성중....');
			addr.val('마산');
			island.val(['제주도', '거제도']);
			gender.eq(1).prop('checked', 'true');
			love.eq(0).prop('checked', 'true');
		});
	});
	// 화면이 로딩 될 때까지 기다림 끝
	// 5번
	$(function(){
		/*
			부모/자식 관계 맺기
				부모.append(자식)
				자식.appendTo(부모)
		*/
		let actor = $('#actor');
		let tae = $('#tae');
		let su = $('#su');
		let bin = $('#bin');
		
		actor.append(tae);
		su.appendTo(actor);
		/*
			let n = $('div');
			let n = $('#div');
			let n = $('.div');
			let n = $('div'); // 화면에 있는 div 요소를 선택하여 변수 n이 가리킴
			let n = $('<div/>'); // div 요소의 객체에 메모리 상에 생성하고 변수 n이 가리킴
		*/
		let n = $('<div/>');
		n.text('한배우'); // <div>한배우</div>
		actor.append(n);
		actor.append($('<div>두배우</div>')); // <div>두배우</div>
		
	});
	
	// 6번
	$(function(){
		$('.data').click(function(){
			alert($(this).html());
		});
	});
```
```
	// 화면이 로딩 될 때까지 기다림
	$(function() {
		// 첫 요소
		//$('ul li').first().addClass('borderRed'); // ul 자손 li 중 첫 번째
		//$('ul').find('li').eq(0).addClass('borderRed'); // ul에서 find로 li를 찾고 eq로 그중 첫번째
		//$('ul > li:eq(0)').addClass('bg'); // ul 자식 1개 li 첫번째
		$('ul > li:nth-child(1)').addClass('bg'); // ul 자식 모든 li 첫 번째 
		
		// 음식 중 세번째 요소
		$('ul#food > li:eq(2)').addClass('borderRed'); // ul 태그 중 id가 food 인 ul 자식 li 중에서 세 번째 li에 클래스를 추가
		
		// 술 중에서 두번째 요소
		$('ul:nth-of-type(2) > li:nth-of-type(2)').addClass('borderRed'); // 두 번째 ul 자식 li 중 2번 째
		
		// 튀김을 포함한 요소
		//$('li:contains("튀김")').addClass('borderRed'); // 튀김을 포함한 li
		let l = $('li').text();
		for(let i=0; l.length; i++){
		}
			
		 
	});
	// 화면이 로딩 될 때까지 기다림 끝
```
```
	// 화면이 로딩 될 때까지 기다림
	$(function() {
		// 원래 이벤트 처리
		/*
		$('li').bind('click', function(){
			$('#result').html($(this).html());
			//$('#result').text($(this).text());
		});
		*/
		// 축약형
		// li를 클릭했을 때
		$('li').click(function(evt){
			$('#result').text($(this).text());
			for(let prop in evt){
				console.log( prop + "=" + evt[prop]);
			}
		});
		// // li를 클릭했을 때 끝
		
		$('h1').css({'cursor':'pointer'}); // 해당하는 곳에 마우스를 갖다대면 손가락 모양으로 바뀜
		
		// h1 태그 클릭 (동적으로 li를 추가했는데 이벤트가 위쪽에 먹히지 않음)
		$('h1').click(function(){
			let li = $('<li></li>'); // li 태그 추가
			li.text(new Date()); // li 태그에 날짜를 추가
			$('ul').append(li); // ul의 자식으로 추가
			$('li').css({'cursor':'pointer'}); // 해당하는 곳에 마우스를 갖다대면 손가락 모양으로 바뀜
			
		});
		
		// 동적으로 생성된 요소의 이벤트 처리
		$('ul').on('click','li', function(){
			$('#result').text($(this).text());
		});
		// 동적으로 생성된 요소의 이벤트 처리 끝
	});
	// 화면이 로딩 될 때까지 기다림 끝
```
```
	// 화면 완료 후
	$(function() {
		// 테이블에서 짝수행을 css 적용
		$('#celebs > table.data > tbody tr:odd').addClass('table_striping');
	
		// 테이블에 마우스가 올라갔을 때 td_mouseover 클래스 속성을 적용하고
		$('#celebs > table.data > tbody tr').mouseenter(function() {
			//$(this).addClass('td_mouseover');
			$('#celebs > table.data > tbody tr:hover').addClass('td_mouseover');
		});
	
		// 마우스가 내려가면 td_mouseover 클래스 속성을 제거
		$('#celebs > table.data > tbody tr').mouseleave(function() {
			//$(this).removeClass('td_mouseover');
			$('#celebs > table.data > tbody tr').removeClass('td_mouseover');
		});
	
		// 감추기 버튼이 눌려졌을 때
		$('#hideButton').click(function() {
			//$('#intro img').fadeOut(2000); // 2초동안 사라짐
			$('#intro img').slideUp(2000); // 2초동안 위 왼쪽으로 사라짐
		});
		
		// 보이기 버튼이 눌려졌을 때
		$('#showButton').click(function() {
			//$('#intro img').fadeIn(1); // 0.001초동안 나타남
			$('#intro img').slideDown(2000); // 2초동안 위 왼쪽에서 나타남
		});
		
		// 감추기/보이기 버튼이 눌려졌을 때
		$('#toggleButton').click(function() {
			//$('#intro img').toggle(2000); // 감추기/보이기 둘다
			//$('#intro img').fadeToggle(2000); // 감추기/보이기 둘다
			//$('#intro img').slideToggle(2000); // 감추기/보이기 둘다
			// 함수 이용 없이
			let img = $('#intro img'); // 이미지 가져오기
			if(img.is(':visible')){ // 이미지가 보일때
				img.fadeOut(1000); // 이미지 사라지게
				$(this).val('보이기'); // 버튼의 글씨는 보이기로
			}else{ // 이미지가 안보일때
				img.fadeIn(1000);
				$(this).val('안보이기');
			}	
			
		});
	
	});
```
```
	$(function(){
		// img 위에 마우스를 올려놨을때
		$('.header .menu .rollover img' ).hover(function(){
			$(this).attr('src', $(this).attr('src').replace('off', 'on')); // 해당 이미지에 속성 src 를 바꾸는데 해당이미지의 src 속성에 들어있는 글자를 가져와서 off 를 on으로 바꾼다 
		}
		// img 위에 마우스를 올려놨을때 끝
		// img 위에서 마우스가 벗어 났을 때
		 , function(){
			$(this).attr('src', $(this).attr('src').replace('on', 'off')); // 해당 이미지에 속성 src 를 바꾸는데 해당이미지의 src 속성에 들어있는 글자를 가져와서 on 을 off로 바꾼다
		});
		// img 위에서 마우스가 벗어 났을 때 끝
	});
```
```
	$(function(){
		// 2초 동안 여백이 20px 글씨크기가 30px 로 바뀐다 
		$('p#intro').animate({ 
			padding : '20px',
			fontSize : '30px'
		}, 2000);
		// 2초 동안 여백이 20px 글씨크기가 30px 로 바뀐다 끝
		// 마우스를 올려놨을 때 2초 동안 왼쪽 여백이 15 증가 마우스를 내려놨을 때는 그 반대로 움직인다
		$('#navigation a').hover(function(){
			$(this).animate({
				paddingLeft : '+=15px'
			}, 2000);
		}, function(){
			$(this).animate({
				paddingLeft : '-=15px'
			}, 2000);
		});
		// 마우스를 올려놨을 때 2초 동안 왼쪽 여백이 15 증가 마우스를 내려놨을 때는 그 반대로 움직인다 끝
	});
```
```
	$(function(){
		// +버튼을 클릭했을 때
		$('.fontSize button:eq(0)').click(function(){
			$('#txt').animate({
				color: 'white',
				fontSize: '+=10px',
				color: 'black'
			}, 1000);
		});
		// +버튼을 클릭했을 때 끝
		// -버튼을 클릭했을 때
		$('.fontSize button:eq(1)').click(function(){
			$('#txt').animate({
				color: 'white',
				fontSize: '-=10px',
				color: 'black'
			}, 1000);
		});
		// -버튼을 클릭했을 때 끝
		// 글씨체 바꾸기
		$('#fontstyle').change(function(){
			$('#txt').css({
				'font-family':$(this).val()
			});
		});
		// 글씨체 바꾸기 끝
	});
```
```
	// Example
	$(function(){
		// +버튼을 클릭했을 때
		$('.fontSize button:eq(0)').click(function(){
			$('#txt').animate({
				color: 'white',
				fontSize: '+=10px',
				color: 'black'
			}, 1000);
		});
		// +버튼을 클릭했을 때 끝
		// -버튼을 클릭했을 때
		$('.fontSize button:eq(1)').click(function(){
			$('#txt').animate({
				color: 'white',
				fontSize: '-=10px',
				color: 'black'
			}, 1000);
		});
		// -버튼을 클릭했을 때 끝
		// 글씨체 바꾸기
		$('#fontstyle').change(function(){
			$('#txt').css({
				'font-family':$(this).val()
			});
		});
		// 글씨체 바꾸기 끝
	});
	// Example 끝
	// 9_연습_동적테이블
	$(function(){
		// 입력 버튼을 눌렀을 때
		$('#bInsert').click(function(){
			// 입력 값이 전부 다 있을 경우
			if($('#name').val() != "" && $('#age').val() != "" && $('#tel').val() != "" && $('#addr').val() != ""){
				// 테이블 id 밑에 tbody 밑에 자식을 추가
				$('#listTable tbody').append(`<tr> 
					<td>
						${$('#name').val()}
					</td>
					<td>
						${$('#age').val()}
					</td>
					<td>
						${$('#tel').val()}
					</td>
					<td>
						${$('#addr').val()}
					</td>
					<td>
						<input class="del" type="button" value="삭제"/>
					</td>
				</tr>`);
				// 테이블 id 밑에 tbody 밑에 자식을 추가 끝
				$('#listTable tbody tr').css({'cursor':'pointer'});
			}
			// 입력 값이 전부 다 있을 경우 끝
		});
		// 입력 버튼을 눌렀을 때 끝
		// 동적으로 생성된 요소의 삭제 이벤트 처리
		$('#listTable').on('click','.del', function(){ // id값 listTable에 동적으로 생성 된 삭제버튼에다가 클릭 이벤트를 만들어주기
			$(this).closest("tr").remove(); // 삭제 버튼 이벤트가 발생할 때 tr 행 전체를 삭제하기
		});
		// 동적으로 생성된 요소의 삭제 이벤트 처리 끝
		
	});
	// 9_연습_동적테이블 끝
```
```
	$(function(){
		// accordion 클래스의 반복문???
		$('.accordion').each(function(){
			let allDt = $(this).find('dt');
			let allDd = $(this).find('dd');
			
			allDd.hide(); // 담아온 모든 dd 를 닫음
			allDd.first().show(); // 담아온 모든 dd 중 첫번째 dd 만 보여주기
			allDt.css({'cursor':'pointer'}); // 모든 dt에다 마우스를 올려두면 손가락 모양으로 바뀜
			// 모든 dt에 더블클릭 이벤트
			allDt.mouseover(function(){
				allDd.hide(); // 담아온 모든 dd 를 닫음
				$(this).next().show(); // 이벤트가 발생했을 때 그 다음요소를 보여줌
				console.log($(this).text()); // 이벤트가 발생했을 때 태그 사이의 글자를 콘솔에 출력
			});
			// 모든 dt에 더블클릭 이벤트 끝
		});
		// accordion 클래스의 반복문??? 끝
	});
```
```
	$(function(){
		let topDiv = $('.tabSet'); // 클래스 tabSet 을 가져옴
		let anchors = topDiv.find('ul.tabs > li > a'); // 태그 ul 중 클래스 tabs 의 자식 li들 중 자식 a 들을 찾음
		let panelDivs = topDiv.find('div.panel');
		
		anchors.show(); // 가져온 a 태그들을 화면에 보이게
		panelDivs.hide(); // panelDivs 전부 사라지게
		
		let lastAnchor = anchors.filter('.on'); // a태그들 중 클래스 on 을 가져옴
		console.log(lastAnchor.attr('href')); // 속성 href 값을 가져옴
		console.log($(lastAnchor.attr('href'))); // 속성 href 값을 가져와서 객체로 만듬
		
		let lastPanel = $(lastAnchor.attr('href')); // $(lastAnchor.attr('href')) = #panel1-1 
		lastPanel.show(); // 가져온 #panel1-1 을 보여준다
		
		// a태그들을 클릭했을 때
		anchors.click(function(e){
			e.preventDefault(); // a 태그들 의 고유 이벤트를 막음
			
			let currentAnchor = $(this);
			let currentPanel = $(currentAnchor.attr('href')); // 클릭한 현재 a 태그의 href 값 을 가져옴
			
			lastPanel.hide(); // 마지막 panel을 숨김
			currentPanel.show(); // 현재 panel을 보여줌
			
			lastAnchor.removeClass('on'); // 마지막 a 태그의 클래스 on 을 삭제
			currentAnchor.addClass('on'); // 현재 a 태그의 클래스 on 을 추가
			
			lastAnchor = currentAnchor; // 마지막 a 태그에 현재 a 태그 기억
			lastPanel = currentPanel; // 마지막 panel에 현재 panel 기억
		});
		// a태그들을 클릭했을 때 끝
		 
	});
```
팝업
```
  <!-- prettyPopin의 표준 스타일을 임포트（1） -->
  <link rel=stylesheet    href="css/prettyPopin.css" type="text/css" />

  <!-- jQuery라이브러리를 임포트（2） -->
  <script type="text/javascript"   src="../../lib/jquery-1.9.1.js"></script>

  <!-- prettyPopin라이브러리를 임포트（3） -->
  <script type="text/javascript"   src="js/jquery.prettyPopin.js"></script>
  <!-- js 외부파일 -->
  <script type="text/javascript"  src="js/scripts.js"></script>
	$(function(){
	// prettyPopin = 팝업창 띄우기
	// 속성 ref 이 prettyPopin 인 첫 번째 a 태그
	$('a[rel="prettyPopin"]:eq(0)').prettyPopin({
		width: 500
	});
	// 속성 ref 이 prettyPopin 인 첫 번째 a 태그 끝
	// 속성 ref 이 prettyPopin 인 두 번째 a 태그
	$('a[rel="prettyPopin"]:eq(1)').prettyPopin({
		width: 500,
		// 팝업창을 닫았을 때 함수 실행
		callback : function(){
			alert('팝업을 닫습니다.');
		}
		// 팝업창을 닫았을 때 함수 실행 끝
	});
	// 속성 ref 이 prettyPopin 인 두 번째 a 태그 끝
});
```
달력
```
<!-- 달력 꾸며주는 -->
<link rel="stylesheet" type="text/css"
  href="http://code.jquery.com/ui/1.10.0/themes/ui-lightness/jquery-ui.css" />
<!-- 제이쿼리 -->
<script type="text/javascript"  src="http://code.jquery.com/jquery-1.9.0.js"></script>
<script type="text/javascript"   src="http://code.jquery.com/ui/1.10.0/jquery-ui.js"></script>
<!-- Datepicker 한국어  -->
<script src="http://ajax.googleapis.com/ajax/libs/jqueryui/1.11.4/i18n/datepicker-ko.js"></script>
<script type="text/javascript">
$(function(){
   var onul = new Date();
   var year = onul.getFullYear();
   var month = onul.getMonth()+1;
   var day = onul.getDate();
   
   $('#today').text(year+"년"+month+"월"+day+"일");
   
   $('#fromDate').datepicker({
      onClose : function(selectedDate){ //selectedDate : 선택한 날짜
         // minDate가 내가 선택한 날짜
         // 내가 시작 날짜를 15일로 정하면 그 전의 날짜는 선택하지 못하게 막음
         $("#toDate").datepicker("option","minDate",selectedDate);
         
      }
   });
   
   $('#toDate').datepicker({
      onClose : function(selectedDate){
         // maxDate가 내가 선택한 날짜
         // 내가 끝날 날짜를 15일로 정하면 그 이후의 날짜는 선택하지 못하게 막음
         $("#fromDate").datepicker("option","maxDate",selectedDate);
      }
   });
});
</script>
</head>
<body>
오늘의 날짜 : <span id="today"></span>
<hr/>
<label for="fromDate">시작일</label>
<input id="fromDate" type="text">~
<label for="toDate">종료일</label>
<input id="toDate" type="text">
```
그림 슬라이드
```
	<!DOCTYPE html>
	<html>
	<head>
	<meta http-equiv="content-type" content="text/html;charset=utf-8" />
	<title> Plugin </title>
	<style type="text/css">
	*{margin:0;padding:0;}
	img{border:none 0;vertical-align:top;}
	#banner_wrap{position:relative;width:470px;margin:0 auto;}
	
	#prevBtn{position:absolute;left:0;top:10px;} 
	#nextBtn{position:absolute;right:15px;top:10px;} 
	</style>
	<link rel="stylesheet" href="https://cdn.jsdelivr.net/bxslider/4.2.12/jquery.bxslider.css">
	<!-- 제이쿼리 -->>
	<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.1/jquery.min.js"></script>
	<!-- bxslider -->
	<script src="https://cdn.jsdelivr.net/bxslider/4.2.12/jquery.bxslider.min.js"></script>
	
	<script>
	  $(document).ready(function(){
		// 이미지 파일들을 슬라이드 형식으로 바뀜
	    $("#slide_banner").bxSlider({
	    	minSlides : 4, // 최소 표현되는 그림
	    	maxSlides : 4, // 최대 표현되는 그림
	    	slideMargin : 10, // 슬라이드의 마진
	    	slideWidth : 80, // 슬라이드의 너비
	    	moveSlides : 1, // 그림 움직이는 개수
	    	auto : true // 자동으로 움직이게
	    	
	    });
	  });
	</script>
	
	</head>
	<body>
	 <div id="banner_wrap">
	     <!-- bxslider가 인식할 수 있도록 구조 변경 -->
	      <div id="slide_banner">
	         <div><a href="#"><img src="images/pic_t1.jpg" alt="사진1" /></a></div>
	         <div><a href="#"><img src="images/pic_t2.jpg" alt="사진2" /></a></div>
	         <div><a href="#"><img src="images/pic_t3.jpg" alt="사진3" /></a></div>
	         <div><a href="#"><img src="images/pic_t4.jpg" alt="사진4" /></a></div>
	         <div><a href="#"><img src="images/pic_t5.jpg" alt="사진5" /></a></div>
	         <div><a href="#"><img src="images/pic_t6.jpg" alt="사진6" /></a></div>
	         <div><a href="#"><img src="images/pic_t7.jpg" alt="사진7" /></a></div>
	         <div><a href="#"><img src="images/pic_t8.jpg" alt="사진8" /></a></div>
	      </div>    
	</div>
	   
	</body>
	</html>
```
쿠키
```
<!-- 제이쿼리 -->
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.7.1/jquery.min.js"></script>
<!-- 쿠키 플러그인 -->
<script type="text/javascript"   src="js/jquery.cookie.js"></script>
<!-- 자바스크립트 작성 -->
<script type="text/javascript">
	$(function() {
		if($.cookie('promotion') != 'no' ){
			window.open("9_promotion.html","","width=400, height=360");	
		}
	});
</script>

<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.7.1/jquery.min.js"></script>
<script type="text/javascript"   src="js/jquery.cookie.js"></script>
<script type="text/javascript">
	$(function() {
		$('#closeWin').click(function() {
			if( $('input[type="checkbox"]').is(':checked') ){
				$.cookie("promotion", "no", {expires: 1});
			}
			window.close();
		});
	});
</script>

<script type="text/javascript">
	/*
	 	웹상에서 쿠키
	 		- 클라이언트(웹)에 저장하는 데이타(정보)
	 		- 보안 취약
	 		- 문자열만 저장
	 */
	$(function() {
		// 2. 화면에 뜨자마자 쿠키 값 가져오기
		let cookieVar = $.cookie('myemail');
		if(cookieVar){
			$('#txtMail').val(cookieVar);
		}
		
		// 1. 버튼이 눌렸을 때 쿠키 입력 값 저장
		$('#btnSave').click(function() {
			let msg = $('#txtMail').val(); 
			$.cookie('myemail', "즐 " + msg, { // myemail 이 key 값
				expires: 1, // 하루동안 보관 / 안 쓰면 계속 보관
			}); // 쿠키에 입력 값 저장
			
			$('#txtMail').val(''); // 입력 값 지우기
		});
	});
</script>
```
jStorage
```
<!-- jQuery라이브러리를 임포트 -->
 <script type="text/javascript"  src="http://code.jquery.com/jquery-1.9.0.js"></script>
 <!-- jstorage라이브러리를 임포트 -->
 <script type="text/javascript" src="js/jstorage.min.js"></script>
 <!-- js작성 -->
 <script type="text/javascript">
	$(function() {
		/*
			jStorage 웹에 직접 지워주기 전까지 계속 저장하고 있는 저장창고? 같은 느낌
		*/
		// jStorage에 myname, mymemo 로 저장한 값을 불러온다
		let myname = $.jStorage.get('myname');
		let mymemo = $.jStorage.get('mymemo');
		
		// 등록버튼 눌렀을 때
		$('#set').click(function() {
			// jStorage에 myname, mymemo 로 저장
			$.jStorage.set('myname', $('#name').val());
			$.jStorage.set('mymemo', $('#memo').val());
		});
		
		// 삭제버튼 눌렀을 때
		$('#del').click(function() {
			// jStorage에 myname, mymemo 삭제 
			$.jStorage.deleteKey('myname');
			$.jStorage.deleteKey('mymemo');
		});
	});
</script>
```
유효성검사 - validation
```
	// oninput 이벤트 연결도 가능
	window.onload = function(){
			/*
				한글이름 영어이름 숫자 이메일
			*/
			let pt1 = "^[가-힣]{2,5}$"; // 한글이름 유효성 패턴
			let pt2 = "^[A-Za-z]{3,10}$"; // 영문성 이름
			let pt3 = "^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$"; // email
			let pt4 = "^[0-9]{2,3}$"; // 전화번호
			let pt5 = "^[0-9]{3,4}$"; // 전화번호1
			let pt6 = "^[0-9]{4}$"; // 전화번호2
			
			let adult = document.querySelector('#adult'); // 성인
			let teen = document.querySelector('#teen'); // 아동
			let child = document.querySelector('#child'); // 유아
			let checkbox = document.querySelector('#checkbox'); // 체크박스 첫번째
			let checkbox2 = document.querySelector('#checkbox2'); // 체크박스 두번째
			let totalMoney = document.querySelector('#totalMoney'); // 상품합계금액
			let kname = document.querySelector('#kname'); // 한글이름
			let radio = document.querySelector('#radio'); // 남자
			let radio2 = document.querySelector('#radio2'); // 여자
			let ename = document.querySelector('#ename'); // 영문이름
			let ename1 = document.querySelector('#ename1'); // 영문이름1
			let tel = document.querySelector('#tel'); // 전화번호
			let tel1 = document.querySelector('#tel1'); // 전화번호1
			let tel2 = document.querySelector('#tel2'); // 전화번호2
			let email = document.querySelector('#email'); // email
			let btn1 = document.querySelector('#btn1'); // 결제하기
			let btn2 = document.querySelector('#btn2'); // 예약하기
			let btn3 = document.querySelector('#btn3');	// 다시하기
			let sum = 0;
			
			// 성인 명수 입력
			adult.addEventListener("keydown", function(e) {
				sum = 0;
				if(e.key === "Enter"){
					e.preventDefault();
					sum = sum + (adult.value * 39000)+(teen.value * 29000)+(child.value * 19000);
					totalMoney.value = sum;
				}		
			});
			// 성인 명수 입력 끝
			// 아동 명수 입력
			teen.addEventListener("keydown", function(e) {
				sum = 0;
				if(e.key === "Enter"){
					e.preventDefault();
					sum = sum + (adult.value * 39000)+(teen.value * 29000)+(child.value * 19000);
					totalMoney.value = sum;
				}		
			});
			// 아동 명수 입력 끝
			// 유아 명수 입력
			child.addEventListener("keydown", function(e) {
				sum = 0;
				if(e.key === "Enter"){
					e.preventDefault();
					sum = sum + (adult.value * 39000)+(teen.value * 29000)+(child.value * 19000);
					totalMoney.value = sum;
				}		
			});
			// 유아 명수 입력 끝
			
			
			
			
			// 결제하기 버튼
			btn1.addEventListener("click", function(e) {
				e.preventDefault();
				e.stopPropagation();
				
				// 여행약관 동의 체크
				if(!checkbox.checked){
					alert("여행약관에 동의해주세요.");
					return;
				}
				// 개인정보 동의 체크
				if(!checkbox2.checked){
					alert("개인정보보호정책에 동의해주세요.");
					return;
				}
				// 한글이름 유효성 체크
				if(!kname.value.match(pt1)){
					alert("2자리 이상 5자리 이하 한글");
					return;
				}
				// 남자 여자 라디오 체크
				if( !((radio.checked && !radio2.checked) || (!radio.checked && radio2.checked)) ) {
					alert("남자 여자 radio 체크");
					return;
				}
				// email 체크
				if(!email.value.match(pt3)){
					alert("알 맞는 email 형식이 아닙니다.")
					return;
				}
				// 영문성/이름 유효성 체크
				if(!ename.value.match(pt2) || !ename1.value.match(pt2)){
					alert("영문 성과 이름은 각각 3자리 이상 10자리 이하");
					return;
				}
				// 전화번호
				if(!tel.value.match(pt4)){
					alert("전화번호 틀림");
					return;
				}
				if(!tel1.value.match(pt5)){
					alert("전화번호1 틀림");
					return;
				}
				if(!tel2.value.match(pt6)){
					alert("전화번호2 틀림");
					return;
				}
				
				document.frm.submit();
			});
			// 결제하기 버튼 끝
			// 다시하기 버튼
			btn3.addEventListener("click", function(e) {
				e.preventDefault();
				adult.value = "";
				teen.value = "";
				child.value = "";
				sum = 0;
				totalMoney.value = "";
			});
			// 다시하기 버튼 끝
			
			
			
	}
```
### javaScript 복습
```
	
```
### 22. JSP
에러났을 때 페이지 이동 - 보통은 web.xml에 설정해놓음
```
	<%@ page errorPage="02_NormalErrorPage.jsp" %>
```
다른 페이지 삽입
```
	<%@ include file="04_footer.jsp" %>
```
jsp에서 한글이 깨질 때
```
	request.setCharacterEncoding("UTF-8");
```
jsp 페이지 이동
```
	response.sendRedirect("04_responseSecond.jsp");
	<jsp:forward page="02_forwardSecond.jsp"/>
```
jsp 쿠키 생성
```
	// 1. Cookie 객체 생성
	Cookie c = new Cookie("id", "jumki12");
	
	// 2. 속성 부여
	c.setMaxAge(5); // 1초 60초 3초
	
	// 3. 클라이언트에 쿠키 전송
	response.addCookie(c);
```
jsp 쿠키 값 가져오기
```
	// 1. 클라이언트로부터 Cookie를 얻어옴 
	Cookie[] c = request.getCookies();
	
	// 2. 쿠키 이름 중에 "yourid"가 있다면 그 쿠키의 값을 출력
	String id = "";
	for(int i = 0; i < c.length; i++){
		System.out.println(c[i].getName() + " " + c[i].getValue());
		if(c[i].getName().equals("id")){
			id = c[i].getValue(); 
		}
	}

	// 1. 클라이언트로부터 Cookie를 얻어옴 
	Cookie all[]=request.getCookies();

	// 2. 얻어온 쿠키의 이름과 값을 출력
	for(int i=0; all !=null && i<all.length; i++){
		out.println((i+1)+"-->"+all[i].getName()+ ":" +all[i].getValue()+"<br>");
	}
```
jsp 세션 생성
```
	// 실제로는 DB에서 가져와야하는 값
	String saveUser = "jumki12";
	String savePass = "1234";
	
	// 이전화면 폼에서 넘겨받는 값
	String user = request.getParameter("user");
	String pass = request.getParameter("pass");
			
	// user, password가 같을 때 로그인 성공, 그렇지 않으면 로그인 실패
	if( ( user.equals(saveUser) ) && ( pass.equals(savePass) ) ){
		// #2. 세션에 "id"라는 이름에 변수 user 값을 저장
		// 서버에 메모리에 저장 , 기본 30분 저장 , 웹브라우저를 닫으면 사라짐
		session.setAttribute("id", user); 
		
		// #1. 로그인 성공하면 바로 MainPage.jsp를 요청
		response.sendRedirect("MainPage.jsp");
	} else {

		// #1. 로그인에 실패하면 바로 LoginForm.jsp을 요청
		response.sendRedirect("LoginForm.jsp");
	}
```
jsp 세션 값 얻어오기
```
	//# 1."id"로 저장된 세션값을 얻어온다.
	Object id = (String)session.getAttribute("id");
	//# 2. 값이 null이라면 LoginForm.jsp로 페이지 이동
	if(id == null){
		response.sendRedirect("LoginForm.jsp");
		return;
	}
	//# 3. null이 아니라면 String 형변환하여 변수에 지정
	String user = (String)id;
```
jsp 세션 메소드
```
	getAttribute()
	setAttribute()
	removeAttribute()
	invalidate() - 세션 전체 삭제 (로그아웃)
```
jsp 장바구니 담기
```
	request.setCharacterEncoding("utf-8");
	ArrayList<Goods> glist = null;
	Goods vo = null;

	// 1. Form의 값(hidden값) 넘겨받기 ( id, name, price )
	String id = request.getParameter("id");
	String name = request.getParameter("name");;
	int price = Integer.parseInt(request.getParameter("price"));
	
	// 2. 세션의 cart 속성을 얻어온다.
	Object obj = session.getAttribute("cart");
	
	// 3. 만일 null이면 ArrayList 객체 새로 생성하고 그렇지 않으면 ArrayList 변수(glist)에 지정
	if(obj == null){
		glist = new ArrayList<Goods>();
	}else{
		glist = (ArrayList<Goods>)obj;
	}
	
	// 4. 1번의 값들을 Goods 객체로 생성후 ArrayList 에 추가
	glist.add(new Goods(id, name, price));
	
	// 5. 세션에 cart 라는 이름에 ArrayList를 저장
	session.setAttribute("cart", glist);
```
jsp 구매완료 후 장바구니 삭제
```
	ArrayList<Goods> glist = null;

	request.setCharacterEncoding("utf-8");
	
	// 1. 세션에서 지정한 cart 속성값을 얻어온다
	Object obj = session.getAttribute("cart");
	
	// 2. 위의 값이 null 이면 리턴하고, 그렇지 않으면 glist 에 세션의 값을 지정
	if(obj == null){
		return;
	}else{
		glist = (ArrayList<Goods>)obj;
	}
	
	// 3. 세션에서 속성을 제거한다
	session.removeAttribute("cart");
```
jsp 빈즈 액션태그
```
	<jsp:useBean> 자바빈 객체 생성
		<jsp:useBean id="빈이름" class="빈클래스이름"
		scope="범위"></jsp:useBean> - scope(자바빈 객체가 저장될 영역)
	<jsp:setProperty> 자바빈 프로퍼티 변경
		<jsp:setProperty name="자바빈" property="이름"
		</jsp:setProperty> - 추가속성 value(변경할 프로퍼티 값) , param(프로퍼티 값에 파라미터 값 대입)
	<jsp:getProperty> 자바빈 프로퍼티 읽기
	<jsp:include> 다른페이지를 동적 삽입
		<jsp:include page="03_paramImage.jsp"> // 페이지를 삽입하면서 name 벨류 값을 바꿀 수 있음
			<jsp:param value="sp" name="lang"/>
		</jsp:include>
	<jsp:forward> 다른페이지로 이동
	<jsp:param> jsp 페이지에 프로퍼티 추가
```
jsp에서 데이타 받는 방법
```
	${param.data } - 파라미터 값
	${sessionScope.login } - 세션 값
	${cookie.isFlag.value } - 쿠키 값
```
JSTL
```
	lib에 jstl.jar , standard.jar 세팅 후
	<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
	<!-- 변수 선언 -->
	<c:set var="gender" value="female"/>
	
	<!-- if문 -->
	<c:if test="${gender == 'male' }">
		당신은 남자입니다.
	</c:if> <br/>
	<c:if test="${gender == 'female' }">
		당신은 여자입니다.
	</c:if> <br/>
	
	<!-- 변수 선언 -->
	<c:set var="age" value="9"/>
	
	<!-- choose when -->
	<c:choose>
	
		<c:when test="${age < 10 }">
			<c:out value="${gender }"></c:out>
		</c:when>
		<c:when test="${age >= 10 && age < 20 }">
			<c:out value="청소년">밍낑</c:out>
		</c:when>
		<c:otherwise>어른밍낑</c:otherwise>
	</c:choose>
	
	<!-- 변수 선언 -->
	<c:set var="sum" value="0"/>
	
	<!-- forEach -->
	<c:forEach var="i" begin="1" end="100">
		<c:set var="sum" value="${sum+i }"></c:set>
	</c:forEach>
	<hr/>
	1~100까지의 합 : ${sum }
	<hr/>
	
	<!-- 1부터 100까지의 홀수의 합과 짝수의 합을 출력하기 -->
	<c:forEach var="i" begin="1" end="100">
		<c:if test="${i % 2 == 0 }">
			<c:set var="even" value="${even+i }"></c:set>
		</c:if>
		<c:if test="${i % 2 != 0 }">
			<c:set var="odd" value="${odd+i }"></c:set>
		</c:if>
	</c:forEach>
```
ajax
```
	let param = { 
		cate : 'book', 
		name : 'kim' 
	};
	
	// 비동기 통신(ajax)
	// 화면을 가만히 있는 상태에서 서버에 요청하고 그 결과 받아오기
	$.ajax({
		type : 'get',
		url : '02_server.jsp',
		data : param,
		dataType : 'text', // 응답 데이타 종류 (text/html/xml/json.....)
		success : parseData,
		error : function(err) {
			alert('에러발생');
			console.log(err);
		}
	});
```
ajax 축약형
```
	$.get('02_server.jsp', param, parseData);
```
ajax - dataType = 'xml'
```
	// 가져오기 버튼이 눌렸을 때
	$('#btnSelect').click(function() {
		$.ajax({
			type : 'get',
			url : 'DataSelect.jsp',
			dataType : 'xml',
			success : selectResult,
			error : function(err) {
				alert("서버전송 실패");
				console.log(err);
			}
		}); // $.ajax
		
		$('#tbd').empty(); // 기존에 있는 동적 테이블 삭제
		function selectResult(result) {
			let person = $(result).find('person');
			person.each(function() {
				let name = $(this).find('name').text();
				let age = $(this).find('age').text();
				let tel = $(this).find('tel').text();
				let addr = $(this).find('addr').text();
				
				$('#tbd').append('<tr>'
					+ '<td>' + name + '</td>'
					+ '<td>' + age + '</td>'
					+ '<td>' + tel + '</td>'
					+ '<td>' + addr + '</td>'
					+ '</tr>'
				);
			});
		}
		
	}); // $('#btnSelect').click
```
```
	rtn_xml += "<customer>";

	while (rs.next()){		
		rtn_xml += "<person>";
		rtn_xml += "<name>" + rs.getString("name") + " </name>";
		rtn_xml += "<age>" + rs.getString("age") +  "</age>";
		rtn_xml += "<tel>" + rs.getString("tel") +  "</tel>";
		rtn_xml += "<addr>" + rs.getString("addr") +  "</addr>";
		rtn_xml += "</person>";		
	}	
	rtn_xml += "</customer>";
	out.write(rtn_xml);
```
ajax VO, LIST 객체 받기
```
	pom.xml에 추가
		<!-- #########  객체를 json/xml로 변환 처리  ######### -->
		<!-- https://mvnrepository.com/artifact/com.fasterxml.jackson.core/jackson-databind -->
		<dependency>
		    <groupId>com.fasterxml.jackson.core</groupId>
		    <artifactId>jackson-databind</artifactId>
		    <version>2.9.6</version>
		</dependency>
		<dependency>
		    <groupId>com.fasterxml.jackson.dataformat</groupId>
		    <artifactId>jackson-dataformat-xml</artifactId>
		    <version>2.9.6</version>
		</dependency>
		<!-- 자바 객체를 json 타입의 문자열로 변환 -->
		<!-- https://mvnrepository.com/artifact/com.google.code.gson/gson -->
		<dependency>
		    <groupId>com.google.code.gson</groupId>
		    <artifactId>gson</artifactId>
		    <version>2.8.2</version>
		</dependency>
	Controller 쪽
		// ajax
		// @Controller + @ResponseBody = @RestController
		@RestController
		public class SampleController {
			
			@RequestMapping(value = "getText", produces = "text/plain;charset=UTF-8") // 반환 값을 한글로 받을 수 있게
			//@ResponseBody // view 페이지 말고 문자열 값을 반환 받고 싶을 때
			public String getText() {
				return "뷰페이지로 보냄";
			}
			
			// 객체를 반환
			@RequestMapping("getObject")
			public SampleVO getObject() {
				return new SampleVO("홍길동", 22, "오늘도화이팅");
			}
			
			// list를 반환
			@RequestMapping("getList")
			public List<SampleVO> getList() {
				List<SampleVO> list = new ArrayList<SampleVO>();
				list.add(new SampleVO("홍길동", 22, "오늘도 화이팅"));
				list.add(new SampleVO("홍길자", 33, "맛점"));
				list.add(new SampleVO("홍길숙", 44, "우리팀 화이팅"));
				
				return list;
			}
			
			// 넘어오는 변수 값 받기
			@GetMapping("sample/{cate}/{cno}")
			public void getUrl(@PathVariable String cate, @PathVariable Integer cno) {
				System.out.println(cate + " : " + cno);
			}
			
			@PostMapping("sample/data")
			public SampleVO getPost(SampleVO vo) {
				System.out.println("확인: " + vo.toString());
				return vo;
			}
		}
	JSP 쪽
		<body>
			<!-- 1 -->
			<a href='getText'>1. 문자열 반환</a>
			<hr/>
			
			<!-- 2 -->
			<a href='getObject'>2. 객체 반환</a>
			<hr/>
			
			<!-- 3 -->
			<a href='getList'> 3. 리스트 객체 반환</a>
			<hr/>
			
			<!-- 4 -->
			<a href='sample/it/1001'> 4. 쿼리스트링처리 </a><br/>
			<a href='sample/novel/2001'> 4. 쿼리스트링처리 </a><br/>
			<hr/>
			
			<!-- 5 -->
			<form action='sample/data' method='post'>
				<input type='text' name='name'>
				<input type='text' name='age'>
				<input type='text' name='message'>
				<input type='submit' value='POST전송'>
			</form>
		</body>
```
ajax 댓글
```
	javaScript 쪽
		$(function(){
	 
		 	// 댓글 추가 버튼이 눌려졌을 때
		 	$('#replyConfirm').click(function(){
		 	
		 		let param = {
		 			bno : $('#bno').val(),
		 			replyer : $('#replyer').val(),
		 			reply : $('#reply').val()
		 		};
		 		
		 		/* form 의 내용을 한번에 받아오기  
		 		let param = $('#replyFrm').serialize();
		 		*/
		 		
				$.ajax({
					type : 'post',
					data : param,
					url : '../replies/new',
					success : function(result){
						$('#reply').val('');
						replyList();
					},
					error : function(err){
						alert('error');
						console.log(err);
					}
				});
				
		 	});
		 	
		 	// 댓글 목록을 서버에서 가지고 와서 출력
		 	replyList();
		 	function replyList() {
		 	
		 		$.ajax({
		 		
		 			type : 'get',
		 			url : '../replies',
		 			data : { bno : $('#bno').val() },
		 			dataType : 'json',
		 			success : function(result){
		 				// console.log(result);
		 				let replyList = $('#replyList'); // jsp 테이블의 아이디를 가져오기
		 				
		 				replyList.empty(); // 테이블 자식들을 삭제
		 				for(row of result){ // 컨트롤러의 결과 값
		 					var tr = $('<tr/>'); // replyList 안에 tr 태그 추가
		 					
		 					var rno = $('<td/>').text(row['rno']); // list 에 rno 값을 td 태그 추가 후 입력
		 					tr.append(rno); // tr에 td 태그 추가
		 					
		 					var replyer = $('<td/>').text(row['replyer']); // list 에 replyer 값을 td 태그 추가 후 입력
		 					tr.append(replyer);
		 					
		 					var reply = $('<td/>').text(row['reply']); // list 에 reply 값을 td 태그 추가 후 입력
		 					tr.append(reply);
		 					
		 					var replydate = $('<td/>').text(row['replydate']); // list 에 replydate 값을 td 태그 추가 후 입력
		 					tr.append(replydate);
		 					
		 					var modifyBtn = $('<td/>').html('<button class="modify">수정</button>');
		 					tr.append(modifyBtn);
		 					
		 					var deleteBtn = $('<td/>').html('<button class="delete">삭제</button>');
		 					tr.append(deleteBtn);
		 					
		 					replyList.append(tr); // 만든 tr 태그를 테이블에 추가
		 				}
		 				
		 			},
		 			error : function(err){
		 				alert('error');
		 				console.log(err);
		 			}
		 			
		 		});
		 		
		 	};
		 	
		 	// 댓글에 '삭제' 버튼이 눌렸을 때
		 	$('#replyList').on('click', '.delete', function(){
		 		// 각 버튼을 클릭했을 때 tr부모까지 가서 자식들 중 0번째
		 		let rno = $(this).parents('tr').children().eq(0).text();
		 		
		 		$.ajax({
					type : 'delete',
					url : '../replies/' + rno,
					success : function(result){
						replyList();
					},
					error : function(err){
						alert('error');
						console.log(err);
					}
				});
				
		 	});
		 	
		 	// 댓글에 '수정' 버튼이 눌렸을 때
		 	$('#replyList').on('click', '.modify', function(){
		 	
		 		// 각 버튼을 클릭했을 때 tr부모까지 가서 자식들 중 0번째
		 		let rno = $(this).parents('tr').children().eq(0).text();
		 		var btnText = $(this).text();
		 		
		 		if( btnText == '수정' ){
		 			
		 			// replyer 수정
		 			let replyertd = $(this).parents('tr').children().eq(1);
		 			let replyerText = $(this).parents('tr').children().eq(1).text();
		 			replyertd.text('');
		 			replyertd.append('<input type="text" name="replyer" value="'+replyerText+'">');
		 		
		 			// reply 수정
		 			let replytd = $(this).parents('tr').children().eq(2);
		 			let replyText = $(this).parents('tr').children().eq(2).text();
		 			replytd.text('');
		 			replytd.append('<input type="text" name="reply" value="'+replyText+'">');
		 			
		 			$(this).text('수정하기');
		 			
		 		}else if( btnText == '수정하기' ){
		 			var replyer = $(this).parents('tr').find('input').eq(0).val();
		 			var reply = $(this).parents('tr').find('input').eq(1).val();
		 			
		 			var param = {
		 				'rno' : rno,
		 				'replyer' : replyer,
		 				'reply' : reply
		 			}
		 			
		 			$.ajax({
		 				type : 'post',
		 				data : param,
		 				url : '../replies/' + rno,
		 				success : function(result){
		 					replyList();
		 				},
		 				error : function(err){
		 					alert('error');
		 					console.log(err);
		 				}
		 			});
		 		}
		 		
				
		 	});
		 	
		 });
```
### 23. mybatis
mybatis-config.xml
```
	<?xml version="1.0" encoding="UTF-8" ?>
	<!DOCTYPE configuration
	 PUBLIC "-//mybatis.org//DTD Config 3.0//EN"
	 "http://mybatis.org/dtd/mybatis-3-config.dtd">
	<configuration>
		<!-- db설정 db.properties -->
		<properties resource="db.properties"/>
		<!-- 추가 설정 -->
		<settings>
			<setting name="mapUnderscoreToCamelCase" value="true"/>
		</settings>
		<environments default="development">
			<environment id="development">
				<transactionManager type="JDBC" />
				<dataSource type="POOLED">
					<property name="driver" value="${driver}" />
					<property name="url" value="${url}" />
					<property name="username" value="${username}" />
					<property name="password" value="${password}" />
				</dataSource>
			</environment>
		</environments>
		<mappers>
			<mapper resource="mybatis/guest/mapper/CommentMapper.xml" />
		</mappers>
	</configuration>
```
CommentMapper.xml
```
	<?xml version="1.0" encoding="UTF-8" ?>
	<!DOCTYPE mapper
	 PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN"
	 "http://mybatis.org/dtd/mybatis-3-mapper.dtd">
	<mapper namespace="CommentMapper">
		<!-- [중요] resultMap 사용하지 않을 예정 
			 	   우리는 resultType만 사용할 예정
		-->
		<!-- parameterType에 hashmap을 넣고 키에 따라서 조건을 줄수 있음
			 그래서 하나의 select 태그로 여러 검색이 가능함
		 -->
		<select id="selectComment" parameterType="hashmap" resultType="mybatis.guest.model.CommentVO">
			SELECT * 
			FROM comment_tab
			<where>
				<if test="commentNo != null">
					comment_no = #{commentNo}
				</if>
			</where>
		</select>
		
		<insert id="insertComment" parameterType="mybatis.guest.model.CommentVO">
			INSERT INTO comment_tab(user_id, comment_content, reg_date)
			VALUES(#{userId}, #{commentContent}, sysdate())
		</insert>
		
		
	</mapper>
```
CommentRepository.java
```
	package mybatis.guest.session;
	import java.io.*;
	import java.util.*;
	import mybatis.guest.model.CommentVO;
	import org.apache.ibatis.io.Resources;
	import org.apache.ibatis.session.*;
	
	public class CommentRepository 
	{
		//	private final String namespace = "CommentMapper";
	
		private SqlSessionFactory getSqlSessionFactory() {
			
			InputStream inputStream;
			try {
				inputStream = Resources.getResourceAsStream("mybatis-config.xml");
			} catch (IOException e) {
				throw new IllegalArgumentException(e);
			}
			SqlSessionFactory sessFactory =  new SqlSessionFactoryBuilder().build(inputStream);
			return sessFactory;
		}
		
		/*
		 * JDBC : Connection (연결)
		 * mybatis : SqlSession (연결)
		 */
		public List<CommentVO> selectComment(){
			SqlSession session = getSqlSessionFactory().openSession();
			try {
				List<CommentVO> list = session.selectList("CommentMapper.selectComment");
				return list;
			}finally {
				session.close(); // 연결 객체를 반환
			}
		}
		
		public void insertComment(CommentVO vo){
			SqlSession session = getSqlSessionFactory().openSession();
			try {
				int result = session.insert("CommentMapper.insertComment", vo);
				if(result != 0) {
					session.commit();
				}else {
					session.rollback();
				}
			}finally {
				session.close(); // 연결 객체를 반환
			}
		}
		
		public CommentVO selectCommentByPk(int commentNo){
			SqlSession session = getSqlSessionFactory().openSession();
			try {
				HashMap map = new HashMap();
				map.put("commentNo", commentNo);
				CommentVO vo = session.selectOne("CommentMapper.selectComment", map);
				return vo;
			}finally {
				session.close(); // 연결 객체를 반환
			}
		}
		
	}
```
### 24. spring
pom.xml 세팅 - spring-context
```
	<!-- https://mvnrepository.com/artifact/org.springframework/spring-context -->
	<dependency>
	    <groupId>org.springframework</groupId>
	    <artifactId>spring-context</artifactId>
	    <version>5.3.23</version>
	</dependency>
```
applicationContext.xml - bean 정의
```
	xml 쪽
		<!-- 빈(bean) 정의 -->
		<bean id="ko" class="ex1_xml.MessageBeanKoImpl"></bean> / bean 태그 안 속성 scope - (singleton, prototype)
		<bean id="en" class="ex1_xml.MessageBeanEnImpl"></bean>
	자바 쪽
		// 1. 스프링 설정파일 연결
		ApplicationContext context = new ClassPathXmlApplicationContext("ex1_xml/applicationContext.xml");
		
		// 2. DI : 스프링 컨테이너에서 빈(Bean) 가져오기
		Message bean = context.getBean("ko", Message.class);
		bean.sayHello("홍길숙");
		
		Message bean2 = context.getBean("en", Message.class);
		bean2.sayHello("Jane");
```
bean 생성할 때 setter로 값 지정해놓기
```
	<!-- 기본형 멤버값 지정 
		1. setter 이용
	-->
	<bean id="member" class="ex2_xml_ref.MemberBean">
		<property name="name" value="홍길동"></property>
		<property name="age" value="34"></property>
		<property name="message">
			<value>쿄쿄쿄</value>
		</property>
	</bean>
	<!-- 기본형 멤버값 지정 
		2. constructor 이용
	-->
	<bean id="member2" class="ex2_xml_ref.MemberBean">
		<constructor-arg index="2" value="홍길국"></constructor-arg>
		<constructor-arg index="1" value="22"></constructor-arg>
		<constructor-arg index="0" value="쿄쿄쿄"	></constructor-arg>
	</bean>

	<!-- 참조형 멤버값 지정 
		3. setter 이용
	-->
	<bean id="dao1" class="ex2_xml_ref.MemberDAO">
		<property name="member" ref="member2"></property>
	</bean>
	
	<!-- 참조형 멤버값 지정 
		4. constructor 이용
	-->
	<bean id="dao2" class="ex2_xml_ref.MemberDAO">
		<constructor-arg index="0" ref="member"></constructor-arg>
	</bean>
```
list형식 bean
```
	// 자바 쪽
	ApplicationContext context = new ClassPathXmlApplicationContext("ex3_xml_list/applicationContext.xml");
		
	ListBean bean = context.getBean("bean", ListBean.class);
	
	for(Integer i : bean.getIntList()) {
		System.out.println(i);
	}
	
	for (MemberBean mb : bean.getMemberList()) {
		mb.output();
	}

	// xml 파일 쪽쪽
	<!-- 빈(bean) 정의 -->
	<bean id="bean" class="ex3_xml_list.ListBean">
		<property name="intList">
			<list>
				<value>22</value>
				<value>33</value>
				<value>44</value>
			</list>
		</property>
		
		<property name="memberList">
			<list>
				<ref bean="m1"/>
				<ref bean="m2"/>
				<!-- bean -->
				<bean class="ex3_xml_list.MemberBean">
					<property name="name" value="홍길숙"></property>
					<property name="age" value="23"></property>
					<property name="message">
						<value>쿄쿄쿄23</value>
					</property>
				</bean>
			</list>
		</property>
		
	</bean>
	
	<bean id="m1" class="ex3_xml_list.MemberBean">
		<property name="name" value="홍길동"></property>
		<property name="age" value="34"></property>
		<property name="message">
			<value>쿄쿄쿄</value>
		</property>
	</bean>
	
	<bean id="m2" class="ex3_xml_list.MemberBean">
		<constructor-arg index="2" value="홍길국"></constructor-arg>
		<constructor-arg index="1" value="22"></constructor-arg>
		<constructor-arg index="0" value="쿄쿄쿄"></constructor-arg>
	</bean>
```
### 어노테이션
@Component - MemberBean
```
	@Component
	public class MemberBean {
		private String name = "홍길숙";
		private int age = 33;
		private String message = "맛점";
			
		public void output() {
			System.out.println("MemberBean [name=" + name + ", age=" + age + ", message=" + message + "]"); 
		}
	}
```
@Autowired - 의존성 주입
```
	@Component
	public class MemberDAO {
		// DI
		@Autowired
		private MemberBean member;
		
		/*
		 * 생성자나 setter 이용하여 멤버변수 지정해야 함
		 */
		public void insert() {
			member.output();
		}
		
	}
```	
@Component("memberDAO") - 객체명을 지정
```
	MemberDAO dao = (MemberDAO)context.getBean("memberDAO");
```
Main
```
	public class MainApp {
		public static void main(String[] args) {
			ApplicationContext context = new ClassPathXmlApplicationContext("ex4_annotation/applicationContext.xml");
			MemberDAO dao = (MemberDAO)context.getBean("memberDAO");
			dao.insert();
		}
	}
```
applicationContext.xml
```
	<context:component-scan base-package="ex4_annotation"></context:component-scan>
```
@Autowired
@Qualifier("outputer2") - 2개가 있을때 오토와이어를 쓰고 퀄리파이어로 id명을 입력
```
	@Autowired
	@Qualifier("outputer2")
	private Outputer outputer;

	<bean id="outputer" class="ex5_autowired.OutputerImpl">
		<property name="path" value="src\\ex5_autowired\\save.txt"></property>
	</bean>

	<bean id="outputer2" class="ex5_autowired.OutputerImpl">
		<property name="path" value="src\\ex5_autowired\\message.txt"></property>
	</bean>
```
### AOP
```
	target - 핵심 기능
	pointcut - 목
```
AOP 설정 xml
```
	<!-- target 핵심기능 -->
	<bean id="targetBean" class="aop1_xml.MessageBeanImpl"></bean>
	
	<!-- advice 공통기능 -->
	<bean id="loggingAdvice" class="aop1_xml.LoggingAdvice"></bean>
	<!-- 2번째 공통기능 -->
	<bean id="sampleAdvice" class="aop1_xml.SampleAdvice"></bean>

	<!-- AOP 환경설정 -->
	<aop:config>
	
		<!-- 들어가는 지점 설정 -->
		<aop:pointcut expression="execution(public * aop1_xml.*.*Hello(..))" id="pointCut"/> <!-- 접근지정자가 public 이고 반환 값이 상관없고 aop1_xml패키지 안 모든 클래스 안 Hello() 로 끝나는 모든 함수 인자는 안따짐 -->
		
		<!-- loggingAdvice 클래스를 연결-->
		<aop:aspect ref="loggingAdvice">
			<!-- pointcut에서 지정한 Hello로 끝나는 메소드 전에 advice(aop1_xml.LoggingAdvice) 안 before 함수를 실행 -->
			<aop:before method="before" pointcut-ref="pointCut"/>
			<!-- pointcut에서 지정한 Hello로 끝나는 메소드 이후에 advice(aop1_xml.LoggingAdvice) 안 xxxxx 함수를 실행 --> 
			<aop:after method="xxxxx" pointcut-ref="pointCut"/>
		</aop:aspect>
		
		<!-- sampleAdvice 클래스를 연결-->
		<aop:aspect ref="sampleAdvice">
			<!-- 전 실행 후 실행 (전과 후 둘다 실행) -->
			<aop:around method="around" pointcut-ref="pointCut"/>
		</aop:aspect>
		
	</aop:config>
```
AOP 어노테이션으로 적용
```
	main쪽
		ApplicationContext context = new ClassPathXmlApplicationContext("aop2_annotation/applicationContext.xml");
		
		MessageBean bean = context.getBean("messageBeanImpl", MessageBean.class);
		
		bean.sayHello();
		System.out.println("========================================");
		bean.enSayHello();
		System.out.println("========================================");
		bean.test();
		System.out.println("========================================");

	impl쪽
		@Component
		public class MessageBeanImpl implements MessageBean {
		
			@Override
			public void sayHello() {
				System.out.println("sayHello() 호출");
			}
		
			@Override
			public void enSayHello() {
				System.out.println("enSayHello() 호출");
			}
		
			@Override
			public void test() {
				System.out.println("test() 호출");
			}
		
		}

	AOP 적용하는 부분
		@Aspect // AOP 어노테이션
		@Component // 빈 자동 생성
		public class SampleAdvice {
			@Around("execution(public * aop2_annotation.*.*(..))") // 어떤 메소드가 실행할때 around가 실행할지 설정
			public Object around(ProceedingJoinPoint point) throws Throwable{
				String name = point.getSignature().getName();
				System.out.println("----------[사전 작업]----------: " + name);
				Object obj = point.proceed();
				System.out.println("----------[사후 작업]----------: " + name);
				
				return obj;
			}
		}

	XML 쪽
		<!-- 1 빈지정 자동 -->
		<context:component-scan base-package="aop2_annotation"></context:component-scan>
		
		<!-- 2 AOP 적용 -->
		<aop:aspectj-autoproxy></aop:aspectj-autoproxy>
	
```
### Spring Mybatis
Main
```
	// 1. Spring 컨테이너를 구동한다.
	AbstractApplicationContext container = new GenericXmlApplicationContext("applicationContext.xml");

	// 2. Spring 컨테이너로부터 BoardServiceImpl 객체를 Lookup한다.
	BoardService boardService = (BoardService) container.getBean("boardService");

	// 3. 글 등록 기능 테스트
	BoardVO vo = new BoardVO();
	vo.setTitle("spring mybatis");
	vo.setWriter("홍길동S");
	vo.setContent("임시 내용..............");
	boardService.insertBoard(vo);

	// 4. 글 목록 검색 기능 테스트		
	BoardVO svo = new BoardVO();
	List<BoardVO> boardList = boardService.getBoardList(svo);
	for (BoardVO board : boardList) {
		System.out.println("---> " + board.toString());
	}

	// 5. Spring 컨테이너 종료
	container.close();
```
Mybatis Class
```
	@Repository("boardDAO")
	public class BoardDAOMybatis {
		
		@Autowired
		private SqlSessionTemplate mybatis;
		/*
		 * JDBC : Connection
		 * mybatis : SqlSession
		 */
	
		public void insertBoard(BoardVO vo) {
			System.out.println("===> Mybatis insertBoard() 호출");
			mybatis.insert("BoardDAO.insertBoard", vo);
		}
	
		public void updateBoard(BoardVO vo) {
			System.out.println("===> Mybatis updateBoard() 호출");
			mybatis.update("BoardDAO.updateBoard", vo);
		}
	
		public void deleteBoard(BoardVO vo) {
			System.out.println("===> Mybatis deleteBoard() 호출");
			mybatis.delete("BoardDAO.deleteBoard", vo);
		}
	
		public BoardVO getBoard(BoardVO vo) {
			System.out.println("===> Mybatis getBoard() 호출");
			return (BoardVO) mybatis.selectOne("BoardDAO.getBoard", vo);
		}
	
		public List<BoardVO> getBoardList(BoardVO vo) {
			System.out.println("===> Mybatis getBoardList() 호출");
			return mybatis.selectList("BoardDAO.getBoardList", vo);
		}
	}
```
BoardService
```
	public interface BoardService {
		// CRUD 기능의 메소드 구현
		// 글 등록
		void insertBoard(BoardVO vo);
	
		// 글 수정
		void updateBoard(BoardVO vo);
	
		// 글 삭제
		void deleteBoard(BoardVO vo);
	
		// 글 상세 조회
		BoardVO getBoard(BoardVO vo);
	
		// 글 목록 조회
		List<BoardVO> getBoardList(BoardVO vo);
	}
```
BoardServiceImpl Class
```
	@Service("boardService")
	public class BoardServiceImpl implements BoardService {
		
		@Autowired
		private BoardDAOMybatis boardDAO;
	
		public void insertBoard(BoardVO vo) {
			boardDAO.insertBoard(vo);
		}
	
		public void updateBoard(BoardVO vo) {
			boardDAO.updateBoard(vo);
		}
	
		public void deleteBoard(BoardVO vo) {
			boardDAO.deleteBoard(vo);
		}
	
		public BoardVO getBoard(BoardVO vo) {
			return boardDAO.getBoard(vo);
		}
	
		public List<BoardVO> getBoardList(BoardVO vo) {
			return boardDAO.getBoardList(vo);
		}
	}
```
db.properties 파일
```
	# ORACLE
	#jdbc.driver=oracle.jdbc.driver.OracleDriver
	#jdbc.url=jdbc:oracle:thin:@127.0.0.1:1521:orcl
	#jdbc.username=javassem
	#jdbc.password=1234
	
	# MYSQL
	jdbc.driver=com.mysql.cj.jdbc.Driver
	jdbc.url=jdbc:mysql://localhost:3306/basic
	jdbc.username=scott
	jdbc.password=tiger
```
Board-mapping.xml
```
	<mapper namespace="BoardDAO">

		<!-- 오라클 연동 -->
		<!-- <insert id="insertBoard" parameterType="BoardVO">		
			INSERT INTO BOARD(SEQ, TITLE, WRITER, CONTENT, REGDATE, CNT)
			VALUES(board_seq.nextval,
				#{title}, #{writer}, #{content}, 
				sysdate, 0)		
		</insert> -->
		<!-- Mysql 연동 -->
		<insert id="insertBoard" parameterType="boardVO">		
			INSERT INTO BOARD(TITLE, WRITER, CONTENT, REGDATE, CNT)
			VALUES(	#{title}, #{writer}, #{content}, 
				sysdate(), 0)		
		</insert>
		
		<update id="updateBoard" parameterType="boardVO">
			
			UPDATE BOARD SET
			TITLE = #{title},
			CONTENT = #{content}
			WHERE SEQ = #{seq}
			
		</update>
		
		<delete id="deleteBoard">
			
			DELETE FROM BOARD
			WHERE SEQ = #{seq}
			
		</delete>
		
		<select id="getBoard" parameterType="int" resultType="boardVO">
			
			SELECT *
			FROM BOARD
			WHERE SEQ = #{seq}
			
		</select>
		
		<select id="getBoardList" resultType="boardVO">
			
			SELECT *
			FROM BOARD
			ORDER BY SEQ DESC
			
		</select>
	</mapper>
```
Mybatis Mapper.xml 파일 안에서 비교 연산자를 인식하기
```
	<select id="getBoardList" resultType="BoardVO">
		<![CDATA[
		SELECT * FROM uploadtemp 
		ORDER BY b_id DESC
		]]>
	</select>
```
applicationContext.xml 파일
```
	<!-- 자동 빈 생성  -->
	<context:component-scan base-package="board.impl"></context:component-scan>
	
	<!-- DataSource 설정 -->
	<context:property-placeholder location="classpath:config/db.properties"/>
	<bean id="dataSource" class="org.apache.commons.dbcp.BasicDataSource">
		<property name="driverClassName" value="${jdbc.driver}"></property> <!-- setDriverClassName() -->
		<property name="url" value="${jdbc.url}"></property>
		<property name="username" value="${jdbc.username}"></property>
		<property name="password" value="${jdbc.password}"></property>
	</bean>

	<!-- Spring과 Mybatis 연동 설정 -->
	<bean id="sqlSession" class="org.mybatis.spring.SqlSessionFactoryBean">
		<property name="dataSource" ref="dataSource"></property> <!-- setDataSource() -->
		<property name="configLocation" value="classpath:mybatis-config.xml"></property> <!-- mybatis의 설정파일 지정 -->
		<!-- value 경로 해석 -->
			<!-- mappers 안에 모든 -->
		<!-- <property name="mapperLocations" value="classpath:mappers/**/*Mapper.xml"></property> -->
		<property name="mapperLocations"> <!-- mapper 파일들을 지정  -->
			<value>classpath:mappings/board-mapping.xml</value>
		</property>
		<property name="typeAliases">
			<list>
				<value>board.vo.BoardVO</value> <!-- 자동으로 별칭이 BoardVO 로 지정 됨 -->
			</list>
		</property> 
	</bean>

	<!-- SqlSession 객체 생성 -->
	<bean class="org.mybatis.spring.SqlSessionTemplate">
		<constructor-arg ref="sqlSession"></constructor-arg>
	</bean>
```
mybatis-config.xml
```
	<configuration>	
		<!-- DB 연동부분은 스프링 설정파일로 이동 -->
	
	
		<!-- Alias 설정 -->
		<typeAliases>
			<typeAlias type="board.vo.BoardVO" alias="boardVO"/>
		</typeAliases>
		
		<!-- Sql Mapper 설정 -->
		<mappers>
			<mapper resource="mappings/board-mapping.xml"/>
		</mappers>
	</configuration>
```
ModelAndView
```
	@Controller
	public class HelloController {
		
		@RequestMapping(value = "start.do")
		public ModelAndView start() {
			System.out.println("클라이언트한테 start.do라는 요청을 받음");
			
			ModelAndView mv = new ModelAndView();
			
			mv.setViewName("hello");
			mv.addObject("dbValue", "추후에 디비값");
			mv.addObject("login", "아이디");
			
			return mv;
		}
	}
```
Web.xml 한글 인코딩 세팅
```
	<!-- 한글 인코딩 -->
	<filter>
		<filter-name>characterEncoding</filter-name>
		<filter-class>org.springframework.web.filter.CharacterEncodingFilter</filter-class>
		<init-param>
			<param-name>encoding</param-name>
			<param-value>UTF-8</param-value>
		</init-param>
	</filter>
	<filter-mapping>
		<filter-name>characterEncoding</filter-name>
		<url-pattern>/*</url-pattern>
	</filter-mapping>
```
File Upload Pom.xml
```
	<!-- ################################################# -->
	<!-- 파일업로드 -->
	<dependency>
		<groupId>commons-fileupload</groupId>
		<artifactId>commons-fileupload</artifactId>
		<version>1.3</version>
	</dependency>
```
File Upload Servlet-Context.xml
```
	<!-- 파일업로드에 필요한 bean -->
	<beans:bean id="multipartResolver" class="org.springframework.web.multipart.commons.CommonsMultipartResolver">
		<!-- 파일업로드 최대 용량(byte) --> 
		<beans:property name="maxUploadSize" value="10485760" />
	</beans:bean>
```
File Upload Form태그
```
	<form action="saveBoard.do" method='post' enctype="multipart/form-data">
```
File Upload VO 쪽
```
	private String b_fname;		// 파일명
	private String b_realfname; // 저장된 파일이름
	private long b_fsize;		// 파일크기
	
	//*************************************************
	MultipartFile file; // ****** type='file'의 name명과 동일
	
	public MultipartFile getFile() {
		return file;
	}
	
	public void setFile(MultipartFile file) {
		this.file = file;
		
		// 업로드 파일이 있는 경우
		if( !file.isEmpty()) {
			this.b_fname = file.getOriginalFilename();
			this.b_fsize = file.getSize();
			
			// 실제 저장된 파일명 만들기
			UUID uuid = UUID.randomUUID();
			this.b_realfname = uuid.toString() + "_" + b_fname;
			
			// 실제파일 저장
			// 추후에 웹서버 경로를 찾아서 수정
			File f = new File("C:\\springweb\\hFileBoard\\src\\main\\webapp\\resources\\upload\\" + b_realfname);
			
			try {
				file.transferTo(f);
			} catch (IllegalStateException e) {				
				e.printStackTrace();
			} catch (IOException e) {
				e.printStackTrace();
			}
			
		}
		
	}
```
Transaction - 트랜잭션
```
	root 
		<!-- ###### Transaction ###### -->
		<bean id="transactionManager" class="org.springframework.jdbc.datasource.DataSourceTransactionManager">
			<property name="dataSource" ref="dataSource"></property>
		</bean>
	
		<tx:annotation-driven transaction-manager="transactionManager"/>
	서블릿
		<!-- Processes application requests -->
		<servlet>
			<servlet-name>appServlet</servlet-name>
			<servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
			<init-param>
				<param-name>contextConfigLocation</param-name>
				<param-value>
				/WEB-INF/spring/appServlet/servlet-context.xml
				/WEB-INF/spring/root-context.xml	
				</param-value>			
			</init-param>
			<load-on-startup>1</load-on-startup>
		</servlet>
	자바쪽
		//#########
		@Transactional
		@Override
		public void addAll(CustomerVO cvo, MemberVO mvo) throws Exception {
			mdao.insertMember(mvo);
			cdao.insertCustomer(cvo);
			
		}
```
Exception처리 - error페이지
```
	자바쪽
		@ControllerAdvice("com.javassem")
		public class ProjectExceptionHandler {
			
			@ExceptionHandler(Exception.class)
			public String handleException(Exception e, Model m) {
				m.addAttribute("exception", e);
				
				return "error/TransErrorPage";
			}
		}
```
페이징 - paging
```
	클래스
		package vo.paging;
	
		public class PagingVO {
			private int pageNum = 1; // 현재 페이지
			private int startPage = 1; // 첫 페이지 	1 ~ 
			private int endPage = startPage + 9; // 끝 페이지    ~ 10
			private int totalPage = 1; // 총 페이지 수
			private int cnt = 5; // 데이터 목록 개수
			private int startBoard = 1; 
			private int endBoard = startBoard + cnt - 1;
			
			
			public PagingVO() {
		
			}
		
			public PagingVO(int pageNum, int countList) {
				super();
				
				if(pageNum < 1) {
					pageNum = 1;
				}
				
				this.totalPage = (int) Math.ceil((double)countList/cnt);
				
				int index = pageNum % 10 == 0 ? pageNum/10 : pageNum/10 + 1; // 페이지의 번호 확인 후 밑에 보여질 페이지 숫자를 결정
				int startPage = 1 + ((index-1) * 10); // 페이지 10개씩
				int endPage = startPage + 9;
				
				if(this.totalPage < endPage) {
					endPage = this.totalPage;
				}
				
				this.pageNum = pageNum;
				this.startPage = startPage;
				this.endPage = endPage;
				this.startBoard = 1 + ((pageNum-1)*cnt);
				this.endBoard = startBoard + cnt - 1;
			}
			
		
			public int getPageNum() {
				return pageNum;
			}
		
			public void setPageNum(int pageNum) {
				this.pageNum = pageNum;
			}
		
			public int getStartPage() {
				return startPage;
			}
		
			public void setStartPage(int startPage) {
				this.startPage = startPage;
			}
		
			public int getEndPage() {
				return endPage;
			}
		
			public void setEndPage(int endPage) {
				this.endPage = endPage;
			}
		
			public int getTotalPage() {
				return totalPage;
			}
		
			public void setTotalPage(int totalPage) {
				this.totalPage = totalPage;
			}
		
			public int getCnt() {
				return cnt;
			}
		
			public void setCnt(int cnt) {
				this.cnt = cnt;
			}
		
			public int getStartBoard() {
				return startBoard;
			}
		
			public void setStartBoard(int startBoard) {
				this.startBoard = startBoard;
			}
		
			public int getEndBoard() {
				return endBoard;
			}
		
			public void setEndBoard(int endBoard) {
				this.endBoard = endBoard;
			}
		
			
			@Override
			public String toString() {
				return "PagingVO [pageNum=" + pageNum + ", startPage=" + startPage + ", endPage=" + endPage + ", totalPage="
						+ totalPage + ", cnt=" + cnt + ", startBoard=" + startBoard + ", endBoard=" + endBoard + "]";
			}
			
			
		}
	컨트롤러
		PagingVO pVO = new PagingVO(pageNum, memberService.selectMemberCount());
		m.addAttribute("pVO", pVO);
```
깃허브 - gitHub 세팅 참고
```
	https://github.com/devAon/Eclipse-GitHub-Coraboration-Tutorial?tab=readme-ov-file
```
달력
```
	오늘 날짜 기준으로 제한하기
		let now_utc = Date.now() // 지금 날짜를 밀리초로
		// getTimezoneOffset()은 현재 시간과의 차이를 분 단위로 반환
		let timeOff = new Date().getTimezoneOffset()*60000; // 분단위를 밀리초로 변환
		// new Date(now_utc-timeOff).toISOString()은 '2022-05-11T18:09:38.134Z'를 반환
		let today = new Date(now_utc-timeOff).toISOString().split("T")[0];
		$("#birth").attr("max", today);
```
중급자바
```
	Stream : 데이타를 전송하는 가상통로
	JAVA가 기준이 돼서 입출력할 때
	자바의 IO : 표준화
		1. byte형 스트림
			- InputStream - 숫자?? 를 읽을 때 Stream으로 끝남
			- OutputStream - 숫자?? 를 출력할 때 Stream으로 끝남
		2. char형 스트림
			- Reader : 문자를 읽을때 Reader로 끝남
			- Writer : 문자를 출력할 때 Writer로 끝남

	RandomAccessFile : 자바의 입출력스트림이 통합 되어있음
```
파일 쓰기/읽기
```
	파일 쓰기
		public static void main( String args[] ) 
		{
			try
			{
				// a.txt 라는 파일을 생성 후 fos 객체에 주소값 저장
				FileOutputStream fos = new FileOutputStream("a.txt");
				
				for( int ch = 'A'; ch <='Z'; ch++)
				{
					fos.write(ch); // a.txt 파일 안에 A~Z 까지 값을 쓰기
				}
				
				/*
				 * for (int i = 0; i < 5; i++) { fos.write(i); }
				 */
				
				fos.close();
				
			}catch( IOException ex ){
				System.out.println("파일전송실패 :" + ex.toString() );
			}
		}
	파일 읽기
		public static  void main( String args[] ) 
		{
			try
			{
				// a.txt 라는 파일을 fis 객체로 가져옴
				FileInputStream fis = new FileInputStream("a.txt");
	
				for (int i = 0; i < 26; i++) {
					int data = fis.read(); // 파일 내용을 읽어서 int data에 저장
					System.out.print(Character.toChars(data)); // int 형이라서 char 형으로 변환
				}
				
				/*
				 *  EOF : -1 파일이 끝났을 때는 fis.read() 에서 -1 값이 나온다
				 */
				while(true) {
					int data = fis.read(); // 파일 내용을 읽어서 int data에 저장
					if(data == -1) { // EOF : -1 파일이 끝났을 때는 fis.read() 에서 -1 값이 나온다 
						break; // 반복문 벗어나기
					}
					System.out.print(Character.toChars(data)); // int 형이라서 char 형으로 변환
				}
				
				/*
				 * for (int i = 0; i < 5; i++) { fos.write(i); }
				 */
				
				fis.close();
				
			}catch( IOException ex ){
				System.out.println("파일읽기실패 :" + ex.toString() );
			}
		}		
```
파일 쓰기/읽기
```
	파일 쓰기
		public static void main( String args[] ) 
		{
			try
			{
				FileOutputStream fos = new FileOutputStream("b.txt");
		
				int 	numCount = 10;
				int		charCount = 26;
				int 	i = 0;
				byte [] data = new byte[numCount + charCount];
				
				for( i=0; i < numCount; i++)
				{
					data[i] = (byte)i; // data 에 값 저장
				}
				
				for( int ch = 'A'; ch <= 'Z'; ch++, i++)
				{
					data[i] = (byte)ch; // data 에 값 저장
				}
					
				fos.write(data);
				fos.close();
				
			}catch( IOException ex ){
				System.out.println("파일전송실패 :" + ex.toString() );
			}
		}
	파일 읽기
		public static void main( String args[] ) 
		{
			try
			{
				FileInputStream fis = new FileInputStream("b.txt"); // b.txt 파일 읽어오기
				byte[] data = new byte[1024]; // byte 배열 data 생성 크기는 1024
				int count = fis.read(data); // fis 의 내용을 data 배열에 담음
				
				// data에는 file 내용 count 안에 file 크기가 있음
				for (int i = 0; i < count; i++) {
					System.out.println((char)data[i]);
					
				}
				
				fis.close();
				
			}catch( Exception ex ){
				System.out.println("파일전송실패 :" + ex.toString() );
			}
		}		
```
파일 쓰기/읽기
```
	파일 쓰기
		// 파일을 생성하는데 데이터를 필터링 해주는 클래스
		DataOutputStream dos = new DataOutputStream(new FileOutputStream("data.txt"));
		
		dos.writeUTF(name);
		dos.writeInt(age);
		dos.writeDouble(height);
		dos.writeChar(bloodType);
		
		dos.close();
	파일 읽기
		// 파일을 생성하는데 데이터를 필터링 해주는 클래스
		DataInputStream dis = new DataInputStream(new FileInputStream("data.txt"));
		
		name = dis.readUTF();
		age = dis.readInt();
		height = dis.readDouble();
		bloodType = dis.readChar();
		
		tfName.setText(name);
		tfAge.setText(String.valueOf(age));
		tfHeight.setText(String.valueOf(height));
		tfBloodType.setText(String.valueOf(bloodType));
```
파일 객체 쓰기/읽기
```
	객체를 직렬화를 해야함 - implements Serializeble
	VO 파일
		public class DataVO implements Serializable{
		private String name;
		private int age;
		private double height;
		private char bloodType;
	파일 쓰기
		// 객체를 담아서 파일 생성
		ObjectOutputStream oos = new ObjectOutputStream(new FileOutputStream("data2.txt"));
		DataVO dataVO = new DataVO(name, age, height, bloodType);
		oos.writeObject(dataVO);
		
		oos.close();
	파일 읽기
		ObjectInputStream ois = new ObjectInputStream(new FileInputStream("data2.txt"));
				
		DataVO dataVO = new DataVO(); // 클래스 객체 생성
		dataVO = (DataVO) ois.readObject(); // 파일안에 객체를 dataVO 객체에 담는다
		
		tfName.setText(dataVO.getName());
		tfAge.setText(String.valueOf(dataVO.getAge()));
		tfHeight.setText(String.valueOf(dataVO.getHeight()));
		tfBloodType.setText(String.valueOf(dataVO.getBloodType()));
		
		ois.close();
```
파일 파일 선택저장/파일 선택열기
```
	파일 선택저장
		// 파일 선택 저장
		JFileChooser fd = new JFileChooser();
		int returnValue = fd.showSaveDialog( null );
		if( returnValue == JFileChooser.APPROVE_OPTION )
		{
			File f = fd.getSelectedFile();
			try{
				/** 
				 * @@@@@@@@@@@@@@@@@@@@@@@@@
				 * */
				try{
					/** 
					 * @@@@@@@@@@@@@@@@@@@@@@@@@
					 * */
					FileWriter out = new FileWriter(f);
					
					out.write(ta.getText());
					
					out.close();
					
				}catch(Exception ex){
					System.out.println("열기 실패");
				}	
				
			}catch(Exception ex){
				System.out.println("저장 실패");
			}	
		}
	파일 선택열기
		// 파일 선택 열기
		JFileChooser fd = new JFileChooser();
		int returnValue = fd.showOpenDialog( null );
		if( returnValue == JFileChooser.APPROVE_OPTION )
		{
			File f = fd.getSelectedFile();
			try{
				/** 
				 * @@@@@@@@@@@@@@@@@@@@@@@@@
				 * */
				FileReader out = new FileReader(f);
				char[] data = new char[1024*5];
				
				while(true) {
					int result = out.read(data);
					if(result == -1) {
						break;
					}
				}
				
				ta.setText(String.valueOf(data));
				
				out.close();
				
			}catch(Exception ex){
				System.out.println("열기 실패");
			}	
		}
```
쓰레드 (Thread)
```
	프로세서 (processer)
		- cpu
	프로세스 (process)
		- 실제 cpu 가 실행하고 있는 프로그램
	쓰레드 (thread)
		- 하나의 프로세스에서 독립적인 작업
	자바의 쓰레드 동작과정
		1. 쓰레드클래스 생성
			- Thread 클래스 상속
			- Runnable 인터페이스 구현
			- run() overriding
		2. 클래스 객체 생성
			- 클래스 객체 생성 후 1번 객체 생성
		3. 쓰레드의 run() 호출
			- start() -> run() 호출
		4. 메소드
			- join() 해당 쓰레드가 끝날때까지 기다림
			- wait() 해당 쓰레드를 잠시 대기시킴
			- 
```
쓰레드 프로그램 - extends Thread
```
	package thread.basic;

	public class Ex1_ThreadTest {
		public static void main(String[] args) {
			MakeCar1 car1 = new MakeCar1("람보르기니");
			car1.start();
			
			MakeCar1 car2 = new MakeCar1("아우디");
			car2.start();
			
			System.out.println("주행 종료");
		}
	}
	
	class MakeCar1 extends Thread{
		String work;
		
		public MakeCar1(String work) {
			this.work = work;
		}
		
		public void run() {
			for (int i = 0; i < 5; i++) {
				System.out.println(work + " 작업 중");
				
				try {
					Thread.sleep(2000);
				} catch (InterruptedException e) {
					e.printStackTrace();
				}
			}
		}
	}
```
쓰레드 프로그램 - implements Runnable
```
	package thread.basic;

	public class Ex2_RunnableTest {
		public static void main(String[] args) {
			MakeCar2 mc1 = new MakeCar2("차틀만들기");
			Thread t1 = new Thread(mc1);
			t1.start();
			
			MakeCar2 mc2 = new MakeCar2("엔진부착");
			Thread t2 = new Thread(mc2);
			t2.start();
		}
	}
	
	class MakeCar2 implements Runnable{
		String work;
		
		public MakeCar2(String work) {
			this.work = work;
		}
	
		@Override
		public void run() {
			for (int i = 0; i < 5; i++) {
				System.out.println(work + " 작업 중");
				
				try {
					Thread.sleep(500);
				} catch (InterruptedException e) {
					e.printStackTrace();
				}
			}
		}
		
	}
```
위에 코딩 축약
```
	package thread.basic;

	public class Ex2_RunnableTest {
		public static void main(String[] args) {
			new Thread(new MakeCar2("차틀만들기")).start();
			new Thread(new MakeCar2("엔진부착")).start();
		}
	}
	
	class MakeCar2 implements Runnable{
		String work;
		
		public MakeCar2(String work) {
			this.work = work;
		}
	
		@Override
		public void run() {
			for (int i = 0; i < 5; i++) {
				System.out.println(work + " 작업 중");
				
				try {
					Thread.sleep(500);
				} catch (InterruptedException e) {
					e.printStackTrace();
				}
			}
		}
		
	}
```
### 동기화
```
	synchronized : 동기화 작업 (동시 다발적인 실행으로 값이 정확하지 않을 때)
		// 멀티 쓰레드가 구동할 때 값이 정확하지 않을때 synchronized 를 써야한다
		// 또는 여러명이서 예매를 하는 경우?
		void increment() {
			synchronized(this) {
				i++;
			}
		}
```
### 쓰레드 빵 예문
```
	package thread.basic;

	class Bread 
	{
		String bread;
	
		//##
		boolean isCheck = false;
	
		public void setBread( String bread )
		{
			this.bread = bread;
			//## 		
			isCheck = true;
			synchronized (this) {
				notifyAll(); // 다시 작업 실행
			}
		}	
	
		public String getBread()
		{
			//## 		
			if(isCheck == false) {
				try {
					synchronized (this) {
						wait(); // 작업 대기
					}
				} catch (Exception e) {
					
				}
			}
			return bread;
		}
	}
	
	class Baker extends Thread
	{
		Bread bbang;
	
		Baker( Bread bbang )
		{
			this.bbang = bbang;
		}
		public void run()
		{
			bbang.setBread("진열된 완성된 맛있는 빵");
		}
	}
	
	class Customer extends Thread
	{
		Bread bbang;
	
		Customer( Bread bbang )
		{
			this.bbang = bbang;
		}
		public void run()
		{
			System.out.println("빵을 사감 : " + bbang.getBread());
		}
	}
	
	class Ex8_BreadTest
	{
		public static void main(String[] args) 
		{
			Bread  bread = new Bread();
	
			Baker  baker = new Baker( bread );
			Customer customer = new Customer( bread );
			customer.start();
			baker.start();
	
			try{
				customer.join();
				baker.join();			
			}catch( Exception ex ){}
	
		}
	}
```
### 통신
```
	용어
		- Protocol : 통신의 규칙
			[ex] HTTP / SMTP / FTP....
		- 네트워크 기본 이론 : OSI 7 계층
			IP(3단계)
			TCP / UDP(4단계)
				Transfer Control Protocol
				User Datagram Protocol
	네트워크의 기본 요소
		(*) 알고 있어야 되는 정보
		PORT 번호 0 ~ 65535(2의16승)
			0 : x
			1 ~ 1023 : 시스템 포트번호
			1024 ~ :
										
				- 클라이언트
					TCP / UDP
					본인 IP
					본인 PORT
					서버 IP(*)
					서버 PORT(*)
				- 서버
					TCP / UDP
					서버 IP
					서버 PORT(*)
					사용자 IP
					사용자 PORT
	
						
```
### 채팅
```
	서버
		package network3.chat;

		import java.io.ObjectInputStream;
		import java.io.ObjectOutputStream;
		import java.net.ServerSocket;
		import java.net.Socket;
		import java.util.ArrayList;
		import java.util.StringTokenizer;
		
		
		public class ChatServer implements Runnable {
			ArrayList vc = new ArrayList();
		
			public void run() {
				ServerSocket ss = null;
				try{
					ss = new ServerSocket(1234);
				}catch( Exception e ) {
					System.out.println(e);
				}
		
				while(true) {
					try{
						Socket s = ss.accept();
						System.out.println("Client 가 접속시도 :" + s );
						ChatService cs = new ChatService(s);
						cs.start();
						vc.add(cs);
		
					} catch( Exception e ) { }
				}
			}  // run ends
		
			public static void main( String [] arg ) {
				ChatServer cs = new ChatServer();
				new Thread(cs).start();
			}
		
		
		
			class ChatService extends Thread {
				String myname = "quest";
				ObjectInputStream in;
				ObjectOutputStream out;
				ChatService( Socket s ) {
					try{
						out = new ObjectOutputStream(s.getOutputStream());
						in = new ObjectInputStream(s.getInputStream());
						
					}catch( Exception e ) {
						System.out.println("소켓스트림 실패");
						e.printStackTrace();
					}
				}// 생성자 종료
		
		
		
				public void run() {
					while(true) {
						try{
							DataToServer dts = (DataToServer)in.readObject();
							String msg = (String)dts.getData();
							int state = dts.getState();
							System.out.println("상태:" + state);
		
							switch(state)
							{	
							case DataToServer.SEND_MESSAGE : 
								putMessageAll( myname + ">" + msg );
								break;
							case DataToServer.CHANGE_NAME :
								putMessageAll( myname + "님이 대화명을 " + msg +"으로 변경하였습니다" );
								this.myname = msg;						
								break;
							}
		
		
						}catch( Exception ex ) { return; }
		
					}
				}// run ends
		
		
				void putMessageAll( String msg ) {
					for( int i =0 ; i<vc.size() ; i++ ) {
						ChatService cs = ( ChatService ) vc.get(i);
		
						try {
							cs.putMessage(msg);
						}catch( Exception e ) {
							vc.remove(i--);
						}
					}
				} // putMessageAll ends
		
				void putMessageTo( String towhom, String msg ) {
					for( int i=0; i<vc.size() ; i++ ) {
						ChatService cs = ( ChatService ) vc.get(i);
						if( towhom.equalsIgnoreCase( cs.myname )) {
							try{
								cs.putMessage( towhom +">"+ msg);
								break;
							}catch( Exception ex ) { }
						}
					}
				} // putMessageTo ends
		
				void putMessage( String msg )
						throws Exception {
					DataToClient dtc = new DataToClient();
					dtc.setData(msg);
					dtc.setState(DataToClient.SEND_MESSAGE);
					out.writeObject( dtc);
				}
		
			} // ChatService class ends
		
		
		}// ChatServer class ends
	클라이언트
		package network3.chat;

		import java.awt.BorderLayout;
		import java.awt.GridLayout;
		import java.awt.event.ActionEvent;
		import java.awt.event.ActionListener;
		import java.awt.event.WindowAdapter;
		import java.awt.event.WindowEvent;
		import java.io.IOException;
		import java.io.ObjectInputStream;
		import java.io.ObjectOutputStream;
		import java.net.Socket;
		import java.util.StringTokenizer;
		import java.util.Vector;
		
		import javax.swing.JButton;
		import javax.swing.JFrame;
		import javax.swing.JLabel;
		import javax.swing.JList;
		import javax.swing.JPanel;
		import javax.swing.JScrollPane;
		import javax.swing.JTextArea;
		import javax.swing.JTextField;
		
		class ChatClient implements ActionListener, Runnable {
			JFrame f;
		
			JTextField connTF, sendTF;
			JButton connB, sendB;
			JTextArea ta;
			
			Socket s;
			ObjectInputStream in;
			ObjectOutputStream out;
		
			// 추가2 : 대화명을 바꾸기
			JTextField changeNameTF;
			JButton    changeNameB;
		
			
			// 추가 : 방인원의 대명 보여주기
			JList  memberList;
			Vector list;
			
			
		
		
			public ChatClient() {
				f = new JFrame("Chat Client");
				
		
				connTF = new JTextField("127.0.0.1");
				sendTF = new JTextField();
				connB = new JButton("접 속");
				sendB = new JButton("확 인");
				ta = new JTextArea(15,40);
				
				// 추가0: 대화명 바꾸기
				changeNameTF	= new JTextField("guest", 10);
				changeNameB		= new JButton("바꾸기");
				JPanel p_changeName = new JPanel();
				p_changeName.add( new JLabel("대화명 : "),"West" );
				p_changeName.add(changeNameTF, "Center");
				p_changeName.add(changeNameB, "East");
				
				JPanel p_serverName = new JPanel();
				p_serverName.setLayout( new BorderLayout() );
				p_serverName.add( new JLabel("서버입력 : "),"West" );
				p_serverName.add(connTF, "Center");
				p_serverName.add(connB, "East");
		
				JPanel p_north = new JPanel();
				p_north.setLayout( new GridLayout(1, 2));
				p_north.add( p_changeName );
				p_north.add( p_serverName );
		
				JPanel p2 = new JPanel();
				p2.setLayout( new BorderLayout() );
				p2.add( new JLabel("메세지입력 : "),"West" );
				p2.add(sendTF,"Center");
				p2.add(sendB, "East");
				
				// 추가2 : 방인원의 대명 보여주기
				memberList = new JList();
				list		= new Vector();
				JPanel  p_east = new JPanel();
				p_east.setLayout( new BorderLayout());
				p_east.add("North", new JLabel("   우 리 방 멤 버   "));
				p_east.add("Center", memberList );
				
		
		
				f.getContentPane().add("North", p_north);
				f.getContentPane().add("Center", new JScrollPane(ta));
				f.getContentPane().add("South", p2);
				f.getContentPane().add("East", p_east);
				
				//f.setSize(500, 300);
				f.pack();
				f.setVisible(true);
				
				connTF.addActionListener(this);
				connB.addActionListener(this);
				sendTF.addActionListener(this);
				sendB.addActionListener(this);
		
				//  추가0: 대화명 바꾸기
				changeNameTF.addActionListener(this);
				changeNameB.addActionListener(this);
			}// 생성자 종료
			
			public void actionPerformed( ActionEvent e ) {
				Object o = e.getSource();
		
				if( o == connTF || o == connB ) {
					connProc();
				}
				
				else if( o == sendTF || o == sendB ) {
					sendProc();
				}
		
				//  추가0: 대화명 바꾸기
				else if( o == changeNameTF || o == changeNameB ) {
					changeNameProc();
				}
			} // actionPerformed ends
			
			// [4] 입력한 대화명을 서버로 변경
			void changeNameProc(){
				try{
					DataToServer dts = new DataToServer(); 
					dts.setData(changeNameTF.getText());
					dts.setState(DataToServer.CHANGE_NAME);
					
					out.writeObject(dts); // 서버에게 메세지와 상태 값을 보내기
					
				} catch( Exception ex ) {
					ta.append(ex + "\n" );
				}
				
			}
		
			// [1] 서버에 접속
			void connProc() {						
				try{
					s = new Socket(connTF.getText(), 1234);
					out = new ObjectOutputStream(s.getOutputStream()); // 채팅 보내기
					in = new ObjectInputStream(s.getInputStream()); // 채팅 받기
					// [2] 쓰레드 구동
					//	2-1. Thread/Runnable 
					//	2-2. run() overriding
					//	2-3. start() 호출
					new Thread(this).start();
				} catch(Exception ex) {
					ta.append( ex.toString() );
				}
			} // connProc ends
			
			@Override
			public void run() {
				while (s.isConnected()) { // 소켓이 연결되어 있는 동안 반복
					try {
						DataToClient dtc = (DataToClient)in.readObject(); // 서버가 보내주는 객체 받기
						String msg = (String)dtc.getData();
						int state = dtc.getState();
						
						switch(state) {
						case DataToClient.SEND_MESSAGE:
							ta.append(msg + "\n"); // ta에 메세지 출력
							break;
						}
						
					} catch (Exception e) {
						return;
					} 
					
				}
				
			}
		
			// [3] 입력한 메세지를 서버로 전송
			void sendProc() {
				try{
					DataToServer dts = new DataToServer(); 
					dts.setData(sendTF.getText());
					dts.setState(DataToServer.SEND_MESSAGE);
					
					out.writeObject(dts); // 서버에게 메세지와 상태 값을 보내기
					sendTF.setText(""); // 보낸 메세지는 비워주기
				} catch( Exception ex ) {
					ta.append(ex + "\n" );
				}
			}// sendProc ends
			
			
			public static void main(String [] args ) {
				new ChatClient();
			}
		
			
			
		}// ChatClient ends
```
### 파이썬
```
	1. 파이썬 설치
	    anaconda
	        https://www.anaconda.com/download
	    IDE : Pycharm
	        https://www.jetbrains.com
	2. 평가 - atosoft
	3. 과제 : oracle cloud 회원가입
	- 본인 핸드폰번호 / 카드
	- 이메일주소(oracle site 등록되지 않은 이메일)
	- 주소 (네이버 영어주소 검색)

	[ 기초 연산자 ]
		+ : 더하기
		- : 빼기
		* : 곱하기
		/ : 나누기(실수값 결과)
		// : 나누기(정수값 결과)
		% : 나머지
		** : 자승 (n제곱)
		
		2. 관계연산자
		<   >   <=  >=  ==  !=
		
		3. 논리연산자
		not     or      and
		
		4. 대입연산자
		=
		+=  -=  *=  /=  //= %=
		&=  |=  ^=
		>>= <<=
		
		5. 기타연산자 : 딕셔너리, 문자열, 리스트, 튜플 등의 자료형에서 사용
		is      : 비교하는 객체의 주소가 같으면 true, 다르면 false
		is not  : 비교하는 객체의 주소가 다르면 true, 같으면 false 
		in      : 요소에 포함되면 true, 없으면 false
		not in  : 요소에 포함되지 않으면 false, 없으면 true    
	[참고]
		증가(++), 감소(--) 연산자 없음
		문자열 합치기
			문자열 + 문자열
		문자열 반복
			문자열 * 숫자
		문자열 + 숫자
			에러 발생
		변수명으로 str 금지!

		문자열의 인덱싱과 슬라이싱
		        인덱스는 0부터 시작한다
		        s[i] : s 문자열에서 i번째 문자 추출
		        s[i:j] : s 문자열에서 i번째에서 j-1까지의 문자 추출
		        s[i:j:k] : s 문자열에서 i번째에서 j-1까지에서 k개씩 건너뛰어 문자 추출
		        s[-i] : s 문자열에서 뒤에서부터 i번째 문자 추출( 뒤에서 인덱스는 1부터 센다 )
			msg[0] == msg[-0] 같은 값을 추출
		        msg[:] 전체 추출
		        msg[i:-j] i번째부터 뒤에서 j-1 까지 추출
		문자열 관련 함수
			s.count('글') : s 문자열에서 '글'이라는 문자 개수 세기
		        s.index('글') : s 문자열에서 문자 '글' 위치 알려주기
		        s.find('글') : s 문자열에서 문자 '글' 위치 알려주기
		        s.rfind('글') : s 문자열에서 문자 '글' 오른쪽에서 왼쪽으로 찾아서 위치 알려주기
		        len(s) : s 문자열 길이
			s.upper() : 소문자를 대문자로
			s.lower() : 대문자를 소문자로
			s.lstrip() : 왼쪽 공백 지우기
			s.rstrip() : 오른쪽 공백 지우기
			s.strip() : 양쪽 공백 지우기
			s.replace("a","b")  :  s 문자열에서 단어 a를 단어 b로 바꾸기
			s.split() : s 문자열을 공백으로 나누기
			s.split('z') : s 문자열을 z 기호로 나누기
			d.join(s) : d 단어를 s 문자열에 삽입
			msg = "{}님 오늘도 행복하세요"

			print(msg.format("홍길자"))
			print(msg.format("홍길국"))
		브레이스
			msg = "{}님 오늘도 행복하세요 - {}로부터"
			print(msg.format("홍길동","ICT"))
			
			msg = "{0}님 오늘도 행복하세요 - {1}로부터"
			print(msg.format("홍길동","ICT"))
			
			msg = "{1}님 오늘도 행복하세요 - {0}로부터"
			print(msg.format("홍길동","ICT"))

			msg = "{name}님 오늘도 행복하세요 - {group}로부터"
			print(msg.format(name="홍길동",group="ICT"))
		소수
			print("내가 좋아하는 숫자는 {0:.2f}입니다".format(su))
			print("내가 좋아하는 숫자는 %.2f입니다"%su)
			print("%s 님은 %d살이고 신장은 %f cm입니다" %(name,age,height))
		boolean
			
			print() 콘솔 출력
			int() 정수형으로
			float() 소수
			str() 문자열로
			type() 타입을 볼수 있음
	리스트, 셋, 튜플
		t = [1,2,3] # list
		t = {1,2,3} # set
		t = (1,2,3) # tuple

		리스트 관련 함수들
			append()    : 요소 추가
			sort()      : 리스트 정렬
			reverse()   : 역순으로 뒤집기
			index()     : 위치 반환
			insert()    : 리스트에 요소 삽입
			remove()    : 요소 제거
			pop()       : 맨 마지막 요소를 꺼내기
			count()     : 요소 개수 세기
			extend()    : 리스트에 리스트를 더하기\
			clear()     : 모든 요소를 제거
		Set 관련 함수들
			print(s.union(p)) # 중복없는 합집합
			print(s.intersection(p)) # 교집합
		dictionary 관련 함수들
			dt = {1:'one', 2:'two', '3':'three'}

			사전.keys() : key만 추출 (임의의 순서)
			사전.values() : value만 추출 (임의의 순서)
			사전.items() : key와 value를 튜플로 추출 (임의의 순서)
			사전['korea'] = 'seoul' # 추가
			사전['korea'] = 'seoul2' # 수정
			사전.update({5:'five',6:'six',7:'seven'}) # 여러개 추가
			사전.update({5:'five2',6:'six2',7:'seven2'}) # 여러개 수정
			print(dt2.get(6,"키값없음")) # 있으면 value 값 없으면 "키값없음"
		튜플
			리스트와 유사하지만 값 변경 불가
			튜플 객체 전체는 삭제 가능
			t4 = (1,) - 요소 1개만 넣고 싶을때
		반복문
			(2) for문
			        for <타켓변수> in 집합객체 :
			            문장들
			        else:
			            문장들
			
			        ` 반복문 뒤에 else는 반복하는 조건에 만족하지않으면 실행
		
		   	(3) while 문
			        while 조건문 :
			            문장들
			        else :
			            문장들
		# enumerate 함수 : 각 요소와 인덱스를 같이 추출
			user_list = ["개발자","코더","전문가","분석가"]
			for idx,i in enumerate(user_list):
			    print("{}, {}".format(idx,i))
		언팩킹
			msg = '행복해'            # 문자열
			li = ['a','b','c']       # 리스트
			tpl = ('ㄱ','ㄴ','ㄷ')    # 튜플
			di = {'k': 5, 'j': 6, 'l':7 }    # 딕셔너리

			x,y,z = di.items()

			print(x) # ('k', 5)
			print(y) # ('j', 6)
			print(z) # ('l', 7)
		# zip 함수 : 각 인덱스로 묶어준다
			days = ["월","화","수"]
			doit = ["잠자기","공부","놀기","밥먹기"]
			month = [5,6,7]
			print(list(zip(days,doit,month)))
			# [('월', '잠자기', 5), ('화', '공부', 6), ('수', '놀기', 7)]
		@ 컴프리핸션 (comprehension)
			` 하나 이상의 이터레이터로부터 파이썬 자료구조를 만드는 컴팩트한 방법
			` 비교적 간단한 구문으로 반복문과 조건 테스트를 결합
			
			* 리스트 컨프리핸션
				[ 표현식 for 항목 in 순회가능객체 ]
				[ 표현식 for 항목 in 순회가능객체 if 조건 ]
			
			* 딕셔러리 컨프리핸션
				{ 키_표현식: 값_표현식 for 표현식 in 순회가능객체 }
			
			* 셋 컨프리핸션
				{ 표현식 for 표현식 in 순회가능객체 }
		# 리스트 컨프리핸션
			blist = [n for n in range(1,7)]
			print(blist) # [1, 2, 3, 4, 5, 6]
			
			blist = [n-1 for n in range(1,7)]
			print(blist) # [0, 1, 2, 3, 4, 5]
			
			blist = [n*2 for n in range(1,7)]
			print(blist) # [2, 4, 6, 8, 10, 12]
			
			blist = [n for n in range(1,7) if n%2 == 0]
			print(blist) # [2, 4, 6]
		# 딕셔너리 컨프리핸션
			data = (1,2,3,3,2,4,5)
			aList = [n for n in data]
			print(aList) # list [1, 2, 3, 3, 2, 4, 5]
			
			aset = {n for n in data}
			print(aset) # set {1, 2, 3, 4, 5}
			
			atuple = {n:n**2 for n in data}
			print(atuple) # dictionary {1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
			
			word = "LOVE LOL"
			wcnt = {letter:word.count(letter) for letter in word}
			print(wcnt) # {'L': 3, 'O': 2, 'V': 1, 'E': 1, ' ': 1}
			
			
			print("*"*50)
			clist = []
			for r in range(1,4):
			    for c in range(1,3):
			        clist.append((r,c))
			print(clist) # [(1, 1), (1, 2), (2, 1), (2, 2), (3, 1), (3, 2)]
			
			print("*"*50)
			dlist = [(r,c)for r in range(1,4) for c in range(1,3)]
			print(dlist) # [(1, 1), (1, 2), (2, 1), (2, 2), (3, 1), (3, 2)]
			print("*"*50)
	함수
		함수생성
			def func():
			f= lambda x,y : x*y - 인자 : 리턴
		특수한기능 - 리턴 값이 여러 개가 가능하다 	
			def func(arg):
    				return arg+5, arg-6
			x,y = func(10) # 언팩킹 도 가능
			print(x,y)
		# 키워드인자(keyword argument)
			func(name="김기동",greeting="헬로우")
		인자 기본값 설정이 가능
			def func(greeting, name="홍길동"):
		# 인자 1개에 여러개 값 받기
			def func(one, two, three=100, *args, **kwargs):
			    sum = one + two + three
			    print("four= ",args)
			    print("kwargs= ",kwargs)
			    for i in args:
			        sum += i
			    for i in kwargs:
			        sum += kwargs[i]
			    return sum
			
			print(func(1,2))
			print(func(1,2,3))
			print(func(1,2,3,4,5,6))
			print(func(1,2,3,java=40,kor=20,eng=20))
			print(func(1,2,3,4,kor=100,math=200))
	맵리듀스
		def calc(x):
		    return x*2
		data = [1,2,3,4,5]
		result = list(map(calc, data))
		print(result) # [2,4,6,8,10]
	모듈
		[정리]
			* 함수 : 파일 내에서 일정한 작업을 수행하는 코드 블록
			* 모듈 : 함수나 클래스들의 파일
				모듈이름은 py 확장자를 제외한 파일 이름
			* 패키지 : 여러 모듈들을 모아놓은 디렉토리
				패키지 = 디렉토리
				모듈 = 파일
		[ 모듈 ]
			- 자주 사용되는 함수를 매번 작성하지 않고 하나의 모듈로 사용하여 재사용
			- 모듈 단위로 분리하여 설계함으로 작업의 효율을 높임
			- 동일한 함수나 클래스를 모듈로 관리
				` 표준 모듈 : 파이썬 안에 기본적으로 제공하는 모듈
				` 사용자 정의 모듈 : 개발자가 직접 정의한 모듈
		# import mymodule
		#
		# print('오늘의 날씨는 ',mymodule.get_weather())
		# print('오늘은 ', mymodule.get_date(),'입니다')
		
		from mymodule import get_weather, get_date
		
		print('오늘의 날씨는 ',get_weather())
		print('오늘은 ', get_date(),'입니다')
	# 시작점 지정 - 실행 파일에는 __name__ 변수에 __main__ 문자열이 들어가 있음
		if __name__ == '__main__':
				
```
### 파이썬 클래스
```
	클래스
		__init__ 함수 : 객체 초기화 함수( 생성자 역할 )
     		self : 객체 자신을 가리킨다.
		class Sample:
		    data = "데이타"
		    def __init__(self, name): # 생성자 함수
		        self.name = name
		        print("__init__ 호출")
		    def __del__(self): # 소멸자 함수
		        print(self.data)
		
		s = Sample("홍길동") # 객체 생성
		print(s.name,s.data) # 멤버변수
		print(dir(s))
		del s
	클래스 static
		class Book:
		    cnt = 0
		
		    def __init__(self,title): # 생성자
		        self.title = title # 책 제목
		        self.cnt += 1 # 책 권수
		    def output(self):
		        print("제목:",self.title)
		        print("책 권수:",self.cnt)
		    @classmethod # static 같은 느낌?
		    def output2(cls):
		        cls.cnt += 1
		        print("책 권수:",cls.cnt) # 이렇게 해야 cnt 개수가 알맞게 올라감
		
		
		b1 = Book("혜경나쁜") # 객체생성
		b2 = Book("정말나쁜") # 객체생성
		
		b1.output() # 메소드 실행
		b2.output() # 메소드 실행
		print("1>", "-"*30)
		
		b1.output2() # static 메소드 실행
		b2.output2() # static 메소드 실행
		print("2>", "-"*30)
		
		Book.output2() # 클래스 명으로 접근 가능
```
### 파이썬 상속
```
	# 상속
		class Animal:
		    def move(self):
		        print("동물은 움직인다")
		
		class Wolf(Animal): # Animal 상속
		    def move(self): # override
		        print("늑대는 4발로 달린다")
		
		class Human(Animal): # Animal 상속
		    def move(self): # override
		        print("인간은 2발로 달린다")
		
		class WolfHuman(Human,Wolf): # Wolf, Animal 상속
		    def move(self): # override
		        super().move() # 부모의 메소드를 실행하는데 먼저 상속 받은 메소드가 실행된다.
		        print("늑대인간은 2발로 달린다")
		
		w = WolfHuman()
		w.move()
```
### 파이썬 매직메소드
```
	매직 메소드

		(1) Binary Operators
		        Operator	Method
		        +	    object.__add__(self, other)
		        -	    object.__sub__(self, other)
		        *	    object.__mul__(self, other)
		        //	    object.__floordiv__(self, other)
		        /	    object.__div__(self, other)
		        %	    object.__mod__(self, other)
		        **	    object.__pow__(self, other[, modulo])
		        >>	    object.__lshift__(self, other)
		        <<	    object.__rshift__(self, other)
		        &	    object.__and__(self, other)
		        ^	    object.__xor__(self, other)
		        |	    object.__or__(self, other)  
		        
		(2) Comparison Operators
		        Operator	Method
		        <	    object.__lt__(self, other)
		        <=	    object.__le__(self, other)
		        ==	    object.__eq__(self, other)
		        !=	    object.__ne__(self, other)
		        >=	    object.__ge__(self, other)
		        >	    object.__gt__(self, other)
		                
		(3) Extended Assignments
		        Operator	Method
		        +=	    object.__iadd__(self, other)
		        -=	    object.__isub__(self, other)
		        *=	    object.__imul__(self, other)
		        /=	    object.__idiv__(self, other)
		        //=	    object.__ifloordiv__(self, other)
		        %=	    object.__imod__(self, other)
		        **=	    object.__ipow__(self, other[, modulo])
		        <<=	    object.__ilshift__(self, other)
		        >>=	    object.__irshift__(self, other)
		        &=	    object.__iand__(self, other)
		        ^=	    object.__ixor__(self, other)
		        |=	    object.__ior__(self, other)
		          
		(4) Unary Operators
		        Operator	Method
		        -	        object.__neg__(self)
		        +	        object.__pos__(self)
		        abs()	    object.__abs__(self)
		        ~	        object.__invert__(self)
		        complex()	object.__complex__(self)
		        int()	    object.__int__(self)
		        long()	    object.__long__(self)
		        float()	    object.__float__(self)
		        oct()	    object.__oct__(self)        
		        hex()	    object.__hex__(self)
		"""
		
		class Sample:
		    def __init__(self,name,age): # 생성자
		        self.name = name
		        self.age = age
		
		    def __str__(self): # 매직메소드
		        return "이름: {0}, 나이: {1} \n".format(self.name,self.age)
		
		    def __add__(self, other): # 매직메소드
		        self.age += other
		
		    def __gt__(self, other): # 매직메소드
		        if self.age > other:
		            return "성인입니다"
		        else:
		            return "미성년입니다"
		
		    def __bool__(self):
		        return self.name == "홍길동"
		
		s = Sample("헤경똥",22)
		print(s) # __str__
		
		s + 10 # 매직메소드가 있으면 이것이 된다고?
		print(s) # __add__
		
		print(s > 20) # __gt__
		
		if s: # __bool__
		    print("홍길동 본인")
		else:
		    print("홍길동 본인이 아닙니다")
```
### 파이썬 예외처리
```
	[에러와 예외]
	    1. 에러
	        문법적 오류
	    2. 예외
	        실행시 발생하는 오류로 예외가 발생하면 프로그램이 비정상 종료된다
	
	    [예외처리]
	    try:
	        예외 발생 가능 문장들
	    except Exception:
	        예외가 발생한 후에 실행할 문장들
	    else:
	        예외가 발생하지 않았을 때 실행되는 문장들
	    finally:
	        예외 발생 여부와 상관없이 무조건 실행되는 문장들
	
	    [참고] 파이썬 내장 예외
	        https://docs.python.org/3/library/exceptions.html

		try: # 예외가 발생할 거 같은 부분
		     10/0
		except Exception as e: # 예외가 발생했을 때 실행 되는 부분 (catch)
		    print("예외",e)
		else: # 예외가 없을 때 실행
		    print("예외 없음")
		finally: # 무조건 실행
		    print("무조건 실행")
```
### 파이썬 파일
```
	@ 파일 읽고 쓰기
	    - 파일을 읽고 쓰기 전에 파일을 열어야 한다
	    - fileObj = open ( filename, mode )
	            mode 첫번째 글자 - 작업 표시
	            r(read)  : 파일 읽기
	            w(write) : 파일 쓰기 ( 파일이 없으면 생성하고 파일이 있으면 덮어쓴다 )
	            x(write) : 파일 쓰기 ( 파일이 없을 때만 생성하고 쓴다 )
	            a(append) : 파일 추가 ( 파일이 있으면 파일의 끝에서부터 추가하여 쓴다 )
	
	            mode 두번째 글자 - 파일 타입
	            t : 텍스트(text) 타입 ( 기본값 )
	            b : 이진(binary) 타입
	            두번째 글자가 없으면 텍스트 타입이다.
	
	            encoding='utf-8' : 한글
	
	    - 파일을 열고 사용 후에는 반드시 닫아야 한다
	파일 읽기 - data.txt 파일 읽기
		try:
		    f = open('./data/data.txt','r',encoding='utf-8') # 파일 읽기
		except FileNotFoundError as e: # 예외 발생
		    print("파일을 찾을 수 없습니다.",e)
		else: # 정상작동
		    while True:
		        line = f.readline() # 파일 한 줄 씩
		        if not line: # 파일 내용이 없으면
		            break # 정지
		        print(line, end='') # 한 줄 읽어온 내용을 출력
		    f.close()  # 스트림 닫기
		finally:
		    print('\n\n종료')
```
### 파이썬 파일 읽기 자동 close
```
	# 자동으로 close - with 이용
	with open('./data/data.txt','r',encoding='utf-8') as f: # 파일 읽기
	    while True:
	        line = f.readline() # 파일 한 줄 씩
	        if not line: # 파일 내용이 없으면
	            break # 정지
	        print(line, end='') # 한 줄 읽어온 내용을 출력
```
### 파이썬 파일 읽기
```
	filename = './data/data.txt' # 파일 경로
	try:
	    with open(filename,'rt',encoding='utf-8') as f: # 파일 읽기 자동 close
	        content = f.read()  # 파일 내용을 고대로 가져옴
	        # print(content)
	        words = content.split()  # 파일 내용을 띄어쓰기로 쪼개서 리스트로 담음
	        print(words)
	        num = len(words)  # 리스트의 길이
	except Exception as e: # 예외 발생
	    print("파일 읽기 예외",e)
	else: # 정상 작동
	    print('파일명:', filename, '총 단어수:', num)
```
### 파이썬 파일 읽기 연습
```
	"""
	[연습]
	    함수 정의 : count_words
	    인자 : filename
	
	    인자로 받은 파일명을 open 하여 파일을 읽어서 단어를 수를 출력한다.
	    존재하지 않는 파일명으로 예외가 발생해도 아무런 일을 하지 않는다
	"""

	def count_words(filename):
	    fname = './data/' + filename
	    try:
	        with open(fname,'r',encoding='utf-8') as f:
	            content = f.read()
	    except Exception as e:
	        print("파일 읽기 예외", e)
	    else:
	        print(content)
	
	# 존재하지 않는 파일명도 있음
	filenames = ['sample.xml', 'xxxx.xxx', 'temp.json']
	for filename in filenames:
	    count_words(filename)
```
### 파이썬 엑셀
```
	# csv : common string value
	# csv -> excel에서 파일을 읽을 수 있기 때문에
	
	import csv
	'''
	# 1. 리스트의 데이타를 csv파일로 저장하기
	data = [[1,'김','과장'],[2,'박','선임'],[3,'주','연구원1']] # 임시 데이타
	with open('./data/imsi.csv','at',encoding='utf-8') as f:
	    cout = csv.writer(f) # 파일 쓰기 객체 생성?
	    cout.writerows(data) # csv 파일 쓰기
	'''
	# 2. csv파일에서 읽어서 리스트에 저장
	result = []
	with open('./data/imsi.csv','rt',encoding='utf-8') as file:
	    cin = csv.reader(file)
	    result = [row for row in cin if row] # 쓰레기값 처리????
	print(result)
```
### 파이썬 json
```
	# 파이썬 json
	import json
	
	f = open('./data/temp.json','r',encoding='utf-8')
	data = f.read()
	print(data)
	print(type(data))
	print('-'*50)
	
	result = json.loads(data) # 문자열로 되어 있는 data 를 json으로 변환
	print(result)
	for key,item in result.items():
	    print(key,item)
	    print(item['No'])
	    print(item['Job'])
	
	f.close()
```
### 파이썬 json
```
	with open('./data/sample.json','r',encoding='utf-8') as jsonf:
	    file = jsonf.read()
	    jsonresult = json.loads(file)
	    print(jsonresult)
	
	appletotal = 0;
	mongototal = 0;
	strawtotal = 0;
	gwajatotal = 0;
	coffeetotal = 0;
	for key,item in jsonresult.items():
	    print(key)
	    print(item)
	    if key == '사과':
	        appletotal += item['price']*item['count']
	    if key == '망고':
	        mongototal += item['price']*item['count']
	    if key == '딸기':
	        strawtotal += item['price'] * item['count']
	    if key == '과자':
	        gwajatotal += item['price'] * item['count']
	    if key == '커피':
	        coffeetotal += item['price']*item['count']
	print('사과 총합   ',appletotal)
	print('망고 총합   ',mongototal)
	print('딸기 총합   ',strawtotal)
	print('과자 총합   ',gwajatotal)
	print('커피 총합   ',coffeetotal)
```
### 파이썬 경로
```
	- import pathlib 만 선언하면
        Path클래스 사용시 pathlib.Path라고 명시해야 한다. 
	"""
	from pathlib import Path
	
	# (1) 해당 경로와 하위 목록들 확인
	#p = Path('C:\Windows')
	p = Path('C:\Windows')
	print(p)
	print(p.resolve()) # resolve() 절대경로로 만들어준다
	
	childDirs = [] # 리스트 생성
	for x in p.iterdir(): # iterator 요소만 추출
	    print(x)
	    if x.is_dir(): # 폴더만
	        childDirs.append(x)
	print(childDirs)
	print('-'*100)
	
	childDirs = [x for x in p.iterdir() if x.is_dir()]
	print(childDirs)
	print('-'*100)
	
	#p = Path('..')
	p = Path('.')
	print(p.resolve())
	j = list(p.glob('../a_datatype_class/*.py'))
	print(j)
```
### 파이썬 존재하지 않는 경로
```
	"""
	# Path는 파일 시스템에 접근하기 때문에, 기본적으로 운영체제 상에 조작 대상 파일 경로가 존재해야 합니다.
	# PurePath는 순수 경로의 기반 클래스입니다.
	# 파일 시스템에 접근하지 않기 때문에, 운영체제 상에 존재하지 않는 파일 경로를 다룰 수도 있습니다.
	"""
	
	#-------------------------------------------------------------------
	# 1 - 존재하지 않는 경로
	from  pathlib import PurePath
	
	j = PurePath('babo/myclass/myjob')
	print(j)
	print(j.parts) # 경로 쪼개기
	print("-"*100)
	
	j = PurePath('e:/babo/myclass/myjob')
	print(j)
	print(j.parts)
	print("-"*100)
	
	j = PurePath('\\192.168.0.12\Share\ICT')
	print(j)
	print(j.parts)
	print("-"*100)
	#-------------------------------------------------------------------
	# 2. 실제 경로로 아닌 가짜 경로를 관리하는 PurePath를 어디에 사용할까?
	# 아마도 경로나 파일명만 조작할 때 사용하지 않을까?
	# 해당 경로나 파일명이 현재 컴퓨터가 아니기에 이름만 관리하는 작업이 필요할 듯 싶다
	j1 = PurePath('C:\Windows\System32\drivers\etc\hosts')
	print(j1.parts)
	print(j1.parts[0])
	print(j1.parts[3])
	print("-"*100)
	
	print(j1.parents[0])
	print(j1.parents[1])
	print(j1.parents[2])
```
### 파이썬 경로상태, 경로(파일) 생성시간, 디렉토리 생성, 파일 생성, 경로제거, 폴더제거
```
	from  pathlib import Path

	# ------------------------------------------------
	# 1. 경로의 상태보기
	print(Path.cwd()) # 현재 작업 경로
	print(Path.home()) # 홈 디렉토리
	
	# ----------------------------------------------------
	# 2. 경로(파일) 생성시간 알아보기
	p1 = Path('Ex03_createPath.py')
	print(p1.stat()) # Ex03_createPath.py 파일의 상태 값
	ctime = p1.stat().st_ctime # Ex03_createPath.py 파일의 상태 값 중 생성 시간
	print(ctime) # 생성 시간이 숫자로만 나오는데
	
	from datetime import datetime # datetime 추출
	result = datetime.fromtimestamp(ctime) # 위의 ctime 을 날짜 와 시간으로 보기
	print(result) # 날짜와 시간으로 나옴
	
	# ------------------------------------------------
	# 3. 디렉토리 생성
	p1 = Path('imsi')
	p1.mkdir(exist_ok=True) # 폴더를 만드는데 존재하면 생성 안함
	
	p2 = Path('imsi2/test/temp')
	p2.mkdir(parents=True, exist_ok=True) # 폴더를 만드는데 한번에 부모와 자식들까지 생성 가능, 존재하면 생성 안함
	
	# ------------------------------------------------
	# 4. 파일 생성
	with open('imsi/1.txt','w',encoding='utf-8') as f:
	    f.write('홍길동') # 홍길동이라는 내용이 들어간 1.txt 파일 생성
	
	p = Path('imsi/2.txt')
	with open(p,'w',encoding='utf-8') as f2:
	    f2.write('홍길동2') # 홍길동2이라는 내용이 들어간 2.txt 파일 생성
	
	p3 = Path('imsi/3.txt')
	p3.write_text('홍길동3',encoding='utf-8') # 위의 내용을 간편하게 쓸 수 있음
	
	# ------------------------------------------------
	#  5. 경로 제거
	p4 = Path('imsi/3.txt')
	p4.unlink() # 파일 삭제
	
	p5 = Path('imsi')
	p5.rmdir() # 비어있는 폴더만 지울 수 있음

	import shutil
	shutil.rmtree('imsi2') # 하위 폴더까지
```
### 파이썬 경로이동
```
	경로 이동은  Path 모듈로 안되어 os 모듈이 필요하다
	"""
	
	from pathlib import Path
	import os
	
	print(Path.cwd())
	#os.chdir('../../..') # 부모디렉토리의 부모디렉토리까지 올라가기
	print(Path.cwd())
	
	print(os.environ['JAVA_HOME']) # 환경변수 값 추출
	print(os.environ['TOMCAT_HOME']) # 환경변수 값 추출
	
	import shutil
	#shutil.copytree('imsi','../copytemp') # imsi 폴더를
	shutil.copy('Ex00.txt', Path('../copytemp')) # Ex00.txt 파일을 위에 복사한 copytemp 폴더에 복사
```
### 파이썬 DB 연동 - MYSQL
1. file - setting - project:abasic - Python Interpreter - 검색 pym - pymysql 클릭 - install Package
```
	DB 검색

		'''
		    파이썬에서 mysql(mariadb) 연동시 필요한 패키지
			mysqlclient
			pymysql
		'''
		
		import pymysql
		
		conn = pymysql.connect(host='127.0.0.1',
				       port=3306,
				       user='scott',
				       password='tiger',
				       db='basic',
				       charset='utf8') # DB 연결
		print('연결성공') # 연결 성공 판단
		
		cursor = conn.cursor() # 커서를 얻어온다?
		sql = "SELECT * FROM emp" # 쿼리문
		cursor.execute(sql) # 쿼리문 보내기 pstmt?
		rows = cursor.fetchall() # 전체를 가져오기? Resultset
		
		print(cursor.rowcount) # 로우 개수
		print(cursor.rownumber)
		
		# 가져온 디비 값을 파일로 생성
		import csv
		output_file = 'files/emp_write.csv'
		with open(output_file,'w',encoding='utf-8') as f:
		    cout = csv.writer(f)
		
		    resultlist = list(row for row in rows if row) # 가져온 DB 값 출력
		    for i in resultlist:
			#print(row)
			cout.writerow(i)
		
		conn.close() # 연결 닫기
	DB 등록
		'''
		    파이썬에서 mysql(mariadb) 연동시 필요한 패키지
		        mysqlclient
		        pymysql
		'''
		
		import pymysql
		
		conn = pymysql.connect(host='127.0.0.1',
		                       port=3306,
		                       user='scott',
		                       password='tiger',
		                       db='basic',
		                       charset='utf8') # DB 연결
		print('연결성공') # 연결 성공 판단
		
		cursor = conn.cursor()
		
		sql = ("INSERT INTO emp(empno,ename,job,hiredate,sal,comm,deptno)"
		       "VALUES(9811,'KIM','IT',now(),10000,2000,10)")
		
		cursor.execute(sql)
		conn.commit()
		conn.close() # 연결 닫기
	DB 등록 파일 내용 읽어서
		import pymysql
		from pathlib import Path
		conn = pymysql.connect(host='127.0.0.1',
		                       port=3306,
		                       user='scott',
		                       password='tiger',
		                       db='basic',
		                       charset='utf8') # DB 연결
		print('연결성공') # 연결 성공 판단
		
		from datetime import datetime
		import csv
		with open('files/emp.csv','r',encoding='utf-8') as empF:
		    cout = csv.reader(empF)
		    for i, e in enumerate(cout):
		        print(i,e)
		        hiredate = e[4]
		        cursor = conn.cursor()
		        sql = "INSERT INTO emp(empno,ename,job,mgr,hiredate,sal,comm,deptno) VALUES(" + e[0] +",'" + e[1] + "','" + e[2] +"',"+e[3]+",'"+hiredate+"',"+e[5]+","+e[6]+","+e[7]+")"
		        cursor.execute(sql)
		        conn.commit()
```
### 파이썬 DB 연동 - ORACLE
전자지갑 - file - setting - project:abasic - Python Interpreter - 검색 cx_oracle - cx_oracle 클릭 - install Package
```
	전자지갑으로 연동
		'''
		    파이썬에서 mysql(mariadb) 연동시 필요한 패키지
		        mysqlclient
		        pymysql
		'''
		
		import cx_Oracle
		
		cx_Oracle.init_oracle_client(lib_dir=r"C:\downloads\db\oracle\instantclient-basic-windows.x64-21.14.0.0.0dbru\instantclient_21_14") # 오라클 전자지갑
		connection = cx_Oracle.connect(user='ADMIN', password='Ict0397989901', dsn='orcl_high') # 오라클 연결
		cursor = connection.cursor()
		print(cursor)
		cursor.execute("SELECT * FROM emp")       # DB 명령 실행 (cursor가 임시 보관)
		out_data = cursor.fetchall()   # cursor가 임시 보관한 내용을 out_data에 저장 (결과는 리스트)
		# out_data 내용 출력해보기
		for i,record in enumerate(out_data):
			print(out_data[i])
```
### 파이썬 DB 연동 - ORACLE
전자지갑 - file - setting - project:abasic - Python Interpreter - 검색 cx_oracle - cx_oracle 클릭 - install Package
```
	전자지갑으로 연동
		'''
		    파이썬에서 mysql(mariadb) 연동시 필요한 패키지
		        mysqlclient
		        pymysql
		'''
		import oracledb

		oracledb.init_oracle_client(lib_dir=r"C:\Users\ict03_029\Oracle\instantclient_11_2")
		con = oracledb.connect(user="scott"
		                       ,password='tiger'
		                       ,dsn="localhost:1521/XE")
		cursor = con.cursor()
		print("연동 성공", cursor)
		# cursor.execute("SELECT * FROM dept")
		# out_data = cursor.fetchall()
		cursor.execute("select * from dept")
		datas = cursor.fetchall()

		print("ok", datas)

		for data in datas:
		    print(data[0])
```
### 파이썬 웹 요청 라이브러리
```
	파이썬에서 웹을 요청할 수 있는 라이브러리
	        1- requests 라이브러리 (s붙음 주의) - 추가
	        2- urllib 라이브러리 - 내장모듈 (request)
	
	    차이점
	        1- requests는 요청 메소드(get/post)를 구분하지만 urllib는 보내는 데이타 여부에 따라 구분됨
	        2- 데이타 보낼 때 requests는 딕셔러니 형태로 urllib는 인코딩한 바이너리 형태로 보낸다
	        
	    requests 라이브러리 추가
	    메뉴 > File > Settings > Project Interpreter > + 버튼 > 'requests' 검색 후 인스톨
	
	[ requests 모듈 ]
	(1) Rest API 지원
	    import requests
	    resp = requests.get('http://www.mywebsite.com/user')
	    resp = requests.post('http://www.mywebsite.com/user')
	    resp = requests.put('http://www.mywebsite.com/user/put')
	    resp = requests.delete('http://www.mywebsite.com/user/delete')
	
	(2) 파라미터가 딕셔너리 인수로 가능
	    data = {'firstname':'John', 'lastname':'Kim', 'job':'baksu'}
	    resp = requests.post('http://www.mywebsite.com/user', data=userdata)
	
	(3) json 디코더 내장 (따로 json 모듈 사용 안해도 됨)
	    resp.json()
```
### 파이썬 requests 외장모듈
```
	import requests

	url = 'http://www.google.com' # 구글 주소
	res = requests.get(url) # 구글에 get 방식으로 요청
	print(res) # <Response [200]>
	print("*"*1000)
	
	print(res.text) # 문자열로 받음
	print("*"*1000)
	
	print(res.content) # byte 객체로 받음
	print("*"*1000)
	
	print(res.headers) # dictionary 구조로 받음
	print("*"*1000)
	for k,v in res.headers.items():
	    print(k,">>",v)
```
### 파이썬 request 내장모듈
```
	# 내장모듈 (주의, s가 없는 request)

	from  urllib import request
	
	url = 'http://www.google.com' # 구글 주소
	
	site = request.urlopen(url)
	page = site.read()
	print(page)
	print("*"*1000)
	
	print(site.status)
	print("*"*1000)
	
	for h in site.getheaders():
	    print(h)
```
### 파이썬 request 이미지 퍼오기
```
	# urlretrieve(): 파일로 바로 저장
	# urlopen(): 파일로 바로 저장하기 않고 메모리에 로딩을 한다.
	
	""" [참고] 파일저장 기본방식
	    f = open('a.txt','w')
	    f.write("테스트 내용")
	    f.close()
	
	    위의 과정을 with 문으로 간략하게 close 필요없음
	    with open("a.txt","w") as f:
	        f.write("테스트 내용")
	"""
	
	from  urllib import request
	
	url = "https://www.google.com/images/branding/googlelogo/1x/googlelogo_light_color_272x92dp.png" # google 이미지
	imgName = "data/daum.png" # 파일로 저장할 장소
	
	site = request.urlopen(url) # url 요청
	page = site.read() # 요청 url page로 담기
	
	with open(imgName,"wb") as f: # wb: 쓰기 바이너리 값
	    f.write(page)
```
### 파이썬 이미지 쉽게 퍼오기
```
	# 크롬에서 구글이미지 > 오른마우스 > 이미지 주소 복사 >
	# 구글 이미지 : https://www.google.com/images/branding/googlelogo/2x/googlelogo_color_272x92dp.png
	# 다음 이미지 : https://t1.daumcdn.net/daumtop_chanel/op/20170315064553027.png
	
	"""
	    urllib 라이브러리(패키지):
	        - URL를 다루는 모듈을 모아 놓은 패키지
	        - Http나 Ftp를 사용하여 데이터를 다운로드 할 때 사용하는 라이브러리
	
	        [예] request 모듈 : 웹 요청을 보내고 받는 기능을 하는 모듈
	                - urlretrieve() 함수를 이용하여 이미지를 다운로드 받아 파일로 저장한다.
	"""
	
	from  urllib import request
	
	url = "https://www.google.com/images/branding/googlelogo/1x/googlelogo_light_color_272x92dp.png" # google 이미지
	imgName = "data/daum22.png" # 파일로 저장할 장소
	
	request.urlretrieve(url,imgName) # 이미지를 쉽게 퍼오기
```
### 파이썬 url 웹 경로
```
	"""
	 urllib.parse.urljoin() : 상대경로를 절대경로로 변화하는 함수
	"""
	
	baseUrl = 'http://www.example.com/html/a.html'
	
	from  urllib import  parse
	print(parse.urljoin(baseUrl, "b.html")) # http://www.example.com/html/b.html
	print(parse.urljoin(baseUrl, "../b.html")) # http://www.example.com/b.html
	print(parse.urljoin(baseUrl, "sub/b.html")) # http://www.example.com/html/sub/b.html
	print(parse.urljoin(baseUrl, "/sub/b.html")) # http://www.example.com/sub/b.html
	print(parse.urljoin(baseUrl, "/")) # http://www.example.com/
	print(parse.urljoin(baseUrl, "/temp/test.html")) # http://www.example.com/temp/test.html
	print(parse.urljoin(baseUrl, "../temp/test.html")) # http://www.example.com/temp/test.html
```
### 파이썬 API
```
	"""
	전세계날씨제공 API : http://openweathermap.org
	
	    1. 회원가입 : 메뉴 > Sign Up > 사용용도 : Education > 대충가입 (무료는 1번에 60번 호출 가능 )
	    2. 개발자모드 : Sign In > API Keys 에서 내가 발급받은 키 (추가 키 가능)
	    3. 발급받고 바로 지정 안됨 (시간소요)
	"""
	
	import requests
	import json
	
	# API 키를 지정합니다. 자신의 키로 변경해서 사용해주세요.
	apikey = "1db47184ebbc18af53fd996be840d270"
	
	# 날씨를 확인할 도시 지정하기
	cities = ["Seoul,KR", "Tokyo,JP", "New York,US"]
	
	# url 지정
	api = "http://api.openweathermap.org/data/2.5/weather?q={city}&APPID={key}"
	
	# 켈빈 온도를 섭씨 온도로 변환하는 함수
	k2c = lambda k: k - 273.15
	
	#def k2c(k):
	#   return k-273.15
	
	for cname in cities:
	    url = api.format(city=cname,key=apikey)
	    res = requests.get(url) # url 요청
	    #print(res.text) # 문자열
	    data = json.loads(res.text) # 문자열 -> json(=dict)
	
	    print(data) # {'coord': {'lon': 139.6917, 'lat': 35.6895}, 'weather': [{'id': 803, 'main': 'Clouds', 'description': 'broken clouds', 'icon': '04d'}], 'base': 'stations', 'main': {'temp': 295.07, 'feels_like': 295.09, 'temp_min': 292.94, 'temp_max': 296.81, 'pressure': 1005, 'humidity': 68}, 'visibility': 10000, 'wind': {'speed': 2.57, 'deg': 40}, 'clouds': {'all': 75}, 'dt': 1717380261, 'sys': {'type': 2, 'id': 2001249, 'country': 'JP', 'sunrise': 1717356378, 'sunset': 1717408367}, 'timezone': 32400, 'id': 1850144, 'name': 'Tokyo', 'cod': 200}
	    print("도시:",data['name'])
	    print("날씨상태:", data["weather"][0]["description"]) # 리스트 안에 set 구조로 되어있는 description 추출
	    print("최고기온:", round(k2c(data["main"]["temp_max"])))
	    print("최저기온:", round(k2c(data["main"]["temp_min"])))
	    print("습도:", data["main"]["humidity"])
	    print("기압:", data["main"]["pressure"])
	    print("풍속:", data["wind"]["speed"])
```
### 파이썬 beautifulsoup
```
	웹서버에 접속하고, 데이터를 요청하며 서버로부터 받는 데이터를 분석해서 정보를 제공할 수 있도록
	파이썬의 표준 라이브러리를 사용해도 되지만
	유용한 외부 라이브러리가 있다.
	
	* requests : 웹요청을 보내고 받는 기능
	* beautifulsoup4 : 서버로부터 받은 데이터를 분석하는데 사용
	            - 스크래이핑 할 수 있는 라이브러리
	            - 다운로드 기능은 없음 ( 다운로드는 urllib를 이용함 )
	            - 추가 설치 필요
	
	(1) 외부 라이브러리 설치
	    * pip : PyPI(Python Package Index : 파이썬 패키지 인덱스)를 관리하는 시스템
	    ( pip 명령어 인식 : C:\ProgramData\Anaconda3\Scripts 환경변수 PATH에 지정되어 있어야 함 )
	
	    > pip install requests  (* 주의 : s 붙음 )
	    > pip install beautifulsoup4
	
	(2) 파이참에서 설치
	    프로젝트 선택 후 메뉴 > File > Settings
	    왼쪽 Project > Project Interpreter 오른쪽 + 버튼
	    검색창에서 requests를 찾아서 install package
	    request에 s가 붙어야 한다.
	
	    bs4도 추가하려면 BeautifulBS4를 찾아서 패키지 인스톨 해야 한다.

```
### 파이썬 웹 요소 추
```
	"""
	    bs4 라이브러리 : 웹에서 가져온 HTML코드를 파이썬에서 사용하기 편하게 파싱해주는 라이브러리
	            [참고] 웹에서 가져온 HTML코드 가져오는 방법
	                - requests 모듈
	                - urllib 의 request 모듈
	
	    BeautifulSoup 모듈
	        - find()
	        - find_all()
	    
	    [참고] 파서의 종류 
	        - lxml : c로 만들어져 속도 빠름
	        - html5lib : 파이썬으로 만들어서 lxml보다 느림
	        - html.parser (*): 파이썬 버전을 확인해서 사용
	"""
	
	from bs4 import BeautifulSoup
	
	html = """
	    <html><body>
	        <h1>스크레이핑 연습</h1>
	        <p>웹페이지 분석하자</p>
	        <p>데이타 정제하기</p>
	    </body></html>
	"""
	
	# 1. 데이타 파서하기
	soup = BeautifulSoup(html,"html.parser")
	
	# 2. 원하는 요소 접근하기
	h1 = soup.html.body.h1 # body 안 h1태그
	print(h1.text)
	
	# 3. 요소의 내용 추출하기
	p = soup.findAll("p") # 모든 p 태그
	print(p)
	
	for i in p:
	    print(i.text)
```
### 파이썬 웹 속성 값 추출
```
	from bs4 import BeautifulSoup

	html = """
	    <html>
	        <body>
	            <ul>
	                <li><a href='http://www.naver.com'>네이브</a></li>
	                <li><a href='http://www.daum.net'>다아음</a></li>
	            </ul>
	        </body>
	    </html>
	"""
	
	''' 리스트(li)목록의 내용과 해당 경로를 추출하기
	    속성추출 : attrs['속성명']
	
	    [출력결과]
	    네이브 : http://www.naver.com
	    다아음 : http://www.daum.net
	'''
	
	soup = BeautifulSoup(html,"html.parser") # html 파씽
	
	a = soup.select("a") # a 태그 추출
	
	for i in a:
	    print(i.get("href")) # a 태그의 속성 href 값
	    print(i.attrs["href"]) # a 태그의 속성 href 값
```
### 파이썬 셀레니움 (웹 컨트롤롤)
```
	1. selenium
	    - 주로 웹앱을 테스트하는데 이용하는 프레임워크
	    - 웹 브라우저를 원격으로 조작할 때 사용
	    - 자동으로 URL을 열고 클릭, 스크롤, 문자 입력등의 동작을 조작할 수 있다.
	    - webdriver라는 API를 통해 운영체제에 설치된 Chrome등의 브라우저를 제어하게 된다.
	
	    [설치]  메뉴 > File > Settings > Project Interpreter > + 버튼
	     selenium 검색 후 인스톨
	        > pip install selenium
	
	    [참고] Selenium의 버전은 자주 업데이트 되고, 브라우저의 업데이트 마다 새로운 Driver를 잡아주기 때문에
	        항상 최신버전을 깔아 주는 것이 좋다.
	
	    [매뉴얼]
	    ` https://selenium-python.readthedocs.io/index.html
	    ` https://docs.seleniumhq.org/docs/
	
	
	2. 크롬 웹드라이버 ( Chrome WebDriver )
	
	    [다운로드] http://chromedriver.chromium.org/downloads
	        chromedirver_win32.zip 파일 다운로드 받고 압축풀기

	* Selenium은 driver객체를 통해 여러가지 메소드를 제공한다.
	  - HTML을 브라우저에서 파싱해주기 때문에 굳이 Python와 BeautifulSoup을 사용하지 않아도 된다.
	
	
	[ URL에 접근하는 api ]
	
	get(‘http://url.com’)
	
	1. DOM 내부에 있는 여러 요소 중 첫 번째 요소(element) 찾는다.
		find_element_by_name(‘HTML_name’)
		find_element_by_id(‘HTML_id’)
		find_element_by_css_selector(‘#css > div.selector’)
		find_element_by_class_name(‘some_class_name’)
		find_element_by_tag_name(‘h1’)
		find_element_by_xpath(‘/html/body/some/xpath’) : xpath 지정하여 해당 요소 추출
		find_element_by_link_text(‘text’) : 링크 텍스트로 요소 추출
	-------------------------------------------------
	[4버전]
		find_element(By.ID, 'HTML_id')
		find_element(By.NAME, 'HTML_name')
	
	2. DOM에서 모든 요소 추출
		find_elemens_by_css_selector(‘#css > div.selector’)
		find_elements_by_class_name(‘some_class_name’)
		find_elements_by_tag_name(‘h1’)
		
		3. DOM 요소에 적용할 수 있는 메소드와 속성
		clear()             : 글자를 지움
		click()             : 클릭
		get_attribute(name) : 요소의 속성 name에 해당하는 값을 추출
		is_displayed()      : 요소가 화면에 출력되는지 확인
		is_enabled()
		is_selected()
		execute_script()
		save_screenshot(filename)
		submit()
		
		외에도 많은 속성과 메소드가 있습니다.
		
		또한 각 브라우저 드라이버 객체의 속성도 있습니다.

	터미널
		pip install --upgrade selenium
		pip install webdriver_manager
	웹 컨트롤
		from selenium import webdriver
		from selenium import webdriver
		from selenium.webdriver.common.by import By
		from selenium.webdriver.chrome.options import Options
		from selenium.webdriver.chrome.service import Service
		from webdriver_manager.chrome import ChromeDriverManager
		import time
		
		# 0. 네이버 로그인 정보
		myID = '정민기'
		myPW = '5176'
		
		# 1. webdriver 객체생성
		options = Options()
		# 옵션에 추가
		# [예] 브라우저 꺼짐 방지
		options.add_experimental_option("detach",True)
		service = Service(ChromeDriverManager().install()) # 크롬드라이버 매니저 설치
		driver = webdriver.Chrome(options=options)
		
		# 2. 페이지 접근
		driver.get("http://ictedu.atosoft.net/worknet/SLogin.asp")
```
### 파이썬 폴리움 (지도)
```
	설치
		folium
	import folium

	# map_osm = folium.Map(location=[37.572807, 126.975918])
	# map_osm.save("./map/map1.html")
	
	# [2] 지도 줌 설정 (16~19)
	# map_osm = folium.Map(location=[37.572807, 126.975918],zoom_start=17)
	# map_osm.save("./map/map1.html")
	
	# [3] 지도 모양 설정
	# map_osm = folium.Map(location=[37.572807, 126.975918],
	#                      zoom_start=17,
	#                      tiles="Stamen Terrain") # Stamen Toner, Mapbox Bright, Mapbox Control room tiles
	# map_osm.save("./map/map1.html")
	
	# [4] Marker
	map_osm = folium.Map(location=[37.572807, 126.975918],
	                     zoom_start=17)
	folium.Marker(location=[37.572807, 126.975918],
	              popup="세종문화회관",
	              icon=folium.Icon(color="red",icon="info-sign")
	              ).add_to(map_osm)
	print(type(37.576099))
	folium.CircleMarker(location=[37.576099, 126.976881],
	                    popup="광화문",
	                    radius=100,
	                    color="red",
	                    fill_color="yellow"
	                    ).add_to(map_osm)
	#folium.TileLayer(tiles="Stamen Toner").add_to(map_osm)
	map_osm.save("./map/map2.html")
```
### 파이썬 주피터노트북 넘파이
```
	주피터 속성 - "워크스페이스경로"
	# 넘파이
		import numpy as np
		nplist = np.array([1,2,3])
		print(nplist*2)
		print(nplist*0)
		print(nplist*0.01)

		# (2) 행렬의 곱
			A = np.array(
			    [[1, 2, 3],
			    [4, 5, 6]])
			B = np.array(
			    [[7,8],
			     [9,10],
			     [11, 12]])
			np.dot(A,B)
		# (3) 전치행렬
			# - 원 행렬에서 행과 열 위치를 교환한 원소로 구성한 행렬
			A = np.array(
			    [[1, 2, 3],
			    [4, 5, 6]])
			np.transpose(A)
		# 평균
			np.mean(ar)
		# 총합
			np.sum(ar)
		# 큰값
			np.max(ar)
		# 각 원소의 누적곱
			np.cumprod(ar)
		# 총합
			np.sum(arr)
		#  특정 행의 합
			np.sum(arr[1])
		# axis=0 : 행방향 - 열단위 합
			np.sum(arr,axis=0)
		# axis=1 : 열방향 - 행단위 합
			np.sum(arr,axis=1)
		# 불린 배열에서의 배열
			arr2 = np.array([[12, 7, 22], [20,33, 44], [4,5,6]])
			arr2[arr2>20]
		# unique 연산자를 이용하여 중복제거
			region = np.array(['가산','서울','서울','판교','가산','일산','일산'])
			np.unique(region)
		# 정렬 (원본 X)
			arr = np.array([9,3,6,1,7,2,4,8,5,6])
			np.sort(arr)
			np.sort(arr)[::-1]		
```
### 파이썬 주피터노트북 판다스
```
	Series
		DataFrame의 한 컬럼 데이터 세트
		Series 역시 DataFrame의 인덱스와 동일한 인덱스를 가진다
		즉 Series는 컬럼이 하나인 데이타 구조체이고, DataFrame은 컬럼이 여러개인 데이타 구조체이다
		DataFrame을 RDBMS의 테이블과 유사하다면, Series는 테이블의 한 컬럼과 유사다하고 볼 수 있다

		# from pandas import Series
		# age_in = Series([22,33,44,25,28])		
		import pandas as pd
		age_in = pd.Series([22,33,44,25,28])
	age_in.index
		RangeIndex(start=0, stop=5, step=1)
	age_in.values
		array([22, 33, 44, 25, 28], dtype=int64)
	Series 인덱스
		리스트, 튜플의 index와 dict 의 key 와 유사
		같은 값의 index 가 가능 ( 즉, 중복 가능 )
	인덱스 지정하며 시리즈 생성
		age_in = pd.Series([22,33,44,25,28], index=['가','나','다','라','마'])
		age_in["다"] = 100
	# Series 인덱스 중복 확인
		srs = pd.Series(["가","나","다"], index=["a","b","b"])
		print(srs["b"]) # 나, 다
	# 딕셔러리를 시리즈 형태로 변환
		info_list = { 'kim': 25, 'park':22, 'lee':34 }
		info_series = pd.Series({ 'kim': 25, 'park':22, 'lee':34 })
	# 그래프
		import pandas as pd
		odd = [1,2,3,4,5]
		sodd = pd.Series(odd)
		sodd.plot()
	DataFrame
		# csv 파일로 저장하기
			import pandas as pd
			
			mysource = {
			    '시도':['서울','경기','인천','부산','대전'],
			    '구분':['특별시','도','광역시','광역시','광역시'],
			    '인구':['999만','1300만','400만','600만','300만'],
			    '면적':[600.9, 10171, 1234.5, 747.8, 459.1]
			}
			df = pd.DataFrame(mysource)
			df.to_csv("result/temp.csv")
		# 컬럼명을 인덱스로 지정
			df2 = pd.read_csv("result/temp.csv",index_col="Unnamed: 0")
			df2
		# csv 파일 가공
			df3 = pd.read_csv("result/temp.csv", # 파일 위치
			                  names=["번호","시도","구분","인구","면적"], # 컬럼명 지정
			                  index_col="번호", # 인덱스 컬럼명
			                  skiprows=[0],  # 첫번째 행 스킵
			                  nrows=3) # 3번 째 행까지만 출력
			df3
		# 엑셀 파일 가공
			df4 = pd.read_excel("data/인구주택총조사2015.xlsx",
			                   nrows=10,
			                   usecols="C:J")
			df4
		# 텍스트파일(data/TextData.txt) 읽어오기
		# 미리 엑셀파일에서 5줄 복사해서 메모장에 넣고 (탭구분상태)로 저장한다.
			df5 = pd.read_csv("data/TextData.txt",encoding="cp949",sep="\t")
			df5
		# json 파일 읽기
			import json
			df9 = json.load(open("data/JsonData.json"))
			print(df9)
			print(df9["kind1"])
			print(df9["region"])
			print(df9["food_name"])
			print(df9["food_name"]["one-of-best"])
		열(컬럼) 추출
			df.컬럼명
			df['컬럼명']
		행 추출
			df.loc[] : 인덱스 지정하지 않으면 인덱스(순서), 인덱스 지정하면 인덱스로 추출
			df.iloc[] : 인덱스(순서)로 추출
		행과 열에서 추출
			df.loc[2, 3] : 2 행의 3열 데이타
			df.loc[1:3, 2:4] : 1부터 3행전까지의 행에서 2부터 4전까지의 열의 데이타

		import pandas as pd
		# 데이타 프레임 자료 생성
		mydata = {
			  'name':['홍길동','박길동','김길동'], 
			  'age':[22,33,44], 
			  'dept':['컴공','국어','산업']
			 }
		df = pd.DataFrame(mydata)
		df.head(10)
			앞에 10개 행 보기
		# 판매건수에서 작은 값 순으로 10개
			df.nsmallest(10,"판매건수")
		# 판매건수에서 작은 값 순으로 10개 중 가격 순
			df.nsmallest(10,["판매건수","가격"])
		# 판매건수에서 큰 값 순으로 10개
			df.nlargest(10,"판매건수")
		# 앞에 행 10개
			df.head(10)
		# 가격순으로 정렬하되 판매건수와 가격만 추출
			temp = df[["판매건수","가격"]]
			temp.sort_values("가격",ascending=False)
		# 가격순으로 정렬하되 판매건수와 가격만 추출
			temp = df[["판매건수","가격"]]
			print(temp)
		# 가격순으로 정렬하되 판매건수와 가격만 추출하여 내림차순 10개
			print(temp.sort_values("가격",ascending=False)[:10]["가격"])
		# 그래프로 변환
			temp.sort_values("가격",ascending=False)[:10]["가격"].plot(kind="bar")
		통계함수
			count()
			sum()
			mean()
			std()
			var()
			min()
			max()
			cumsum()
			cumprod()
			describe() : 요약통계량
		# df["가격"] 에서 10000원 20000원 사이 상품
			condi = (df["가격"] > 10000) & (df["가격"] < 20000)
			df[condi]
		# 결측치 False True 로 나오게
			print(df.isnull())
		# 결측치 개수
			print(df.isnull().count)
		# 1컬럼 결측치 Unknown, 2컬럼 결측치 -100
			df.fillna({1:"Unknown",2:-100})
		# 임신횟수(pregnant)당 당뇨병 발생(diabetes) 확률을 구한다
			temp = df[["pregnant","diabetes"]]
			temp
		# 그룹별 수
			temp2 = temp.groupby("pregnant").count()
			print(temp2)
			print("*"*100)
			
		# 그룹별 합
			temp3 = temp.groupby("pregnant").sum()
			print(temp3)
			print("*"*100)
			
		# 그룹별 평균
			temp4 = temp.groupby("pregnant").mean() 
			print(temp4)
			print("*"*100)
		# 한글처리 그래프
			from matplotlib import rc
			rc('font', family='Malgun Gothic')
		# (3) W로 시작하는 artist_name 추출
			condi = df["artist_name"].str.startswith("W")
			df[condi]
		# (4) album_name에 'LOVE'이라는 단어가 들어있는 데이타 추출
			condi = df["album_name"].str.contains("LOVE")
			df[condi]
	컬럼추가
		df["gender"] = ["여자","여자","남자"]
	# 행 추가
		df.loc[3] = ["맹길동",55,"기계","남자"]
	# 인덱스순서를 변경하려면 -> 인덱스는 우선 DataFrame이 있는 상태에서 변경해야 한다
		df4 = df.reindex(index=[1,9,2,0,3])
	# 총 데이터 건수와 데이타 타입등 정보 확인
		df.info()
	# 기본통계량 구하기 ( 총개수, 평균, 표준편차, 최소값, 4분위수 등)
		df.describe()
	csv 파일 데이타 분석
		import pandas as pd
		data = pd.read_csv("data/president_heights.csv")
		print(type(data))
		print(data.head())
		print(data.tail(12))
	막대그래프
		pp.plot(kind="bar")
	원형그래프
		pp.plot(kind="pie")
	시각화
		import seaborn
		anscombe = seaborn.load_dataset('anscombe')
		anscombe
	추출
		dataset_1 = anscombe[ anscombe['dataset']=='I']
		dataset_2 = anscombe[ anscombe['dataset']=='II']
		dataset_3 = anscombe[ anscombe['dataset']=='III']
		dataset_4 = anscombe[ anscombe['dataset']=='IV']
	그래프로
		import matplotlib.pyplot as plt
		# [결론] 평균, 분산 등의 수치가 같아도 그래프 형태로 확인하면 다른 데이타임을 알 수 있다
		fig = plt.figure()  #  1-전체 그래프의 기본 틀
		axes1 = fig.add_subplot(2,2,1) # 2-그래프를 넣을 그래프 격자
		axes2 = fig.add_subplot(2,2,2)
		axes3 = fig.add_subplot(2,2,3)
		axes4 = fig.add_subplot(2,2,4)
		
		axes1.plot(dataset_1['x'], dataset_1['y'], 'o') # 3-격자에 그래프 추가
		axes2.plot(dataset_2['x'], dataset_2['y'], 'o')
		axes3.plot(dataset_3['x'], dataset_3['y'], 'o')
		axes4.plot(dataset_4['x'], dataset_4['y'], 'o')
	그래프
		from pandas import Series
		s=Series([1.5, 2.3, 0.9], index=['no1','no2','no3'])
		splot = s.plot(kind="hist") # 그래프 그리기
		splot.set_xlabel("data2") # x축 제목
		splot.set_ylabel("value2") # y축 제목
		splot.set_title("Sample") # 그래프 제목

		df.plot(kind="barh",title="DATA CHART", xlabel="하하",ylabel="하하")
	""" 0. 플롯 스타일 """
		plt.style.use("classic") # 그래프 꾸미기
	""" 1. 색상지정 """
		plt.plot(np.sin(x-0), color="red") 
		plt.plot(np.sin(x-1), color="g")
		plt.plot(np.sin(x-2), color="#FF9933")
		plt.plot(np.sin(x-3), color="chartreuse")
		plt.plot(np.sin(x-4), color=(0.5,0.2,1.0))
	""" 2. 선스타일 """
		plt.plot(np.sin(x-0), color="red", linestyle="solid") 
		plt.plot(np.sin(x-1), color="g", linestyle="dotted")
		plt.plot(np.sin(x-2), color="#FF9933", linestyle="dashed")
		plt.plot(np.sin(x-3), color="chartreuse", linestyle="dashdot")
	''' 4. 범례 '''
		plt.plot(np.sin(x-0),"-g",label="first") # solid + green
		plt.plot(np.sin(x-1),"--c",label="second") # dashed + cyan
		plt.plot(np.sin(x-2),"-.k",label="third") # dashed + black
		plt.plot(np.sin(x-3),":r",label="fourth") # dotted + red
		
		plt.legend(loc=1)
	그래프 위치 지정
		plt.figure(figsize=(12,8))
	
		plt.subplot(223) # 2행 2열 세 번째
		plt.subplot(224) # 2행 2열 네 번째
		plt.subplot(211) # 2행 1열 첫 번째
		
		plt.show()

		plt.figure(figsize=(12,8))

		plt.subplot(2,3,(1,2)) # 2행 1열 첫 번째 두 번째
		plt.subplot(2,3,3) # 2행 1열 세 번째
		plt.subplot(2,1,2) # 2행 2열 전체
		
		plt.show()plt.figure(figsize=(12,8))
		
		plt.subplot(2,3,(1,2)) # 2행 1열 첫 번째 두 번째
		plt.subplot(2,3,3) # 2행 1열 세 번째
		plt.subplot(2,1,2) # 2행 2열 전체
		
		plt.show()
	그래프 영역 지정 그리기
		# 1- 그래프 틀(영역)을 만들기
		fig, ax = plt.subplots(1,2)
		
		# 2- 그래프 그리기
		ax[0].plot(np.random.randn(100))
		ax[1].plot(np.random.randn(200).cumsum())
	그래프 마커 추가
		plt.plot(step,data,linestyle="dashed",color="blue",marker="o",markersize=12,markerfacecolor="cyan")
	# 그래프 주석
		ax.annotate("My comment", xy=(6.2,1),xytext=(3,2),arrowprops=dict(facecolor="red",shrink=0.05))
	히스토그램 (수치 를 나타낼 때)
		tips["total_bill"]
		plt.hist(tips["total_bill"],bins=100,color="green")
		plt.title("전체지불금액");
		plt.xlabel("빈도수")
		plt.ylabel("지불금액")
	# 이변량 그래프 - 변수 2개를 이용한 그래프
	# 지불금액에 따른 팁 금액을 나타내는 그래프
		plt.scatter(tips["total_bill"],tips["tip"]);
	# 이산형 변수와 연속형 변수 - 박스플롯
	# 성별에 따른 팁을 나타내는 그래프
		female = tips[tips["sex"] == 'Female']["tip"] 
		male = tips[tips["sex"] == 'Male']["tip"] 
		print(female)
		print(male)
		
		plt.boxplot([female,male],labels=("여자","남자"));
		plt.title("성별에 따른 팁금액")
	# 다변량 그래프 - 3개 이상의 변수로 그래프
	# (1) 성별을 0과 1로 변환하는 함수 선언
	# 식사지불과 팁의 정도를 성별에 따라 그래프를 그린다면
		def gender(sex):
		    if sex == "Female":
		        return 0
		    else:
		        return 1
		
		# (2) 변경한 성별값의 변수(컬럼 sex_col) 추가
		tips["sex_col"] = tips["sex"].apply(gender)
		tips.head(20)
		
		# (3) 그래프 : x와 y 축, c=점의 색상, alpha=점의 투명도, s=점의 크기
		#    테이블당의 인원수를 점의 크기로 표현한다면 s=tips['size']*10 추가
		plt.scatter(x=tips["total_bill"],
		            y=tips["tip"],
		            c=tips["sex_col"],
		            s=tips["size"]*20,
		            alpha=0.5
		           )
	한글 처리
		from matplotlib import font_manager, rc
		import matplotlib.pyplot as plt
		
		plt.rcParams['axes.unicode_minus']=False  # 추가설정 : 폰트를 변경하면 -표시가 ㅁ으로 변경되기에 '-'를 변경하지 않도록 지정
		rc('font', family='Malgun Gothic')
	폰트 종류
		font_manager.fontManager.ttflist
	# csv 데이터 합치기
		df = pd.concat([df01,df02])
		df
	# 두 데이타프레임에 동일한 컬럼명이면 하나의 컬럼명으로
	# 다른 컬럼명이면 두 개의 컬럼명이 중복
		merge_data = pd.merge(site,visited,left_on="name", right_on="site")
		merge_data
	# 값들 중 NaN 이 포함 되어 있을 때
		df["좋아요"].fillna(0).mean()
	# 결측치를 그림으로 볼 수 있음
		#!pip install missingno
		import missingno as msno
		
		msno.matrix(df)
	 누락값 비교 방법 : pandas 메소드 이용
		import pandas as pd
		
		print(pd.isnull(NaN)) # isnull 로는 비교 가능
	# 누락값 개념
		from numpy import NaN, NAN, nan
		print(NaN == False) # NaN != False
		print(NaN == 0) # NaN != 0
		print(NaN == NaN) # 비교 자체가 안됨
	""" 누락값 확인 """
		ebola = pd.read_csv('./data/ebola_timeseries.csv')
		ebola	
	# 제일 먼저 데이타 확인
		ebola.shape
	# 누락값이 아닌 값의 개수 확인
		ebola.count()
	# 누락값의 수 구하기
		ebola.shape[0] - ebola.count()
	# 전체적인 누락값의 수를 얻으려면 - numpy 라이브러리의 count_nonzero() 이용
		import numpy as np
		np.count_nonzero(ebola.isnull())
	""" (1) 누락값 삭제하기 """
		ebola_dropna = ebola.dropna()
		ebola_dropna
	""" (2) 누락값 대치하기 """
		re_ebola = ebola.fillna(0) # 원래는 평균값이나 중앙값 등등 지정하기
		re_ebola
	datetime 파이썬 날짜
		""" datetime 라이브러리 : date / time / datetime 오브젝트 """
		from datetime import datetime
		
		# 현재 시간 출력
		print(datetime.now()) # 년월일시분초
		print(datetime.today())
		print("*"*100)
		
		# 시간 계산
		t1 = datetime.now()
		t2 = datetime(2023,12,25)
		print(t1 - t2)
		print("*"*100)
		
		# 형식으로 지정
		t1 = datetime.now()
		print(t1)
		print(t1.strftime("%Y-%m-%d"))
		print(t1.strftime("%y-%m-%d"))
		print("*"*100)
		
		# 시:분:초 형식으로 출력
		print(t1.strftime("%Y-%m-%d %H:%M:%S"))
		print("*"*100)
		
		# 년,월,일 추출
		print(t1.year) # 년 추출
		print(t1.month) # 월 추출
		print(t1.day) # 일 추출
		print(t2.hour) # 시 추출
		print(t1.minute) # 분 추출
		print(t1.second) # 초 추출
	# datetime 오브젝트로 변경하여 필요한 데이타 추출 및 계산
		ebola["date_dt"] = pd.to_datetime(ebola["Date"])
		
		# 파일을 읽을 때부터 datetime 변경 가능
		ebola_temp = pd.read_csv('./data/ebola_timeseries.csv',parse_dates=["Date"]) # 컬럼명# datetime 오브젝트로 변경하여 필요한 데이타 추출 및 계산
		ebola["date_dt"] = pd.to_datetime(ebola["Date"])
		
		# 파일을 읽을 때부터 datetime 변경 가능
		ebola_temp = pd.read_csv('./data/ebola_timeseries.csv',parse_dates=["Date"]) # 컬럼명
	# 년, 월, 일 추출
		ebola["Date"].str[:]
		ebola["year"] = ebola["date_dt"].dt.year # datetime형은 dt 객체를 이요해서 추출
	# 에볼라 최초 발병일 구하기
		ebola["date_dt"].min() # date_dt 중 제일 작은 날짜
		ebola["date_dt"].max() # date_dt 중 제일 큰 날짜
	# 파일 가져오기
		import pandas as pd # 판다스 임포트
		from datetime import datetime # 데이트타임 임포트
		banks = pd.read_csv('./data/banklist.csv')
		banks.head() # 자료 5개까지 보기
		
		# info 로 구조 파악
		banks.info()
		
		# datetime 으로 변경
		banks["Closing Date_dt"] = pd.to_datetime(banks["Closing Date"])
		banks["Closing_year"] = banks["Closing Date_dt"].dt.year # 년
		banks["Closing_quarter"] = banks["Closing Date_dt"].dt.quarter # 분기
		print(banks.head(10)) # 변경 후 자료 확인
		
		# 연도별 파산은행 구하기
		closing_year_group = banks.groupby("Closing_year").count()
		
		# 시각화
		import matplotlib.pyplot as plt
		plt.plot(closing_year_group) # 연도별 파산은행 그래프 그리기
```
### 파이썬 쇼핑몰 데이타 분석
```
	# 데이터를 다루는 library인 padas를 import합니다.
	import pandas as pd
	
	# 화면에 출력하는 데이터 프레임의 최대 row 수를 500으로 설정합니다.
	pd.set_option('display.max_rows', 500)
	
	# 화면에 출력하는 데이터 프레임의 최대 column 수를 500으로 설정합니다.
	pd.set_option('display.max_columns', 500)
	
	# csv 파일 읽기
	order = pd.read_csv('./data/shoppingmall/order_info.csv')
	order.head()
	
	# 테이블 생성
	table = pd.pivot_table(order,
	                       values = 'price',
	                       index = 'shop_id',
	                       aggfunc = 'sum')
	table.sort_values(( 'price'), ascending=False).head(10)
	
	# 시각화
	import seaborn as sns
	import matplotlib.pyplot as plt
	%matplotlib inline
	%config InlineBackend.figure_format = 'retina'
	
	# 테이블 생성
	table = pd.pivot_table(order,
	                       values = 'price',
	                       index = 'shop_id',
	                       aggfunc = ['sum', 'count'])
	table.columns = ['sum', 'count']
	table = table.sort_values('sum', ascending=False).head(10)
	table
	
	# head(10)를 구해서 그래프 출력
	table_top10 = table.head(10)
	sns.barplot(data=table_top10, x=table_top10.index, y='sum', order=table_top10.index)
	
	# 다른 방식으로 출력
	top10_index = table_top10.index
	sns.barplot(data=order, x='shop_id', y='price',estimator=sum, order=table_top10.index, errwidth=0)
	
	# 시각화
	import matplotlib as mpl
	sns.set_style('whitegrid') #스타일은 원하는 것을 사용하세요.
	
	mpl.rc('font', family='Malgun Gothic') # Mac의 경우는 AppleGothic, 윈도우의 경우는 Malgun Gothic을 사용하면 됩니다 :) 
	mpl.rc('axes', unicode_minus=False)
	
	# from IPython.display import set_matplotlib_formats
	# set_matplotlib_formats('retina')
	
	order['timestamp'] = pd.to_datetime(order['timestamp'])
	order.dtypes
	
	plt.figure(figsize=[15,3.5])
	sns.lineplot(x='timestamp', y='price', data=order)
	
	order['hour'] = order['timestamp'].dt.hour
	table = order.pivot_table(values='price',
	                          index='hour',
	                          aggfunc='sum')
	
	table.head()
	
	plt.figure(figsize=[15,4])
	sns.lineplot(data=table, x=table.index, y='price')
	
	plt.figure(figsize=[15,4])
	sns.pointplot(data=table, x=table.index, y='price')
	
	user = pd.read_csv('./data/shoppingmall/user_info.csv')
	print(user.shape)
	user.head()
	
	merged = order.merge(user, on='user_id')
	merged.head()
	
	# 위의 병합된 테이블을 이용하여, 당일 매출 Top 10 쇼핑몰에서 구매를 한 고객들의 연령대 분포를 확인하고자 하는데
	# 나이 정보가 없는 경우는 -1이 입력되어 있기 때문에 이를 처리한다
	
	print(top10_index) # 비교하기 위해 출력
	
	merged_top10 = merged[(merged['shop_id'].isin(top10_index)) & (merged['age'] != -1)]
	merged_top10.head(20)
	
	fig, (ax1, ax2) = plt.subplots(ncols=2, nrows=1)
	fig.set_size_inches([15,4])
	
	sns.boxplot(data = merged_top10, x='shop_id', y='age', ax=ax1)
	sns.violinplot(data = merged_top10, x='shop_id', y='age', ax=ax2)
	
	fig.savefig('figure.png', dpi=400)
	
	def make_generation(age):
	    if age == -1:
	        return '미입력'
	    elif age // 10 >= 4:
	        return "30대 후반"
	    elif age // 10 == 1:
	        return "10대"
	    elif age % 10 < 3:
	        return str(age // 10 * 10) + f"대 초반"
	    elif age % 10 <= 6:
	        return str(age // 10 * 10) + f"대 중반"
	    else:
	        return str(age // 10 * 10) + f"대 후반"
	
	    
	print(make_generation(10))
	print(make_generation(23))
	print(make_generation(29))
	print(make_generation(32))
	print(make_generation(35))
	print(make_generation(40))
	
	age_list = ['10대', '20대 초반', '20대 중반', '20대 후반', '30대 초반', '30대 중반', '30대 후반']
	for i in age_list:
	    user["연령대"] = user['age'].map(make_generation)
	user.head()
	
	# shop = pd.read_csv('./data/shoppingmall/shop_info.csv')
	shop = pd.read_csv('./data/shoppingmall/shop_info.csv', index_col='shop_id')
	print(shop.shape)
	shop.head()
	
	merged_table = order.merge(user, on='user_id').merge(shop, on='shop_id')
	
	merged_table.head()
	
	def check_generation(row):
	    if row['category'] == '의류' and row['연령대'] == '미입력':
	        return True
	    else:
	        return row['연령대'] in str(row['age_y'])
	        
	merged_table['거래연령 일치여부'] = merged_table.apply(check_generation, axis=1)
	merged_table.head(2)
	
	table = merged_table.pivot_table(values='거래연령 일치여부',
	                                                    index='shop_id',
	                                                    aggfunc=['mean', 'count'])
	
	table.head()
	
	table[table.index.isin(top10_index)]
```
### 파이썬 머신러닝 machine learning
```
	# 보스턴 주택가격 데이터셋
	from sklearn.datasets import fetch_california_housing
	
	# 회귀분석을 위한 패키기
	from sklearn.linear_model import LinearRegression
	
	# 학습용, 검증용 데이터를 나누기 위한 패키기
	from sklearn.model_selection import train_test_split
	
	boston = fetch_california_housing()
	
	print("boston.data.shape\n",boston.data.shape)
	print("*"*100)
	print("boston\n",boston)
	print("*"*100)
	
	print(boston.DESCR) # boston 데이타 설명 보기
	print("*"*100)
	print("type(boston.data)\n",type(boston.data)) # boston 데이타 타입 확인
	print("*"*100)
	
	import pandas as pd # 판다스 임포트
	df = pd.DataFrame(boston.data)
	df.columns = boston.feature_names # df 의 컬럼들을 boston 컬럼명으로 변경
	
	# data
	X = df
	print(X)
	print("*"*100)
	
	# rable
	y = boston.target # 주택가격
	print(y)
	print("*"*100)
	
	## 데이타셋에서 훈련데이타와 검증(테스트) 데이타로 나누기 (7:3)
	# X_train : 훈련데이타
	# X_test : 테스트데이타
	# y_train : 훈련데이타 의 답
	# y_test : 테스트데이타 의 답
	X_train, X_test, y_train, y_test = train_test_split(X,y, test_size=0.2, random_state=0) # X data y rable 7:3 검증
	print("X_train\n",X_train.head())
	print("*"*100)
	print("y_train\n",y_train[:5])
	print("*"*100)
	
	# 훈련데이타 학습하기
	lr = LinearRegression()
	lr.fit(X_train, y_train) # 학습
	
	# 검증하기
	print("훈련 데이타셋 점수:{:.2f}".format(lr.score(X_train, y_train))) # 훈련데이타셋 점수
	print("*"*100)
	print("테스트 데이타셋 점수:{:.2f}".format(lr.score(X_test, y_test))) # 테스트 데이타셋 점수
	print("*"*100)
	
	# 예측하기
	print("X.head(1)\n",X.head(1)) # 훈련데이타에서 1번 데이타를 가지고 예측해보기
	print("*"*100)
	print("y[1]\n",y[1]) # 훈련데이타에서 1번 데이타 의 정답
	print("*"*100)
	
	import numpy as np
	sample_x = np.array([[8.3252,41.0,6.984127,1.02381,322.0,2.555556,37.88,-122.23]])
	print("sample_x\n",sample_x)
	print("*"*100)
	
	sample_y = lr석
```
### 파이썬 머신러닝 machine learning
```
	import pandas as pd # 데이타
	import numpy as np # 숫자
	
	# 데이타 로딩
	df = pd.read_csv('../data/titanic/temp/train.csv')
	print("df.head()\n",df.head())
	print("*"*100)
	
	# 컬럼명 미리 만들기
	cols_to_keep = ["Survived","Age","Fare"] # 생존, 나이, 요금
	
	# one hot incoding 방식
	dummy_Pclass = pd.get_dummies(df["Pclass"], prefix="Pclass")
	print("dummy_Pclass\n",dummy_Pclass)
	print("*"*100)
	
	dummy_Sex = pd.get_dummies(df["Sex"], prefix="Sex")
	print("dummy_Sex\n",dummy_Sex)
	print("*"*100)
	
	# 데이타 생성
	data = df[cols_to_keep] # 이차원 리스트 데이타프레임 만들기
	data = data.join(dummy_Sex)
	print("data\n",data)
	print("*"*100)
	
	data = data.join(dummy_Pclass)
	print("data\n",data)
	print("*"*100)
	
	## 데이타셋과 레이블(답)
	train_lable = data["Survived"] # 생존 여부
	train_data = data[data.columns[1:]] # 그 외 데이타
	print("train_data\n",train_data)
	print("*"*100)
	print("train_lable\n",train_lable)
	print("*"*100)
	
	# 머신러닝 로지스틱 회귀 분석
	from sklearn.linear_model import LogisticRegression
	lr = LogisticRegression() # 객체 생성
	lr.fit(train_data,train_lable) # 데이터, 정답 학습 시키기
	
	# 학습 검증하기
	print("훈련 점수 : {:.2f}\n".format(lr.score(train_data,train_lable))) # 데이터, 정답
	print("*"*100)
	
	# 예측
	data["predict"] = lr.predict(train_data) # 생존여부 예측해보기
	print("data.head(20)\n",data.head(20))
	print("*"*100)
	
	# 분석
	print("Age     Fare  Sex_female  Sex_male  Pclass_1  Pclass_2  Pclass_3") # 각 데이터 컬럼들로 정답 분석 가능
	print("*"*100)
	print(lr.coef_) # 각 데이터 컬럼들로 정답 분석 가능
```
### 파이썬 머신러닝 붓꽃
```
	'''
	붓꽃 데이타
	iris(붓꽃) 데이타셋 : 빅데이타, 머신러닝, 통계 등에서 많이 사용하는 데이타
	     Sepal Length 꽃받침의 길이 정보이다.  
	     Sepal Width 꽃받침의 너비 정보이다.  
	     Petal Length 꽃잎의 길이 정보이다.  
	     Petal Width 꽃잎의 너비 정보이다.    
	     Species 꽃의 종류 정보이다. ( setosa / versicolor / virginica)
	'''
	import numpy as np
	from sklearn import datasets
	
	iris = datasets.load_iris()
	
	# ------------ iris 데이타셋 살펴보기
	# 위의 참고문헌을 보면 iris는 Bunch클래스 객체인데 이는 Dictionary와 비슷한 구조
	# Dictionary는 기본적으로 key와 value로 구성된다
	
	display(iris.keys())
	display(iris['data'][:10])		# 붓꽃의 4가지 정보
	display(iris['target'])			# 붓꽃의 종류를 0,1,2로 표현
	display(iris['target_names'][:10]) # 붓꽃의 종류
	
	display(type(iris['data'])) # 'numpy.ndarray'
	display(iris['data'].shape)
	display(iris['target'].shape)
	
	# [참고] 간단하게 seaborn에 데이타셋으로 가져와서 그래프로 보면 꽃의 데이타로 species 를 알 수 있다
	#  그래프 ] 산점도 그래프
	import seaborn as sns
	
	sns.set(style='ticks')
	iris = sns.load_dataset('iris')
	sns.pairplot(iris, hue='species')

```
### 파이썬 머신러닝 SVC
```
	# 머신러닝 SVM
	import pandas as pd
	from sklearn import datasets
	from sklearn import svm, metrics
	from sklearn.model_selection import train_test_split
	import numpy as np
	
	#  1. 데이타로딩
	iris = datasets.load_iris()
	
	# 2. 데이터와 레이블 분리 변수 선언
	X= iris.data
	y= iris.target
	
	# 3. 데이터셋 분리 ( 학습데이타:검증데이타 = 7:3 )
	X_train,X_test,y_train,y_test = train_test_split(X,y,random_state=0, test_size=0.3)
	
	# 4. 알고리즘 데이터를 학습시키고 예측하기 ( 테스트 데이타로 예측 )
	model = svm.SVC()
	model.fit(X_train,y_train)
	
	# 5. 예측하기
	y_predict = model.predict(X_test) # 예측
	print(y_predict)
	print("*"*100)
	print(iris["target_names"][y_predict])
	print("*"*100)
	
	# 6. 정확도 ( 예측값과 테스트라벨의 차이 )
	y_predict = model.predict(X_test)
	print("정확도\n",metrics.accuracy_score(y_test,y_predict))
	print("*"*100)
	
	# 검증
	print("훈련데이타 검증: {:.2f}".format(model.score(X_train,y_train)))
	print("테스트데이타 검증: {:.2f}".format(model.score(X_test,y_test)))
	print("*"*100)
```
### 파이썬 머신러닝 DecisionTreeClassifier dtc
```
	from sklearn import datasets, metrics
	from sklearn.model_selection import train_test_split
	from sklearn.preprocessing import StandardScaler
	import numpy as np
	
	# 1. 데이타 로딩
	
	iris = datasets.load_iris()
	# 데이터 key 확인
	print("iris.keys()\n",iris.keys())
	print("*"*100)
	
	# 2. 데이터와 레이블 분리 변수 선언
	X= iris.data
	y= iris.target
	print("X\n",X)
	print("*"*100)
	print("y\n",y)
	print("*"*100)
	
	# 3. 데이타셋을 분리 ( 학습용:검증용 = 7:3 )
	X_train,X_test,y_train,y_test = train_test_split(X,y,random_state=0, test_size=0.3)
	
	# 5. 트리 모델 생성하고 학습하기
	from sklearn.tree import DecisionTreeClassifier
	dtc = DecisionTreeClassifier()
	dtc.fit(X_train,y_train) # 학습
	
	# 6. 검증
	print("훈련데이타 검증: {:.2f}".format(dtc.score(X_train,y_train)))
	print("테스트데이타 검증: {:.2f}".format(dtc.score(X_test,y_test)))
	print("*"*100)
	
	# 7. 정확도 ( 예측값과 테스트라벨의 차이 )
	y_predict = dtc.predict(X_test)
	print("정확도\n",metrics.accuracy_score(y_test,y_predict))
	print("*"*100)
	
	# 8. 예측
	y_predict = dtc.predict(X_test) # 예측
	print(y_predict)
	print("*"*100)
	print(iris["target_names"][y_predict])
	print("*"*100)
```
### 파이썬 머신러닝 graphviz
```
	'''
	[ 참고 ] graphviz 설치
	- Graphviz 프로그램 연결하는 라이브러리(??)
	    > pip install graphviz
	    
	- 직접설치 필요
	  :  https://graphviz.gitlab.io/_pages/Download/Download_windows.html
	  
	  (1) 다운받아 직접 설치
	       > Windows > Stable 2.38 Windows install packages > 10 > release >  graphviz-2.38.msi 다운로드 받아 실행
	'''
	#!pip install graphviz
	# pydotplus 설치
	#!pip install pydotplus
	
	from sklearn.tree import export_graphviz
	import pydotplus
	import graphviz
	from IPython.display import Image
	
	# graphviz의 경로를 환경변수 PATH에 등록
	import os
	os.environ['PATH'] += os.pathsep + 'C:/Program Files/Graphviz/bin'
	
	dot_data = export_graphviz(dtc, out_file=None, feature_names=iris.feature_names,
	                          class_names=iris.target_names, filled=True, rounded=True, special_characters=True)
	
	        #dot_data = export_graphviz(iris_tree, out_file=None, feature_names=['petal length', 'petal width'],
	        #                          class_names=iris.target_names, filled=True, rounded=True, special_characters=True)
	
	# 그래프 생성
	graph = pydotplus.graph_from_dot_data(dot_data)
	# 그래프를 이미지로 변환
	Image(graph.create_png())
```
### 파이썬 머신러닝 최적의 알고리즘 찾기 all_estimators
```
	### 최적의 알고리즘 찾기
	### all_estimators() 메소드 이용하여 모든 알고리즘 추출
	import pandas as pd
	from sklearn.model_selection import train_test_split
	from sklearn.metrics import accuracy_score
	from sklearn.utils import all_estimators
	
	import warnings
	warnings.filterwarnings('ignore')
	
	# 붓꽃 데이터 읽어 들이기
	iris_data = pd.read_csv("../data/iris/iris.csv", encoding="utf-8")
	
	# 붓꽃 데이터를 레이블과 입력 데이터로 분리하기 
	y = iris_data.loc[:,"variety"]
	x = iris_data.loc[:,["sepal.length","sepal.width","petal.length","petal.width"]]
	
	# (0) 학습 전용과 테스트 전용 분리하기 
	x_train, x_test, y_train, y_test = train_test_split(x, y, test_size = 0.2, train_size = 0.8, shuffle = True)
	
	# (1) classifier 알고리즘 모두 추출하기
	allAlgorithms = all_estimators(type_filter="classifier")
	
	for(name, algorithm) in allAlgorithms:
	    # (1) 알고리즘 종류 확인
	    # print(name)
	    
	    # 현재 자료형이 안 맞아서 학습되지 않는 알고리즘들이기에 제외해야 한다 -> 추가로 코딩을 예쁘게 
	    if name=='CheckingClassifier' or name=='ClassifierChain' \
	        or name=='MultiOutputClassifier' or name=='OneVsOneClassifier' \
	        or name=='OneVsRestClassifier' or name=='OutputCodeClassifier' \
	        or name=='VotingClassifier' or name=='StackingClassifier':
	        continue
	        
	    #-----------------------------------------    
	    # 에러가 발생하면 위에 print(name)으로 알고리즘을 확인 후 에러난 알고리즘이름을 위에 추가한다
	    
	    # (2) 각 알고리즘 객체 생성하기 
	    clf = algorithm()
	
	    # (3) 학습하고 평가하기 
	    clf.fit(x_train, y_train)
	    y_pred = clf.predict(x_test)
	    print(name,"의 정답률 = " , accuracy_score(y_test, y_pred))
	
	import pandas as pd
	from sklearn.utils import all_estimators
	from sklearn.model_selection import KFold
	import warnings
	from sklearn.model_selection import cross_val_score
	
	# 붓꽃 데이터 읽어 들이기
	iris_data = pd.read_csv("../data/iris/iris.csv", encoding="utf-8")
	
	# 붓꽃 데이터를 레이블과 입력 데이터로 분리하기 
	y = iris_data.loc[:,"variety"]
	x = iris_data.loc[:,["sepal.length","sepal.width","petal.length","petal.width"]]
	
	# classifier 알고리즘 모두 추출하기
	warnings.filterwarnings('ignore')
	allAlgorithms = all_estimators(type_filter="classifier")
	
	# (1)
	# K-분할 크로스 밸리데이션 전용 객체 
	# 데이타를 5그룹으로 분할하고 분할할 때 랜덤하게 섞는다
	kfold_cv = KFold(n_splits=5, shuffle=True)
	
	for(name, algorithm) in allAlgorithms:
	    
	    # 현재 자료형이 안 맞아서 학습되지 않는 알고리즘들이기에 제외해야 한다 -> 추가로 코딩을 예쁘게 
	    if name=='CheckingClassifier' or name=='ClassifierChain' \
	        or name=='MultiOutputClassifier' or name=='OneVsOneClassifier' \
	        or name=='OneVsRestClassifier' or name=='OutputCodeClassifier' \
	        or name=='VotingClassifier' or name=='StackingClassifier':
	        continue
	        
	    # (2) 각 알고리즘 객체 생성하기
	    clf = algorithm()
	
	    # (3)
	    # score 메서드를 가진 클래스를 대상으로 하기
	    if hasattr(clf,"score"):
	
	        # (4) 크로스 밸리데이션
	        # cross_val_score (clf:알고리즘 객체, x:입력데이터, y:레이블데이터, cv:교차검증 적용 객체)
	        scores = cross_val_score(clf, x, y, cv=kfold_cv)
	        print(name,"의 정답률=")
	        print(scores)
	
	import pandas as pd
	from sklearn.utils import all_estimators
	from sklearn.model_selection import KFold
	import warnings
	from sklearn.model_selection import cross_val_score
	
	# 붓꽃 데이터 읽어 들이기
	iris_data = pd.read_csv("../data/iris/iris.csv", encoding="utf-8")
	
	# 붓꽃 데이터를 레이블과 입력 데이터로 분리하기 
	y = iris_data.loc[:,"variety"]
	x = iris_data.loc[:,["sepal.length","sepal.width","petal.length","petal.width"]]
	
	# 학습 전용과 테스트 전용 분리하기 
	x_train, x_test, y_train, y_test = train_test_split(x, y, test_size = 0.2, train_size = 0.8, shuffle = True)
	
	# 그리드 서치에서 사용할 매개 변수 --- (*1)
	parameters = [
	    {"C": [1, 10, 100, 1000], "kernel":["linear"]},
	    {"C": [1, 10, 100, 1000], "kernel":["rbf"], "gamma":[0.001, 0.0001]},
	    {"C": [1, 10, 100, 1000], "kernel":["sigmoid"], "gamma": [0.001, 0.0001]}
	]
	
	# 그리드 서치 --- (*2)
	from sklearn.svm import SVC
	from sklearn.model_selection import GridSearchCV
	
	
	kfold_cv = KFold(n_splits=5, shuffle=True)
	clf = GridSearchCV( SVC(), parameters, cv=kfold_cv)
	clf.fit(x_train, y_train)
	print("최적의 매개 변수 = ", clf.best_estimator_)
	
	# 최적의 매개 변수로 평가하기 --- (*3)
	y_pred = clf.predict(x_test)
	print("최종 정답률 = " , accuracy_score(y_test, y_pred))
```
### 파이썬 형태소 분석
```
	# 설치
	#!pip install konlpy
	
	# KoNLPy의 kkma 형태소 분석기 확인 꼬꼬마
	from konlpy.tag import Kkma
	from konlpy.utils import pprint
	
	kkma = Kkma() # 꼬꼬마 객체
	
	# 문장분석
	print("꼬꼬마 문장분석\n",kkma.sentences("한국어 분석을 시작합니다 재미있어요~")) # ['한국어 분석을 시작합니다', '재미있어요~']
	
	# 명사분석
	print("꼬꼬마 명사분석\n",kkma.nouns("한국어 분석을 시작합니다 재미있어요~")) # ['한국어', '분석']
	
	# 품사분석
	print("꼬꼬마 품사분석\n",kkma.pos("한국어 분석을 시작합니다 재미있어요~"))
	
	print("*"*100)
	# 한나눔 분석
	from konlpy.tag import Hannanum
	hannanum = Hannanum()
	
	# 형태소분석
	print("한나눔 형태소분석\n",hannanum.morphs("한국어 분석을 시작합니다 재미있어요~")) # ['한국어 분석을 시작합니다', '재미있어요~']
	
	# 명사분석
	print("한나눔 명사분석\n",hannanum.nouns("한국어 분석을 시작합니다 재미있어요~")) # ['한국어', '분석', '시작']
	
	# 품사분석
	print("한나눔 품사분석\n",hannanum.pos("한국어 분석을 시작합니다 재미있어요~"))
	print("*"*100)
	
	# Okt 분석
	from konlpy.tag import Okt
	okt = Okt()
	
	# 명사분석
	print("Okt 명사분석\n",okt.nouns("한국어 분석을 시작합니다 재미있어요~")) # ['한국어', '분석', '시작']
	
	# 형태소분석
	print("Okt 형태소분석\n",okt.morphs("한국어 분석을 시작합니다 재미있어요~")) # ['한국어 분석을 시작합니다', '재미있어요~']
	
	# 품사분석
	print("Okt 품사분석\n",okt.pos("한국어 분석을 시작합니다 재미있어요~"))
	print("*"*100)
	
	# [연습] 독도는 대한민국의 아름다운 섬이다
	words = okt.pos("독도는 대한민국의 아름다운 섬이다")
	print(words)
	print("*"*100)
	words = okt.pos("독도는 대한민국의 아름다운 섬이다", norm=True, stem=True)
	print(words)
```
### 파이썬 네이버 영화 평점 텍스트 분석
```
	# 데이타 확인
	import pandas as pd
	
	train_df = pd.read_csv('nsmc-master/ratings_train.txt', sep='\t')
	train_df.head(5)
	
	# label 값이 1이면 긍정, 0이면 부정
	
	# 0과 1 (부정과 긍정)의 비율이 균등한 분포임을 확인
	train_df['label'].value_counts()
		
	# null 값 확인
	train_df.isnull().sum()
	
	# 'document' 컬럼에 Null 값이 있는데 이는 공백으로 변환
	train_df = train_df.fillna(' ')
	
	# 숫자를 공백으로 변경
	import re
	train_df['document'] = train_df['document'].apply(lambda x: re.sub(r"\d+",' ', x))
	
	# 테스트 데이타로 위와 동일한 작업
	test_df = pd.read_csv('nsmc-master/ratings_test.txt', sep='\t')
	test_df = test_df.fillna(' ')
	test_df['document'] = test_df['document'].apply(lambda x: re.sub(r"\d+",' ', x))
	
	#!pip install konlpy	
	#!pip install sklearn
	
	# 형태소 분석
	# Twitter 객체의 morphs() 는 입력 인자로 들어온 문장을 형태소 단어 형태로 토큰화해 리스트 객체로 반환	
	from konlpy.tag import Twitter
	
	twitter = Twitter()
	
	# 입력 인자로 들어온 텍스트를 형태소 단어로 토큰화하여 리스트 형태로 변환
	def tw_tokenizer(text):
	    tokens_ko = twitter.morphs(text)
	    return tokens_ko
	
	# 시간소요 ( 노트북 16G : 30 분이상)
	# TF-IDF 방식으로 
	from sklearn.feature_extraction.text import TfidfVectorizer
	from sklearn.linear_model import LogisticRegression
	from sklearn.model_selection import GridSearchCV
	
	tfidf_vect = TfidfVectorizer(tokenizer=tw_tokenizer, ngram_range=(1,2), min_df=3, max_df=0.9)
	# 상위 90%로 제한
	tfidf_vect.fit(train_df['document'])
	tfidf_matrix_train = tfidf_vect.transform(train_df['document'])
		
	# 학습 데이타에 적용한 TfidfVectorizer를 테스트 데이터에도 사용 ( 시간소요 : 10분)
	tfidf_matrix_test = tfidf_vect.transform(test_df['document'])
	
	lg_clf = LogisticRegression(random_state=0)
	
	# -------------- 모델에 학습
	lg_clf.fit(tfidf_matrix_train, train_df['label'])
	
	# -------------- 테스트를 예측
	preds = lg_clf.predict(tfidf_matrix_test)
	
	# --------------- 정확도
	from sklearn.metrics import accuracy_score
	print('TF-IDF LogisticRegression의 예측 정확도 : ', accuracy_score(test_df['label'], preds))
		
	# 파라미터 C 최적화를 위해 GridSearchCV를 이용
	params = {'C':[1, 3.5, 4.5, 5.5, 10]}
	grid_cv = GridSearchCV(lg_clf, param_grid=params, cv=3, scoring='accuracy', verbose=1)
	grid_cv.fit(tfidf_matrix_train, train_df['label'])
	print(grid_cv.best_params_, round(grid_cv.best_score_,4))
	
	# [결과] {'C': 3.5} 0.8592
	# C가 3.5일 때 0.8592 정확도임
	
	# classifier는 GridSearchCV에서 최적 파라미터로 학습된 classifier를 그대로 이용
	best_estimator = grid_cv.best_estimator_
	preds = best_estimator.predict(tfidf_matrix_test)
	
	from sklearn.metrics import accuracy_score
	print('LogisticRegression 정확도: ', accuracy_score(test_df['label'], preds))
	
	# type(test_df['document']) -> Series
	comment = pd.Series(['안보면 후회'])
	tfidf_matrix_test = tfidf_vect.transform(comment)
	preds = best_estimator.predict(tfidf_matrix_test)
	preds
	
	comment = pd.Series(['감독 꼬라지하고는'])
	tfidf_matrix_test = tfidf_vect.transform(comment)
	preds = best_estimator.predict(tfidf_matrix_test)
	preds
	
	comment = pd.Series(['이 훌륭한 배우들을 데려다가'])
	tfidf_matrix_test = tfidf_vect.transform(comment)
	preds = best_estimator.predict(tfidf_matrix_test)
	preds
	
	comment = pd.Series(['이 훌륭한 배우들을 데려다가 이렇게 만들었어'])
	tfidf_matrix_test = tfidf_vect.transform(comment)
	preds = best_estimator.predict(tfidf_matrix_test)
	preds
```
### 파이썬 WordCloud naver 검색 분석
```
	import pandas as pd
	import numpy as np
	import platform
	import matplotlib.pyplot as plt
	from bs4 import BeautifulSoup 
	from urllib.request import urlopen
	import urllib
	import time
	
	%matplotlib inline
	
	# 간단한 한글 폰드 등록
	from matplotlib import rc
	plt.rcParams['axes.unicode_minus']=False
	rc('font', family='Malgun Gothic')
	
	# 주소를 약간 수정함
	html = 'https://kin.naver.com/search/list.nhn?query={key_word}&page={num}'
	response = urlopen(html.format(num=1, key_word=urllib.parse.quote('여자친구 선물')))
	soup = BeautifulSoup(response, "html.parser")
	tmp = soup.find_all('dl')
	
	# 테스트로 첫번째 페이지의 텍스트만 가져온다
	tmp_list = []
	for line in tmp:
	    tmp_list.append(line.text)
	tmp_list
	#1000 만개 정도의 검색 결과를 읽어온다.
	# 첫번째 페이지 start=1, 두번째 페이지인 경우 start=11인거 확인한다.
	# 웹 페이지 직접 접근 할 땐느 간단이 time.sleep()으로 요청을 간격적으로 한다.
	# 시간이 10분 정도 소요되기에 상태바를 보여준다. ( tqdm.tqdm_notebook 이용)
	
	from urllib.request import urlopen
	from tqdm import tqdm_notebook
	
	present_candi_text = []
	
	# 1부터 99까지 지식인 검색 내용을 가져온다
	for n in range(1,100):
	    response = urlopen(html.format(num=n, key_word=urllib.parse.quote('여자친구 선물')))
	    soup = BeautifulSoup(response, "html.parser")
	    tmp = soup.find_all('dl')
	
	    for line in tmp:
	        present_candi_text.append(line.text)
	    time.sleep(0.5)
	    
	print("present_candi_text\n",present_candi_text[:5])
	print("*"*100)
	
	present_text = ""
	for each_line in present_candi_text:
	    present_text = present_text + each_line + "\n"
	
	# 형태소 분석
	import nltk
	from konlpy.tag import Okt
	okt = Okt()
	
	tokens_ok = okt.morphs(present_text)
	#print(tokens_ok)
	ok = nltk.Text(tokens_ok)
	print(len(set(ok.tokens))) # set 을 한다면 중복되는 단어들을 없애준다
	print("*"*100)
	
	print(tokens_ok)
	print("*"*100)
	
	# 많이 사용되는 단어 100개 추출
	print(ok.vocab().most_common(100))
	print("*"*100)
	
	# 의미없는 단어들을 수동으로 제거해준다.
	stop_words = ['.','가','요','답변','...','을','수','에','질문','제','를','이','도',
	                      '좋','1','는','로','으로','2','것','은','다',',','니다','대','들',
	                      '2017','들','데','..','의','때','겠','고','게','네요','한','일','할',
	                      '10','?','하는','06','주','려고','인데','거','좀','는데','~','ㅎㅎ',
	                      '하나','이상','20','뭐','까','있는','잘','습니다','다면','했','주려',
	                      '지','있','못','후','중','줄','6','과','어떤','기본','!!',
	                      '단어','선물해','라고','중요한','합','가요','....','보이','네','무지',
	              "\n","ㅠㅠ","??","\n\n","\n\n\n","\n\n\n\n","|","&","Q","A","****)"]
	
	tokens_ok = [each_word for each_word in tokens_ok 
	                          if each_word not in stop_words]
	
	# 많이 사용되는 단어 100개 추출
	ok = nltk.Text(tokens_ok)
	print(ok.vocab().most_common(100))
	print("*"*100)
	
	#!pip install WordCloud
	# """ 워드 크라우드 그리기 """
	from wordcloud import WordCloud, STOPWORDS
	from PIL import Image
	
	# 많이 사용되는 단어 300개
	data = ok.vocab().most_common(300)
	
	# 단어 추출을 위한 리스트
	data_list = []
	for txt, cnt in data:
	    data_list.append(txt) # 단어만 추출
	print("data_list\n",data_list) # 확인
	print("*"*100)
	
	data_str = ' '.join(data_list) # 단어 사이사이 마다 공백을 끼워 넣겠다
	
	wordcloud = WordCloud(font_path="malgun",
	                     background_color="white",
	                     width=400,
	                     height=400,
	                     scale=2.0,
	                     max_font_size=200)
	wordcloud.generate(data_str)
	plt.imshow(wordcloud, interpolation="bilinear")
	plt.axis("off")
	plt.show()
```
### 파이썬 NaiveBayesClassifier 나이브베이즈 분류
```
	from nltk.tokenize import word_tokenize
	import nltk
	#nltk.download('punkt')
	""" 훈련데이타 """ 
	train = [('i like you', 'pos'), 
	         ('i hate you', 'neg'), 
	         ('you dislike me', 'neg'),
	         ('i like her', 'pos')]
	
	# 훈련문장에서 사용된 단어들 모두 찾기
	all_words = set(word.lower() for sentence in train 
	                             for word in word_tokenize(sentence[0]))
	print("all_words\n",all_words)
	
	# 위 모든 단어들이 각각 훈련문장에 속한 단어인지 아닌지 확인
	t = [({word: (word in word_tokenize(x[0])) for word in all_words}, x[1])
	                                                        for x in train]
	print("t\n",t)
	print("*"*100)
	
	# 나이브베이즈분류 NaiveBayes 분류
	clf = nltk.NaiveBayesClassifier.train(t)
	
	# 테스트데이타
	test_sent = "i seoul you"
	test_sent_features = {word.lower() : (word in word_tokenize(test_sent.lower())) for word in all_words}
	print("test_sent_features\n",test_sent_features)
	print("*"*100)
	
	# 예측
	clf.classify(test_sent_features)
```
### 파이썬 NaiveBayesClassifier 나이브베이즈 분류 한글
```
	from nltk.tokenize import word_tokenize
	import nltk
	
	# 2020.07 실행시 에러 발생하여 추가
	#nltk.download('punkt')
	
	from konlpy.tag import Okt
	okt = Okt()
	
	""" 훈련데이타 """
	
	train = [('메리가 좋아', 'pos'), 
	         ('고양이도 좋아', 'pos'),
	         ('난 수업이 지루해', 'neg'),
	         ('메리는 이쁜 고양이야', 'pos'),
	         ('난 마치고 메리랑 놀거야', 'pos')]
	
	all_words = set(word.lower() for sentence in train 
	                    for word in word_tokenize(sentence[0]))
	print("all_words\n",all_words)
	print("*"*100)
	
	t = [({word: (word in word_tokenize(x[0])) for word in all_words}, x[1])
	                                                        for x in train]
	print("t\n",t)
	print("*"*100)
	
	# 나이브베이즈 분류기 훈련
	clf = nltk.NaiveBayesClassifier.train(t)
	
	# 테스트데이타
	test_sent = "난 수업을 마치고 메리랑 놀거야"
	test_sent_features = {word.lower() : (word in word_tokenize(test_sent.lower())) for word in all_words}
	print("test_sent_features\n",test_sent_features)
	print("*"*100)
	
	# 예측
	print("예측\n",clf.classify(test_sent_features))
	print("*"*100)
	
	# github의 Lucy Park 님의 코드에 따르면 태그를 붙여주는 것이 좋다고 권장함
	def tokenize(doc):
	    return ['/'.join(t) for t in okt.pos(doc, norm=True, stem=True)]
	
	train_docs = [(tokenize(row[0]),row[1]) for row in train]
	print("train_docs\n",train_docs)
	print("*"*100)
	
	# 사용되는 전체 단어(말뭉치) 찾기
	tokens = [t for d in train_docs for t in d[0]]
	print("tokens\n",tokens)
	print("*"*100)
	
	# 훈련문장의 단어들이 전체 단어(말뭉치)에 있는 단어인지 확인
	# 명사와 조사를 구분하여 판독이 용이
	def term_exists(doc):
	    return {word: (word in set(doc)) for word in tokens}
	
	train_xy = [(term_exists(d),c) for d,c in train_docs]
	print("train_xy\n",train_xy)
	print("*"*100)
	
	test_sentence = "난 수업을 마치면 메리랑 놀거야"
	test_docs = okt.pos(test_sentence)
	print("test_docs\n",test_docs)
	print("*"*100)
	
	test_sent_features = {word:(word in tokens) for word in test_docs}
	print("test_sent_features\n",test_sent_features)
	print("*"*100)
	
	print("예측\n",clf.classify(test_sent_features))
	print("*"*100)
```
### 파이썬 텐서플로우 제일 많이 쓰는 머신러닝
```
	#!pip install tensorflow
	# (1) tf.keras 를 이용한 XOR 네트워크 계산
	import tensorflow as tf
	import numpy as np
	
	# 1. 데이타 확인
	x = np.array([[1,1], [1,0], [0,1], [0,0]])
	#y = np.array([[0], [1], [1], [0]]) # XOR
	y = np.array([[1], [1], [1], [0]]) # OR
	
	# 2. 모델을 설정
	    # 1. 리스트형
	# model = tf.keras.Sequential([
	#     tf.keras.layers.Dense(units=2, activation="sigmoid", input_shape=(2,)), # 뉴런2개, 활성함수, 들어오는내용2개
	#     tf.keras.layers.Dense(units=1, activation="sigmoid") # 뉴런1개, 활성함수
	# ])
	
	    # 2. add() 함수 추가
	model = tf.keras.Sequential()
	model.add(tf.keras.layers.Dense(units=2, activation="sigmoid", input_shape=(2,))) # 뉴런2개, 활성함수, 들어오는내용2개
	model.add(tf.keras.layers.Dense(units=1, activation="sigmoid")) # 뉴런1개, 활성함수
	    
	# 3. 모델 실행
	model.compile(optimizer="sgd", loss="mse") # 경사 하강법
	
	# 4. 모델 요약
	model.summary()
	
	# 4. 모델에 학습
	history = model.fit(x, y, epochs=100, batch_size=1) # 100번 반복, 1개씩
	print("학습내역\n",history)
	print("*"*100)
	
	# 4.5  검증하기
	print("검증\n",model.evaluate(x,y))
	print("*"*100)
	
	# 5. 예측하기
	print("예측결과\n",model.predict(x))
```
###
```
	import numpy as np
	import tensorflow as tf
	
	np.random.seed(3)
	tf.random.set_seed(3)
	  
	# 준비된 수술 환자 데이터를 불러옴
	data_set = np.loadtxt("./dataset/ThoraricSurgery.csv", delimiter=",")
	  
	# 환자의 기록과 수술 결과를 X와 Y로 구분하여 저장
	X = data_set[:,0:17]
	Y = data_set[:,17]
	
	print("17 개 항목\n",X[0])   # 17 개 항목
	print("*"*100)
	print("결과\n",Y[0])   # 결과
	print("*"*100)
	
	# [1]  모델 생성 - 리스트형
	model = tf.keras.Sequential([
	    tf.keras.layers.Dense(units=30, activation="relu", input_dim=17), # 
	    tf.keras.layers.Dense(units=1, activation="sigmoid") # 
	])
	
	# [2]  모델 생성 - add 함수
	# model = tf.keras.Sequential()
	# model.add()
	
	# [참고] 모델 요약
	model.summary()
	
	# 모델 컴파일
	model.compile(loss="mean_squared_error", optimizer="adam", metrics=["accuracy"])
	
	# 모델 학습
	model.fit(X, Y, epochs=100, batch_size=10) # 100번 반복 학습 10개씩
	
	# 모델 정확도
	test_loss, test_accuracy = model.evaluate(X,Y)
	print("정확도\n",test_accuracy)
	print("*"*100)
	
	# 예측
	pre_x = [[447,8,5.2,4.1,0,0,0,0,0,0,12,0,0,0,0,0,49]] # 환자 정보
	pre_x = np.array(pre_x)
	print("예측\n",model.predict(pre_x))
	print("*"*100)
	
	# 예측
	pre_x = [[14.,2.,3.98,3.06,2.,0.,0.,0.,1.,1.,14.,0.,0.,0.,1.,0.,80.]] # 환자 정보
	pre_x = np.array(pre_x)
	print("예측\n",model.predict(pre_x))
	print("*"*100)
	
	# 예측
	pre_x = [[42.,2.,3.24,2.52,1.,0.,0.,0.,1.,0.,12.,0.,0.,0.,1.,0.,63.]] # 환자 정보
	pre_x = np.array(pre_x)
	print("예측\n",model.predict(pre_x))
	print("*"*100)
```
### 파이썬 웹(web) 프레임워크(framework)
```
	1. Django
		가장 유명
		중규모 이상의 웹 앱을 구현한다면 적합
		개발에 필요한 기능이 구현되어 있다
	2. Flask
		마이크로 앱 프레임워크
		핵심기능을 유지하면서 확장성을 가진다
		간단한 웹 서버 역할만
	설치
		pip install flask
	웹 예제
		from flask import Flask
		app = Flask(__name__)
		
		@app.route("/")
		def hello_word():
		    return "hello world"
	실행
		flask run
		flask --app app0_route run
```
### 파이썬 루트
```
	# app0_route.py
	from flask import Flask
	app = Flask(__name__)
	
	@app.route("/") # 127.0.0.1
	@app.route("/index") # 127.0.0.1:5000/index
	def hello_word():
	    return "hello world2222222"
	
	
	@app.route("/users/<username>") # 127.0.0.1:5000/users/홍길동
	def get_user(username):
	    return username+"님이 입장하셨습니다."
	
	@app.route("/posts/<int:post_id>") # 127.0.0.1:5000/posts/111
	def get_post(post_id):
	    return str(post_id) + "번 글을 확인"
```
### 파이썬 렌더
```
	# app1_render.py
	from flask import Flask, render_template
	
	# 파일명, static폴더, 템플릿폴더
	app = Flask(__name__, static_folder="static", template_folder="templates")

	# 렌더 테스트
	@app.route("/hello")
	def hello():
	    return render_template("hello.html") # import 필요 - 화면 넘기기
	# http://127.0.0.1:5000/hello

	# 진자 테스트
	@app.route("/hello_jinja/<nickname>")
	def hello_jinja(nickname):
	    return render_template("hello_jinja.html", name=nickname) # import 필요 - 화면 넘기기
```
### 파이썬 진자 jinja
```
	base.html
		<!DOCTYPE html>
		<html>
		<head>
		    <link type='text/css' rel='stylesheet' href="/static/css/hello.css">
		    {% block head %}
		    {% endblock %}
		</head>
		<body>
		    {% block body %}
		    {% endblock %}
		</body>
		</html>
	hello_jinja.html
		{% extends "layout/base.html" %}

		{% block head %}
		    <title>진자란 무엇인가</title> <!-- base.html 파일에서 title이 된다 -->
		{% endblock %}
		
		{% block body %} <!-- base.html 파일에서 body 내용이 된다 -->
		    {% if name == "홍길동" %}
		        <h1>{{name}}님 반갑습니다.</h1>
		    {% else %}
		        <img src="/static/image/hello_world.png">
		    {% endif %}
		{% endblock %}
```
### 파이썬 Blueprint 블루프린트
```
	# app2_Blueprint
		'''
		    Blueprint
		        - 앱의 규모가 클 때 앱을 분할하여 관리
		        - 공통 url을 묶어 관리
		'''
		
		from flask import Flask
		from app3_v1 import app as v1_app
		from app3_v2 import app as v2_app
		
		app = Flask(__name__)
		app.register_blueprint(v1_app) # 블루프린트 등록
		app.register_blueprint(v2_app) # 블루프린트 등록
		
		# [서버 실행] flask --app app2_Blueprint run
		# [브라우저 확인] http://127.0.0.1:5000/v1/users
		#               http://127.0.0.1:5000/v2/users
	# app3_v1.py
		from flask import Blueprint

		# app = Blueprint(블루프린트앱의 이름, 보통 __name__ 지정, url 구별하기 위한 경로)
		app = Blueprint("v1",__name__,url_prefix="/v1") # localhost:5000/v1
		
		# localhost:5000/v1/users
		@app.route("/users")
		def users():
		    return "여기는 v1/users 입니다."
	# app3_v2.py
		from flask import Blueprint

		# app = Blueprint(블루프린트앱의 이름, 보통 __name__ 지정, url 구별하기 위한 경로)
		app = Blueprint("v2",__name__,url_prefix="/v2") # localhost:5000/v2
		
		# localhost:5000/v2/users
		@app.route("/users")
		def users():
		    return "여기는 v2/users 입니다."
```
### 파이썬 db mysql 연결
```
	환경변수
		.env 파일 생성
			FLASK_APP=apps.app:create_app
			FLASK_ENV=development
	설치
		pip install python-dotenv
	# apps/app.py
		from flask import Flask
		from apps.crud import views as crud_views
		
		def create_app():
		    app = Flask(__name__)
		    app.register_blueprint(crud_views.crud, url_prefix="/crud")
		
		    return app
	# apps/crud/views.py
		from flask import Blueprint, render_template
		from apps.crud import dbconn
		
		crud = Blueprint("crud",
		                 __name__,
		                 static_folder="static", # css 파일, image 파일
		                 template_folder="templates") # 화면 파일
		
		@crud.route("/")
		def index():
		    return render_template("crud/index.html")
		
		@crud.route("/dbtest")
		def dbtest():
		    db_class = dbconn.Database()
		    print("DB연결성공")
		    print("*"*100)
		
		    query = "SELECT empno, ename FROM emp"
		    rows = db_class.executeAll(query)
		    print(rows)
		    return render_template("crud/dbtest.html", resultData=rows) # 변수명 resultDate로 행 1줄을 넘긴다
	# apps/crud/dbconn.py
		import pymysql # mysql 임포트
		
		# DB 클래스 생성
		class Database():
		
		    # 생성자
		    def __init__(self):
		        # 멤버변수 지정
		        self.db = pymysql.connect(
		            host="localhost", # IP
		            user="scott", # USER
		            password="tiger", # PASS
		            db="basic", # DATABASE
		            charset="utf8"
		        )
		        self.cursor = self.db.cursor(pymysql.cursors.DictCursor)
		
		    # 메소드
		    def executeOne(self, query, args={}):
		        self.cursor.execute(query,args)
		        row = self.cursor.execute().fetchone()
		        return row
		
		    # 메소드
		    def executeAll(self,query,args={}):
		        self.cursor.execute(query,args)
		        rows = self.cursor.fetchall()
		        return rows
		
		    # 메소드
		    def execute(self, query, args={}):
		        self.cursor.execute(query,args)
		
		    # 커밋 메소드
		    def commit(self):
		        self.db.commit()
	dbtest.html
		{% extends "crud/base.html" %}
		
		{% block title %} 우리의 앱 {% endblock %}
		
		{% block content %}
		    <div class="jumbo">
		        <h2> 플라스크 + 마이에스큐엘 </h2>
		        <hr/>
		        {# 추후에 레코드를 전부 받아서 출력(반복문은???) #}
		        {% for i in resultData %}
		            <h5> 아이디 {{i.empno}}</h5>
		            <h5> 사원명 {{i.ename}}</h5>
		            <hr/>
		        {% endfor %}
		    </div>
		{% endblock %}
```
### node.js 노드
```
	설치
		nodejs.org - node.js 서버
		https://code.visualstudio.com/ - 비주얼스튜디오코드
	실행
		Terminal
			node hello.js - hello.js 파일 실
```
### node.js 웹 작성 실행
```
	// [1] 실행구동 확인
	console.log("hello");
	
	// [2] 웹구동 확인
	let http = require("http");
	
	function onRequest(request,response){
	    response.writeHead(200,{ "Content-Type": "text/plain" }); // 글자 타입 설정
	    response.write("Hello~~ World~~~~!!!!") // 글씨 작성
	    response.end() // 응답 끝
	}
	
	// 8888 포트로 접속했을 경우 onRequest 함수 실행하면서 웹 서버를 띄운다
	http.createServer(onRequest).listen(8888); 
```
### node.js 비동기 방식
```
	// Ex02_async_callback.js
	function order(coffee, callback){
	    console.log(`${coffee} 주문`)
	    console.log(coffee + "주문")
	
	    setTimeout(()=>{
	        callback(coffee);
	    }, 2000); // 2초 타이머
	}
	
	function pickup(result){
	    console.log(`${result} 준비 완료`);
	}
	
	order("카페라떼", pickup)
	
	console.log("다른 작업 진행")
```
### node.js 비동기 방식이라 데이타를 받을 때 기다려 줘야 함
```
	then 방식 기다리고나서 실행
		// 사이트에서 데이타를 받아오고
		// then 그러고나서 () 함수를 실행
		fetch("http://jsonplaceholder.typicode.com/users")
		.then( response => response.json() )
		.then( users=> console.log(users) ); 
		
		console.log("다른 작업");
	async
	await 방식 기다리고나서 실행
		// Ex05_async_await.js
	
		async function init(){
		    // 사이트안에 데이타를 가져옴
		    const response = await fetch("http://jsonplaceholder.typicode.com/users");
		
		    // 가져온 데이타를 json으로 변환후 users 에 담기
		    const users = await response.json();  
		    console.log(users)
		}
		
		init();
```
### node.js exepress
```
	프로젝트 설정
		npm init
			entry point - 시작 화면
			git repository - 깃 연결
	express 설치
		npm install express
	코드
		// App1.js
		// 서버
		const express = require("express");
		const app = express();
		const port = 3000;
		
		// 대기하다가 3000포트번호로 접속했을 경우 함수 실행
		app.listen(port,()=>{
		    console.log("서버실행")
		});
		
		// 요청(request)가 들어오면 지정된 함수를 호출(콜백함수)
		app.get("/", (req,res)=>{
		    res.send("노드 헬로우 성공");
		});
		
		// 요청(/func1)
		app.get("/func1", (req,res)=>{
		    res.send("헬로우 -1");
		});
		
		// 요청(/func2)
		app.get("/func2", (req,res)=>{
		    res.send("헬로우 -2");
		});
		
		// 콜백함수 다음 불러지는 함수는 미들웨어함수
		app.get("/func3", (req,res,next)=>{
		    console.log(" 첫번째 호출 ");
		    next();    
		}, function(req,res){
		    res.send(" 두번째 호출");
		});
		
		// 콜백함수 다음 불러지는 함수는 미들웨어함수 배열로
		const method1 = function(req, res, next){
		    console.log("첫번째 호출 1");
		    next();
		};
		
		const mehotd2 = function(req, res){
		    res.send("두번째 호출2");
		};
		
		app.get("/func4", [method1, mehotd2]);
```
### node.js 라우터 router
```
	App.js
		const express = require("express");
		const app = express();
		const port = 3000;
		
		app.listen(port, ()=>{
		    console.log("서버실행");
		});

		// 외부 js 파일 가져오기
		const customerRoute = require("./router/customer");
		
		app.use("/customer", customerRoute);
	customer.js
 		// router/customer.js
		const express = require("express");
		const router = express.Router();
		
		router.get("/",(req, res)=>{
		    res.send("고객정보 조회 /customer 라우터");
		});
		
		router.post("/insert",(req, res)=>{
		    res.send("고객정보 입력 /customer/insert 라우터");
		});
		
		
		router.put("/update",(req, res)=>{
		    res.send("고객정보 수정 /customer/update 라우터");
		});
		
		router.delete("/delete",(req, res)=>{
		    res.send("고객정보 삭제 /customer/delete 라우터");
		});
		
		// 설정 라우터들을 외부에서 사용 가능하도록
		module.exports = router;
```
### node.js mysql
```
	설치
		npm install mysql
	sql.js 파일
		// 2_db/mysql/sql.js
		module.exports = {
		    // 1 검색
		    employeeList : `SELECT * FROM emp`,
		    
		    // 2 입력
		    // 실제 입력 - > INSERT INTO emp set empno=9912, ename='홍씨', job='아이티'
		    employeeInsert : `INSERT INTO emp SET ?`,
		
		    // 3 수정
		    // 실제 수정 - > UPDATE emp SET ename='김씨', job='개발' WHERE empno=9912
		    employeeUpdate : `UPDATE emp SET ? WHERE empno=?`,
		
		    // 4 삭제
		    employeeDelete : `DELETE FROM emp WHERE empno=?`
		}
	index.js 파일
		// 2_db/mysql/index.js
		const mysql = require("mysql");
		const sql = require("./sql.js");
		
		// ConnectionPool 생성
		const pool = mysql.createPool({
		    host : "127.0.0.1",
		    port : 3306,
		    user : "scott",
		    password : "tiger",
		    database : "basic",
		    connectionLimit : 10
		});
		
		// 쿼리를 실행하고 결과를 반영하는 함수
		const query = async (alias, value)=>{
		    return new Promise((resolve, reject)=>{
		        pool.query(sql[alias], value, (error, results)=>{
		            if(error){
		                console.log("에러 발생");
		                reject(error);
		            }else{
		                resolve(results);
		            }
		        });
		    });
		};
		
		module.exports = {query};
	App_mysql.js 파일
		// 2_db/App_mysql.js
		const express = require("express");
		const app = express();
		const port = 3000;
		
		app.listen(port, ()=>{
		    console.log("서버실행");
		});
		
		const mysql = require("./mysql"); // index.js 실행
		
		// 데이타 검색
		app.get("/api/employee", async (req, res)=>{
		    const employees = await mysql.query("employeeList");
		    console.log(employees);
		    res.send(employees);
		});
		
		// 데이타 입력
		app.use(
		    express.json({
		        limit : "50mb"
		    })
		);
		app.post("/api/employee/insert", async (req, res)=>{
		    console.log("입력");
		    console.log(req.body);
		
		    const result = await mysql.query("employeeInsert", req.body.param);
		    res.send(result);
		});
		
		// 데이타 수정
		app.put("/api/employee/update", async (req, res)=>{
		    console.log("수정");
		    console.log(req.body);
		
		    const result = await mysql.query("employeeUpdate", req.body.param);
		    res.send(result);
		});
		
		// 데이타 삭제
		app.delete("/api/employee/delete/:id", async (req, res)=>{
		    console.log("삭제");
		    // :id 값을 읽어서 id에다가 담기
		    const {id} = req.params;
		
		    const result = await mysql.query("employeeDelete", id);
		    res.send(result);
		});
```
### node.js mongodb
```
	설치
		https://www.mongodb.com/try/download/community
	환경변수
		Path 를 bin 경로로 설정
	접속
		cmd - mongo
	유저생성
		db.createUser({
			user: "root",
			pwd: "admin1234",
			roles: [
				{ role: "userAdminAnyDatabase", db: "admin" },
				{ role: "dbAdminAnyDatabase", db: "admin" },
				{ role: "readWriteAnyDatabase", db: "admin" }
			]
		});
	VisualStudioCode 터미널
		npm install mongoose@6.10
	index.js
		const mongoose = require("mongoose");

		const connect = ()=>{
		    // root계정:비번admin1234@IP:port
		    mongoose.connect("mongodb://root:admin1234@127.0.0.1:27017", {dbName : "test"}, (error)=>{
		        if(error){
		            console.log("Mongodb 연결 실패 :", error);
		        }else{
		            console.log("MongoDB 연결 성공 : 127.0.0.1:27017/test")
		        }
		    });
		};
		
		module.exports = {connect}
	emp.js
		// schemas/emp.js

		const mongoose = require("mongoose");
		const { type } = require("os");
		const {Schema} = mongoose;
		
		/*
		    스키마 타입
		        Number / String / Date / Boolean
		        ObjectId : 객체 아이디
		        Buffer : 파일을 담을 수 있는 버퍼
		        Array : 여러개
		*/
		const empSchema = new Schema({
		    empno : {
		        type : Number,
		        required : true,
		        unique : true
		    },
		    ename : {
		        type : String,
		        required : true
		    },
		    job : {
		        type : String 
		    },
		    sal : {
		        type : Number
		    }
		});
		
		const Emp = mongoose.model("emp", empSchema);
		
		// module.exports = {Emp} 차이는? 
		module.exports = Emp;
	App_mongodb.js
		const express = require("express");
		const app = express();
		
		app.listen(3000, ()=>{
		    console.log("웹 서버 구동중");
		});
		
		const mongodb = require("./0_async/4_mongodb");
		mongodb.connect();
		
		const Emp = require("./0_async/4_mongodb/schemas/emp");
		
		// 전체 검색
		app.get("/emp", async (req, res)=>{
		    const employees = await Emp.find();
		    console.log(employees);
		    res.send(employees);
		});
		
		// 입력
		app.get("/empInsert", async (req, res)=>{
		    const empInsert = await Emp.create({
		        empno : 1112,
		        ename : "박길동",
		        job : "개발",
		        sal : 5000
		    });
		    console.log(empInsert);
		});
		
		// 입력 여러개
		app.get("/empInsert2", async (req, res)=>{
		    const empInsert2 = await Emp.create([
		        {
		            empno : 1113,
		            ename : "최길동",
		            job : "IT",
		            sal : 4000
		        },
		        {
		            empno : 1114,
		            ename : "김길동",
		            job : "개발",
		            sal : 6000
		        }
		    ]);
		    console.log(empInsert2);
		});
		
		// 검색
		app.get("/empTest", async (req, res)=>{
		    // 전체검색
		    // const employees = await Emp.find({});
		
		    // 월급이 5000이상 검색
		    // const employees = await Emp.find({ 
		    //     sal : { $gte:5000 }
		    // });
		
		    // 월급이 5000이상 이름이 김길동
		    // const employees = await Emp.find({
		    //     sal : { $gte:6000 },
		    //     ename : "김길동"
		    // });
		
		    // 이름이 "길동"이 포함 
		    // 결과값 ename, sal
		    const employees = await Emp.find({
		        ename: /김/
		    },"ename sal");
		
		    console.log(employees);
		    res.send(employees);
		});
		
		// 수정
		app.get("/empUpdate1", async (req, res)=>{
		    const empUpdate1 = await Emp.updateOne({empno : 1113}, {job : "개발"});
		    console.log(empUpdate1);
		});
		
		// 수정 여러개
		app.get("/empUpdate2", async (req, res)=>{
		    const empUpdate2 = await Emp.updateMany({sal : {$gte : 5000}}, {job : "디자인"});
		    console.log(empUpdate2);
		});
		
		// 삭제
		app.get("/empDelete", async (req, res)=>{
		    const empDelete = await Emp.deleteOne({empno : 1113});
		    console.log(empDelete);
		});
		
		// 여러개 삭제
		app.get("/empDelete2", async (req, res)=>{
		    const empDelete2 = await Emp.deleteMany(
		        {$or:[
		            {empno:1234},
		            {empno:1114}
		        ]});
		    console.log(empDelete2);
		});
```
### node.js 게시판 board CRUD
```
	설치
		npm init
			초기 프로젝트 설정
		npm install express
			DB 연동
		npm install mysql
			mysql 서버
		npm install nodemon
			서버를 자동으로 껐다 켜주는
		npm install ejs
		npm install body-parser
		npm install path
			경로를 편하게 해주는
```
### node.js 게시판 board CRUD
```
	database.js
		// config/database.js
		module.exports = {
		    host : "localhost",
		    user : "scott",
		    password : "tiger",
		    database : "basic"
		}
	sql.js
		module.exports = {
		    // 1 검색
		    boardList : `SELECT bNum, bTitle, bName, bContent, mId, bPw, date_format(insertDate, '%Y-%m-%d') as insertDate, date_format(updateDate, '%Y-%m-%d') as updateDate FROM node_board`,
		    boardInsert : `INSERT INTO node_board(bTitle, bName, bContent, mId, bPw) VALUES(?, ?, ?, ?, ?)`,
		    boardDetail : `SELECT bNum, bTitle, bName, bContent, mId, bPw, date_format(insertDate, '%Y-%m-%d') as insertDate, date_format(updateDate, '%Y-%m-%d') as updateDate FROM node_board WHERE bNum = ?`,
		    boardUpdate : `UPDATE node_board SET bTitle=?, bName=?, bContent=?, mId=?, bPw=? WHERE bNum=?`,
		    boardDelete : `DELETE FROM node_board WHERE bNum = ?`    
		}
	board.js
		const express = require("express");
		const ejs = require("ejs");
		const path = require("path");
		const bodyParser = require("body-parser");
		
		const app = express();
		
		// 환경변수 쪽에 포트번호가 지정되어 있는걸 쓰거나 3000번 지정
		app.set("port", process.env.PORT || 3000);
		
		// ejs 파일로 화면 이동을 위해
		app.set("view engine", "ejs");
		
		// public/board_write.html form태그 안 input 값 받아오기 쉽게
		app.use(bodyParser.urlencoded({ extended : true }));
		
		app.listen(app.get("port"), ()=>{
		    console.log("Express 서버 구동 >>",app.get("port"));
		});
		
		// DB 연동
		const mysql = require("mysql");
		const dbconfig = require("./config/database");
		const sqlQuery = require("./config/sql");
		const conn = mysql.createConnection(dbconfig);
		
		// 전체 조회
		// "SELECT bNum, bTitle, bName, bContent, mId, bPw, insertDate, updateDate FROM node_board"
		app.get("/", async (req, res)=>{
		    const sql = await sqlQuery.boardList;
		    //const sql = "SELECT bNum, bTitle, bName, bContent, mId, bPw, date_format(insertDate, '%Y-%m-%d') as insertDate, date_format(updateDate, '%Y-%m-%d') as updateDate FROM node_board";
		
		    conn.query( sql, (err, result, fields)=>{
		        if(err){
		            throw err; // err 가 났을 경우
		        }
		        console.log(result);
		
		        // 뷰페이지 렌더링
		        // res.render("파일경로",{ 데이타명 : 전송할데이타 });
		        res.render("board_index", { users : result });
		    } );
		});
		
		// 글쓰기 입력화면 이동
		app.get("/create", (req, res)=>{
		    // 현재 경로에서 public/board_write.html 로 응답
		    res.sendFile(path.join(__dirname, "public/board_write.html"));
		});
		
		// 글쓰기 저장
		app.post("/insert", (req, res)=>{
		    // public/board_write.html form태그 안 input 값 받아오기
		    const bTitle = req.body.bTitle;
		    const bName = req.body.bName;
		    const bContent = req.body.bContent;
		    const mId = req.body.mId;
		    const bPw = req.body.bPw;
		    
		    const param = [bTitle, bName, bContent, mId, bPw];
		
		    //console.log("사용자 입력 값", param);
		
		    //const sql = "INSERT INTO node_board(bTitle, bName, bContent, mId, bPw) VALUES(?,?,?,?,?)";
		    const sql = sqlQuery.boardInsert;
		    conn.query(sql, param, (err, result, fields)=>{
		        if(err){
		            throw err;
		        }
		        console.log("입력성공", result);
		        res.redirect("/");
		    });
		});
		
		// 수정화면 이동
		app.get("/edit/:bNum", (req, res)=>{
		    const bNum = req.params.bNum;
		    //console.log("글번호에 의한 조회", bNum);
		
		    const sql = sqlQuery.boardDetail;
		    conn.query(sql, [bNum], (err, result, fields)=>{
		        if(err){
		            throw err;
		        }
		        console.log("글번호에 의한 조회", result);
		        res.render("board_edit", { user : result });
		    });
		});
		
		// 수정 처리
		app.post("/update/:bNum", (req, res)=>{
		    const bNum = req.params.bNum;
		    console.log("수정 처리", bNum);
		
		    const bTitle = req.body.bTitle;
		    const bName = req.body.bName;
		    const bContent = req.body.bContent;
		    const mId = req.body.mId;
		    const bPw = req.body.bPw;
		    
		    const param = [bTitle, bName, bContent, mId, bPw, bNum];
		    console.log("수정 처리 입력값", param);
		
		    const sql = sqlQuery.boardUpdate;
		    conn.query(sql, param, (err, result, fields)=>{
		        if(err){
		            throw err;
		        }
		        console.log("수정 처리", result);
		        res.redirect("/");
		    });
		});
		
		// 삭제 처리
		app.get("/delete/:bNum", (req, res)=>{
		    const bNum = req.params.bNum;
		    console.log("삭제 처리", bNum);
		    
		    const sql = sqlQuery.boardDelete;
		    conn.query(sql, bNum, (err, result, fields)=>{
		        if(err){
		            throw err;
		        }
		        console.log("삭제 처리", result);
		        res.redirect("/");
		        //res.render("/");
		    });
		});
```
### React
```
	[React]
		페이스북을 개발한 기술로 공개한 소프트웨어
		UI를 위한 자바스크립트 라이브러리
		화면 출력에 특화된 프레임워크(화면 출력 속도 빠름)
	[장점]
		리엑트 컴포넌트는 가상 DOM 을 랜더링
			1. 화면의 일부만 수정되어도 전체를 다시 그리지 않음
			2. 가상 DOM에서 먼저 이전의 화면과 비교해서 차이 나는 부분만 찾아서 그 부분 수정
		컴포넌트 기반
			엘리먼트 : 컴포넌트를 화면상에 띄운 것
	[참고]
		Angular.js : 화면부터 형상관리, 배포까지 포함한 완성형 프레임워크
		React.js : UI에 특화된 프레임워크
		Vue.js : 다른 프레임워크의 장점 흡수하고 단점 보완
	[마운팅]
		리엑트가 처음으로 각 컴포넌트의 render()를 콜해서 자신의 DOM 트리를 구성하는 과정
		마운팅 과정
			생성자 -> render() -> componentDidMount()
	[웹팩]
		기존 웹 문서파일로 변환
		웹 브라우저가 해석할 수 없는 .sass, .cjs 등 .js .css 파일로 변환
		이미지 파일등을 크기를 적절하게 자르거나 묶어주는 역할
	[JSX]
		리액트에서 HTML과 자바스크립트를 함께 사용하고자 확장한 문법
		Javascript XML : A syntax extension to javascript
		[샘플]
			const : 자바스크립트 변수 = html 코드
			const elem = <h1> hello </h1>;
			===================================
			const name = "홍길동";
			const elem = <h1> Hello, {name}</h1>;
	[컴포넌트와 엘리먼트 개념]
		- 붕어빵틀 vs 엘리먼트
		- 클래스 vs 객체
		- 컴포넌트(빈구조) ---> Virtual DOM ---> 브라우저 DOM
		  +
		- 속성		    (react element)   (dom element)
		- 리액트 엘리먼트 특징
			생성되면 변하지 않음
			엘리먼트가 생성 후에는 children이나 attribute 변경 안됨
		props 개념
			- 컴포넌트에서 전달한 데이타 객체
	[테스트]
		https://babeljs.io/docs/
	설치 세팅
		Extensions
			javascript
			eslint
	cmd 관리자 권한 실행
		npm install -g yarn
		npm install -g create-react-app
	visualStudioCode shell 을 cmd로 바꾸고
		create-react-app .
	react 실행
		npm start
		npm run start
	chrom 접속
		확장프로그램 - 검색 - react - 확장 추가
```
### React 컴포넌트 component
```
	index.js
		import React from 'react';
		import ReactDOM from 'react-dom/client';
		import './index.css';
		import reportWebVitals from './reportWebVitals';
		
		//import App from './1_component/App1_class';
		//import App from './1_component/App2_tag';
		import App from './1_component/App3_variable';
		
		const root = ReactDOM.createRoot(document.getElementById('root'));
		root.render(
		  <React.StrictMode>
		    <App />
		  </React.StrictMode>
		);
		
		reportWebVitals();
	App1_class.js
		import { Component } from "react";
		import "../App.css";
		
		// 클래스형 컴포넌트
		class App extends Component {
		    render(){
		        let title = "우리사이트";
		        return(
		            // 리턴안에 작성코드는 JSX 문법
		            // 리턴값이 화면 출력됨
		            // 최상위 태그가 반드시 1개
		            <div className="App">
		                <div className="App-logo">{title}</div>
		            </div>
		        );
		    };
		}
		
		export default App;
	App1_func.js
		import "../App.css";

		// 함수형 컴포넌트
		function App(){
		    let title = "우리사이트22";
		    return(
		        // 리턴안에 작성코드는 JSX 문법
		        // 리턴값이 화면 출력됨
		        // 최상위 태그가 반드시 1개
		        <div className="App">
		            <div className="App-logo">{title}</div>
		        </div>
		    );
		}
		
		export default App;
```
### React 컴포넌트 component
```
	index에서 import만 바꿔주면 됨
		/*
		    리액트의 장점 -> 리액트를 사용하는 이유
		        1. 태그 재사용
		        2. 데이타 바인딩
		*/
		import { render } from "@testing-library/react";
		import "../App.css";
		import { Component } from "react";
		
		// 함수형 컴포넌트
		function MyHeader(){
		    return (
		        <header>
		            <h1 className="App-link"> 우리사이트 </h1>
		            우리는 리액트를 한다
		        </header>
		    )
		}
		
		// 클래스형 컴포넌트
		class MyFooter extends Component{
		    render(){
		        return (
		            <header className="App-logo">
		                <h1> 우리사이트22 </h1>
		                우리는 리액트를 한다22
		            </header>
		        )
		    }; 
		}
		
		function App(){
		    return (
		        <div className="App">
		            <MyHeader></MyHeader>
		            <MyHeader></MyHeader>
		            <MyHeader/>
		            <hr/>
		            <MyFooter/>
		            <MyFooter/>
		        </div>
		    )
		}
		
		export default App;
```
### React {}
```
	index에서 import만 바꿔주면 됨
		import "../App.css";
	
		let message = "감사합니다.";
		
		function msg(){
		    return "오늘도 행복";
		}
		
		let styleA = "App-logo";
		let appLogo = "App-link";
		let app_logo = "App-link";
		//let app-logo = "App-link";
		let styleB = { color:"blue", fontSize:"22px"};
		function App(){
		    return(
		        <div className="App">
		            <h3 className={appLogo}>우리팀화이팅1</h3>
		            <h3 className={app_logo}>우리팀화이팅2</h3>
		            <h3>우리팀화이팅3</h3>
		            <hr/>
		            <h2 className={styleA}> 안녕하세요 </h2>
		            <h2 className={styleA}> {message} </h2>
		            <h3 className={styleA}> { msg() } </h3>
		            <hr/>
		            <h3 style={styleB}>짝꿍님안녕</h3>
		            <h3 style={{ color:"blue", fontSize:"22px"}}>짝꿍님안녕2</h3>
		            <hr/>
		            <img src="logo192.png"></img>
		            <img src="logo512.png"></img>
		        </div>
		    )
		}
		
		export default App;
```
### React props 데이터 이동
```
	import "../App.css"

	function Book(props){
	    console.log(props);
	    return(
	        <div>
	            <h2>제목: {props.title}</h2>
	            <h4>저자: {props.writer}</h4>
	            <h5>가격: {props.price}</h5>
	            {/* 문자열 템플릿 양식으로 */}
	            <h5>{`가격: ${props.price}`}</h5>
	        </div>
	    );
	}
	
	function App(){
	    return(
	        <div className="App">
	            <Book title="자바" writer="김쌤" price="100"></Book>
	            <Book title="파이썬" writer="박쌤" price="200"></Book>
	            <Book title="리엑트" writer="최쌤" price="500"/>
	        </div>
	    )
	}
	
	export default App;
```
### React Button 버튼
```
	import "../App.css";

	function Btn(props){
	    return (
	        <button className={`App-${props.css}`}>{`${props.label}`}</button>
	    )
	}
	
	function Button(){
	    return (
	        <div className="App">
	            <Btn css="link" label="확인"></Btn>
	            <Btn css="logo" label="입장"></Btn>
	        </div>
	    )
	}
	
	export default Button;
```
### React props 데이터 이동
```
	/*
	[props]
	     컴포넌트에 전달된 데이타 객체
	     읽기전용
	     리엑트 컴포넌트의 props 는 바꿀 수 없음
	
	    1 MyHeader 컴포넌트 만들기
	        <header>
	            <h1>여기는 제목</h1>
	            <p>여기는 내용</p>
	        </header>
	    2 App 컴포넌트에서 MyHeader 엘리먼트 2개 생성
	*/
	
	function MyHeader(props){
	    let mytitle = props.title;
	    mytitle = "변경";
	    return(
	        <header>
	            <h1>{`여기는 ${mytitle}`}</h1>
	            <p>{`여기는 ${props.content}`}</p>
	        </header>
	    )
	}
	
	function App2(){
	    return(
	        <div className="App">
	            <MyHeader title="민기" content="짱"></MyHeader>
	            <MyHeader title="민기2" content="짱2"></MyHeader>
	        </div>
	    )
	}
	
	export default App2;
```
### React 버튼 이벤트 button event
```
	import "../App.css";

	function App(){
	    function test(){
	        alert("이벤트 1");
	    }
	
	    return(
	        <div className="App">
	            <button> 이벤트 0 </button><br/>
	            <button onClick={test}> 이벤트 1 </button><br/>
	            <button onClick={()=>{alert("이벤트 2");}}> 이벤트 2 </button><br/>
	            <button onClick={function(){alert("이벤트 3");}}> 이벤트 3 </button><br/>
	        </div>
	    );
	}
	
	export default App;
```
### React 리스트 list
```
	CommentList.jsx
		import React from "react";
		import Comment from "./Comment";
		
		const comments = [
		    {
		        id : "001",
		        name: "홍순이",
		        comment: "안녕하세요",
		        imgname : "imgs/img1.PNG",
		    },
		    {
		        id : "002",
		        name: "홍길동",
		        comment: "오늘도 행복~!",
		        imgname : "imgs/img2.PNG",
		    },
		    {
		        id : "003",
		        name: "박길동",
		        comment: "리액트~ 화이팅!!!!!",
		        imgname : "imgs/img3.PNG",
		    },
		];
		
		function CommentList() {
		    return(
		        <div>
		            {comments.map((c)=>{
		                return(
		                    <Comment key={c.id} name={c.name} comment={c.comment} imgname={c.imgname}/>
		                );    
		            })}
		        </div>
		    )
		}
		
		export default CommentList;
	Comment.jsx
		/* eslint-disable */    // 경고 안 뜨게 하려면 
		import React from "react";
		
		const styles = {
		    wrapper: {
		        margin: 8,
		        padding: 8,
		        display: "flex",
		        flexDirection: "row",
		        border: "1px solid grey",
		        borderRadius: 16,
		    },
		    imageContainer: {},
		    image: {
		        width: 50,
		        height: 50,
		        borderRadius: 25,
		    },
		    contentContainer: {
		        marginLeft: 8,
		        display: "flex",
		        flexDirection: "column",
		        justifyContent: "center",
		    },
		    nameText: {
		        color: "black",
		        fontSize: 16,
		        fontWeight: "bold",
		    },
		    commentText: {
		        color: "black",
		        fontSize: 16,
		    },
		};
		
		function Comment(props) {
		    return(
		        <div style={styles.wrapper}>
		            <div>
		                {/* 이미지 출력 */}
		                <img src={props.imgname} style={styles.image}/>
		            </div>
		            <div style={styles.contentContainer}>
		                <span style={styles.nameText}>{props.name}</span><br/>
		                <span style={styles.commentText}>{props.comment}</span><br/>
		                <span style={styles.image}>{props.imgname}</span><br/>
		            </div>
		        </div>
		    );
		}
		
		export default Comment;
```
### React class state 클래스 스테이트
```
	import { Component } from "react";
	import "../App.css";
	
	// 클래스형 컴포넌트
	/*
	    state : 리엑트에서 컴포넌트에서 변경 가능한 데이타 처리
	        state 변수는 반드시 setState() 함수로 변경이 가능
	*/
	class App extends Component{
	    
	    // 생성자
	    constructor(props){
	        super(props);
	        // 변수 선언
	        this.title = "우리동네 사이트";
	        this.state = { favorite : "맛집" };
	    }
	    render(){
	        return(
	            <div className="App">
	                <h2>클래스형 컴포넌트에서 값 변경</h2>
	                <div className="App-link">{this.title}</div>
	                <button onClick={()=>{
	                    this.title = "너네동네 사이트";
	                    console.log("타이틀", this.title);
	                    //this.forceUpdate();
	                }}>일반변수 값 바꾸기 안됨</button>
	                <hr/>
	                <div className="App-link">{this.state.favorite}</div>
	                <button onClick={()=>{
	                    this.setState({ favorite : "호남식당" });
	                    console.log("식당", this.state.favorite);
	                }}>state 변수 변경</button>
	                <hr/>
	                <hr/>
	                <button onClick={()=>{
	                    this.setState({ favorite : "태국식당" });
	                }}>setState() 함수로 변경</button>
	            </div>
	        );
	    }
	}
	
	export default App;
```
### React function useState 펑션 유즈스테이트
```
	import "../App.css";
	import { useState } from "react";
	
	/*
	    함수형 컴포넌트
	        state : 리엑트 컴포넌트의 변경 가능한 데이터
	            -> state 변경시 useState() 이용
	
	        [참고]
	            useXXXXX() -> hook
	    [예]
	        let [변수명, set변수명] = useState(초기값);
	        let [test, setTest] = useState("테스트"); --> let test = "테스트"; // 변경 가능 (setTest())
	*/
	function App(){
	    // 정적 데이터
	    let title = "우리동네 사이트";
	
	    // 동적 데이터
	    let [favorite, setFavorite] = useState("맛집");
	
	    return(
	        <div className="App">
	            <h2>함수형 컴포넌트에서 state 변경</h2>
	            <div className="App-title">{title}</div>
	            <div className="App-subtitle">{favorite}</div>
	            <hr/>
	            <button onClick={()=>{ title = "너네동네" }}>일반변수 바꾸기</button>
	            <button onClick={()=>{ favorite = "베트남집" }}>state변수 직접바꾸기</button>
	            <button onClick={()=>{ setFavorite("네팔집") }}>setter로 바꾸기</button>
	        </div>
	    );
	}
	
	export default App;
```
### React state, useState 카운트
```
	클래스형
		import { Component } from "react";
		import "../App.css";
		
		class App extends Component{
		
		    constructor(){
		        super();
		        this.state = { num : 0 };
		    }
		    
		    render(){
		        return (
		            <div className="App">
		                <h1>{`값 : ${this.state.num}`}</h1>
		                <button onClick={()=>{
		                    this.setState({num : this.state.num+1});
		                }}>+</button>
		                <button onClick={()=>{
		                    this.setState({num : this.state.num-1});
		                }}>-</button>
		            </div>
		        );
		    } 
		}
		
		export default App;
	함수형
		import { useState } from "react";
		import "../App.css";
		
		function App(){
		    let [num, setNum] = useState(0);
		
		    return (
		        <div className="App">
		            <h1>{`값 : ${num}`}</h1>
		            <button onClick={()=>{
		                setNum(++num);
		            }}>+</button>
		            <button onClick={()=>{
		                setNum(--num);
		            }}>-</button>
		        </div>
		    );
		}
		
		export default App;
```
### React 클래스 컴포넌트 class component mount 함수
```
	클래스형
		import { Component } from "react";
		import "../App.css";
		
		/*
		    - 마운팅(mounting)
		        : 리엑트가 처음으로 각 컴포넌트의 render()를 불러서 자신의 DOM 트리를 구성하는 과정
		    
		*/
		class ClassComp extends Component{
		
		    // 생성자
		    constructor(props){
		        super(props);
		        console.log("-------------0) constructor");
		        this.state = { number : 0 };
		    }
		
		    // 처음 render() 전
		    componentWillMount(){
		        console.log("-------------1) componentWillMount");
		    }
		
		    // 처음 render() 후
		    componentDidMount(){
		        console.log("-------------2) componentDidMount");
		    }
		
		    // 화면 바뀔 때
		    shouldComponentUpdate(nextPros, nextState){
		        console.log("-------------3) shouldComponentUpdate");
		        return true;
		    }
		
		    // 바뀔 때 render() 전
		    componentWillUpdate(nextPros, nextState){
		        console.log("-------------4) componentWillUpdate");
		    }
		
		    // 바뀔 때 render() 후
		    componentDidUpdate(nextPros, nextState){
		        console.log("-------------5) componentDidUpdate");
		    }
		
		    // 렌더
		    render(){
		        console.log("-------------X) render");
		        return (
		            <div className="App">
		                <h2>클래스 컴포넌트</h2>
		                <div className="App-title">
		                    {this.state.number}
		                </div>
		                <input type="button" value="눌러" onClick={()=>{this.setState({ number : Math.round(Math.random()*100) })}}></input>
		            </div>
		        );
		    }
		}
		
		function App(){
		    return (
		        <div>
		            <ClassComp></ClassComp>
		        </div>
		    );
		}
		
		export default App;
```
### React 함수 컴포넌트 function component useEffect 함수
```
	함수형
		import "../App.css";
		import { useEffect, useState } from "react";
		
		function FuncComp(props){
		    let [number, setNumber] = useState(0);	
		    /*
		        클래스 컴포넌트에서 
		            componentDidMount()
		            componentDidUpdate()
		            componentWillUnmount()
		        3개를 합친 효과 함수가 있다.
		        useEffect();
		    */
		    useEffect(function(){
		        console.log("useEffect()");
		    });
		
		    return (
		        <div>
		            <h2>함수 컴포넌트</h2>
		            <p>숫자 : {number}</p>
		            <input type="button" value="눌러1" 
		                onClick={()=>{
		                    setNumber( Math.round(Math.random()*100) );
		                }}
		            ></input>
		            <hr/>
		            <input type="button" value="눌러2"
		                onClick={ function(){
		                    setNumber( Math.round(Math.random()*100) );
		                }}
		            ></input>
		        </div>
		    );
		}
		
		function App(){
		    return (
		        <div className="App">
		            <FuncComp></FuncComp>
		        </div>
		    );
		}
		
		export default App;
```
### React 함수 컴포넌트 function component useEffect 함수
```
	import { useEffect, useState } from "react";

	/*
	    [ hook ]
	        1> 무조건 최상의 레벨에서만 호출
	            -> 반복문이나 조건문, 중첩함수 안에서 호출하면 안됨
	        2> 함수형 컴포넌트에서만 호출
	            -> 일반 자바스크립트 함수에서는 호출하면 안됨
	    
	    [0] useState()
	    [1] useEffect()
	        클래스 컴포넌트에서 사용하던 생명주기 함수의 기능을 대신 수행
	        componentDidMount() / componentDidUpdate() / componentWillUnmount()
	    * useEffect( 이벤트함수, 의존성배열 );
	        배열 안에 있는 변수 중에서 하나라도 값이 변경되면 이벤트함수 실행
	        의존성배열이 없는 경우는 DOM 변경된 이후에 함수를 실행
	    의존성 배열이 없는 경우
	        컴포넌트가 업데이트될 때마다 실행
	    의존성 배열이 있는 경우
	        배열의 값이 변경될 때마다 실행
	    의존성 배열이 [] 빈 배열인 경우
	        처음에만 실행    
	*/
	function Form(){
	    const [realName, setRealName] = useState("ㄲ");
	    const [nickName, setNickName] = useState("ㄴ");
	    
	    useEffect(()=>{
	        console.log(`본명: ${realName} \t 별명: ${nickName}`);
	    }, []);
	
	    return (
	        <div>
	            <div>
	                <span>본명 :</span>
	                <input type="text" value={realName} onChange={(event)=>{
	                    setRealName(event.target.value);
	                }}></input>
	            </div>
	            <div>
	                <span>별명 :</span>
	                <input type="text" value={nickName} onChange={(event)=>{
	                    setNickName(event.target.value);
	                }}></input>
	            </div>
	        </div>
	    );
	}
	
	function App(){
	    return <Form/>
	}
	
	export default App;
```
### React 함수 컴포넌트 function component useEffect 함수
```
	import { useEffect, useState } from "react";

	/*
	    [ hook ]
	        1> 무조건 최상의 레벨에서만 호출
	            -> 반복문이나 조건문, 중첩함수 안에서 호출하면 안됨
	        2> 함수형 컴포넌트에서만 호출
	            -> 일반 자바스크립트 함수에서는 호출하면 안됨
	    
	    [0] useState()
	    [1] useEffect()
	        클래스 컴포넌트에서 사용하던 생명주기 함수의 기능을 대신 수행
	        componentDidMount() / componentDidUpdate() / componentWillUnmount()
	    * useEffect( 이벤트함수, 의존성배열 );
	        배열 안에 있는 변수 중에서 하나라도 값이 변경되면 이벤트함수 실행
	        의존성배열이 없는 경우는 DOM 변경된 이후에 함수를 실행
	    의존성 배열이 없는 경우
	        컴포넌트가 업데이트될 때마다 실행
	    의존성 배열이 있는 경우
	        배열의 값이 변경될 때마다 실행
	    의존성 배열이 [] 빈 배열인 경우
	        처음에만 실행    
	*/
	function Form(){
	    const [realName, setRealName] = useState("ㄲ");
	    const [nickName, setNickName] = useState("ㄴ");
	    
	    useEffect(()=>{
	        console.log(`Form 컴포넌트 마운트`);
	        console.log(`본명: ${realName} \t 별명: ${nickName}`);
	
	        // unmount : 화면에서 없어졌을 때 동작 하는 return
	        return ()=>{
	            console.log(`--------> Form 컴포넌트 언마운트`);
	        };
	    }); // 이쪽에 배열이 있냐 없냐로 기능이 다름
	
	    return (
	        <div>
	            <div>
	                <span>본명 :</span>
	                <input type="text" value={realName} onChange={(event)=>{
	                    setRealName(event.target.value);
	                }}></input>
	            </div>
	            <div>
	                <span>별명 :</span>
	                <input type="text" value={nickName} onChange={(event)=>{
	                    setNickName(event.target.value);
	                }}></input>
	            </div>
	        </div>
	    );
	}
	
	function App(){
	    const [isVisible, setIsVisible] = useState(true);
	
	    return (
	        <div>
	            <button onClick={()=>{
	                setIsVisible(!isVisible);
	            }}>{isVisible ? "숨기기" : "보이기"}</button>
	            <hr/>
	            {isVisible && <Form/>}
	        </div>
	    );
	}
	
	export default App;
```
### React 함수 컴포넌트 function component useMemo 함수
```
	/*
	    useMemo
	        - 지정된 값에 변화가 있을 때만 함수 실행
	    
	    useMemo(func, []);
	*/
	
	import { useMemo, useState } from "react";
	
	const getAverage = (nums) => {
	    console.log("계산중", nums);
	    if(nums.length === 0){
	        return 0;
	    }
	
	    const sum = nums.reduce((a,b) => a+b);
	    console.log(sum);
	    return sum / nums.length;
	};
	
	// function Average(){};
	const Average = ()=>{
	
	    const [num, setNum] = useState("");
	    const [list, setList] = useState([]);
	
	    const onChange = (event) => {
	        setNum(event.target.value);
	    };
	
	    const onInsert = () => {
	        const newList = list.concat(parseInt(num));
	        setList(newList); 
	        setNum("");
	    };
	
	    const avg = useMemo(()=>getAverage(list), [list]);
	
	    return (
	        <div>
	            <input type="text" value={num} onChange={onChange}></input>
	            <button onClick={onInsert}>등록</button>
	            <hr/>
	            <ul>
	                {
	                    list.map((value, i)=>{
	                        return <li key={i}>{value}</li>
	                    })
	                }
	            </ul>
	            <div>
	                {/* 평균값 : { getAverage(list) } */}
	                평균값 : {avg}
	            </div>
	        </div>
	    );
	};
	
	const App = ()=>{
	    return <Average/>
	};
	
	export default App;
```
### React 함수 컴포넌트 function component useRef 함수
```
	const inputEL = useRef(null); // 1111111111111111111111111111111111111 변수
	<input type="text" value={num} onChange={onChange} ref={inputEL}></input>  {/* 222222222222222222222 포커스 주고싶은 곳 ref 지정 */}
	inputEL.current.focus(); // 333333333333333333 이거 다음 input 태그로 포커스 지정
```
### React 함수 컴포넌트 function component useRef 함수 form
```
	import { useRef, useState } from "react";
	import "../App.css";
	
	const App = () => {
	    // 입력 값들
	    const [formData, setFormData] = useState({ userId : "", userName : "" }); 
	
	    // 입력 값들 저장
	    const [data, setData] = useState({
	        array : [],
	        uselessValue : null
	    });
	
	    // 입력 값들 저장 번호
	    const nextId = useRef(1);
	
	    // 입력 값이 바뀔 때
	    const onChange = (evt) => {
	        const { name, value} = evt.target;
	        //console.log(name, " : ", value);
	        setFormData({...formData, [name] : [value]});
	        console.log(formData);
	    };
	
	    // 등록 버튼 클릭
	    const onSubmit = (evt) => {
	        evt.preventDefault();
	        const info = {
	            id : nextId.current,
	            userId : formData.userId,
	            userName : formData.userName
	        };
	
	        nextId.current += 1;
	
	        setData( {...data, array : data.array.concat(info)} );
	        setFormData({ userId : "", userName : "" });
	    };
	
	    // 항목 삭제함수
	    const onRemove = (id) => {
	        alert(id);
	        setData({ ...data,
	            array : data.array.filter((info)=>{
	                return info.id !== id;
	            })
	         });
	    };
	
	    return (
	        <div>
	            <form onSubmit={onSubmit}>
	                <input type="text" name="userId" placeholder="아이디" onChange={onChange} value={formData.userId}></input><br/>
	                <input type="text" name="userName" placeholder="이름" onChange={onChange} value={formData.userName}></input><br/>
	                <button type="submit">등록</button>
	            </form>
	            <hr/><hr/>
	            <div>
	                <ul>
	                    {
	                        data.array.map((info)=>{
	                            return <li key={info.id} onClick={()=>{
	                                onRemove(info.id);
	                            }}>{info.userId} : {info.userName}</li>        
	                        })
	                    }
	                </ul>
	            </div>
	        </div>
	    );
	};
	
	export default App;
```
### React useRef() 함수 비제어컴포넌트
```
	import { useRef, useState } from "react";

	const App = () => {
	    const [result, setResult] = useState(0);
	
	    // HTMLDOM 접근 useRef
	    const elemX = useRef(null);
	    const elemY = useRef(null);
	
	    const add = () => {
	        console.log(elemX.current.value);
	        console.log(elemY.current.value);
	        let x1 = parseInt(elemX.current.value);
	        let y1 = parseInt(elemY.current.value);
	        setResult(x1+y1);
	    }
	
	    return (
	        <div>
	            <h2>비제어컴포넌트</h2>
	            X값 : <input type="text" ref={elemX}></input>
	            <br/>
	            Y값 : <input type="text" ref={elemY}></input>
	            <hr/>
	            <button onClick={add}>계산하기</button>
	            결과 : {result}
	        </div>
	    );
	}
	
	export default App;
```
### React useReducer() 함수
```
	/*
	    useReducer
	        리듀서는 현재상태(state) 와 액션(action) 값을 전달받아 새로운 상태를 반환하는 함수
	    function reducer(state, action){
	        return {....};
	        // 반환하는 새로운 상태는 불변성을 가짐
	    }
	    
	    dispatch(action) : 리듀서 함수 호출
	*/
	
	import { useReducer } from "react";
	
	// 리듀서 함수
	function reducer(state, action){
	    switch(action.type){
	        case "ADD" : {
	            return {value : state.value + 1};
	        }
	        case "MINUS" : {
	            return {value : (state.value > 0) ? state.value - 1 : 0};
	        }
	        default : {
	            return state;
	        } 
	    }
	}
	
	// 카운터 컴포넌트
	const Counter = ()=>{
	
	    // useReducer()
	    const [state, dispatch] = useReducer(reducer, {value : 0});
	
	    return (
	        <div>
	            <h2> 값: {state.value}</h2>
	            <hr/>
	            <button onClick={()=>{
	                dispatch({type : "ADD"});
	            }}>+</button>
	            <button onClick={()=>{
	                dispatch({type : ""});
	            }}>=======</button>
	            <button onClick={()=>{
	                dispatch({type : "MINUS"});
	            }}>-</button>
	        </div>
	    );
	}
	
	export default Counter;
```
### React useHook 훅 만들기
```
	import { useEffect, useState } from "react";

	// 사용자 hook
	function useCounter(initValue){
	    // count 변수
	    const [count, setCount] = useState(initValue);
	
	    // increase 함수
	    const increase = () => setCount(count => count+1);
	
	    // decrease 함수
	    const decrease = () => setCount(count => Math.max(count-1, 0));
	
	    return [count, increase, decrease];
	}
	
	const MAX_CAPACITY = 5;
	
	function Room(props){
	
	    const [count, increase, decrease] = useCounter(0);
	
	    const [isFull, setIsFull] = useState(false);
	
	    // 값이 변경될 때마다
	    useEffect(()=>{
	        setIsFull(count >= MAX_CAPACITY);
	    }, [count]);
	
	    return (
	        <div style={{padding : 16}}>
	            <p>{`총 ${count}명 입실`}</p>
	            {!isFull && <button onClick={increase}>입장</button>}
	            <button onClick={decrease}>퇴실</button>
	            <hr/>
	            { isFull && <p style={{color : "red"}}>정원이 가득 찼습니다.</p>}
	        </div>
	    );
	}
	
	export default Room;
```
### React props 함수 이동
```
	// props 함수 이동 
	import { useState } from "react";
	
	function LoginBtn(props){
	    return (
	        <div>
	            <button onClick={props.onClick}>로그인</button>
	        </div>
	    );
	}
	
	function LogoutBtn(props){
	    return (
	        <div>
	            <button onClick={props.onClick}>로그아웃</button>
	        </div>
	    );
	}
	
	function LoginControl(props){
	    const [isLogged, setIsLogged] = useState(false);
	    let button;
	
	    if(isLogged){
	        button = <LogoutBtn onClick={ ()=>{ setIsLogged(false) }}/>
	    }else{
	        button = <LoginBtn onClick={ ()=>{ setIsLogged(true) }}/>
	    }
	
	    return (
	        <div>
	            {button}
	        </div>
	    );
	}
	
	function App(){
	    return (
	        <div>
	            <LoginControl/>
	        </div>
	    );
	}
	
	export default App;
```
### React render stop 컴포넌트 렌더링 막기
```
	/*
	    컴포넌트 렌더링 막기
	        return null;
	*/
	
	import { useState } from "react";
	
	// return null 일 경우 Banner 가 화면에 출력되지 않는다
	function Banner(props){
	    if( !props.show ){
	        return null; 
	    }
	
	    return (
	        <div>광고</div>
	    );
	}
	
	function MainPage(){
	    const [show, setShow] = useState(false);
	
	    const toggleHandler = () => {
	        setShow(!show);
	    }
	
	    return (
	        <div>
	            <Banner show={show}/>
	            <hr/>
	            {/* show 값 true 일땐 false로 바꿔주고 show 값 false 일땐 true로 바꿔준다 */}
	            <button onClick={()=>{ setShow(!show); }}>{ show ? "감추기" : "보이기" }</button>
	            <br/><br/>
	            <button onClick={toggleHandler}>{ show ? "감추기2" : "보이기2" }</button>
	        </div>
	    );
	}
	
	function App(){
	    return (
	        <div>
	            <MainPage/>
	        </div>
	    );
	}
	
	export default App;
```
### React Form 폼
```
	import { useState } from "react";

	function My_form(props){
	    let [name, setName] = useState("");
	    let [message, setMessage] = useState("");
	    let [trevel, setTrevel] = useState("");
	    let [gender, setGender] = useState("");
	
	    const formSubmit = (evt) => {
	        evt.preventDefault();
	        let formData = `이름은: ${name}
	                        메세지: ${message}
	                        여행지: ${trevel}
	                        성별 : ${gender}`;
	        alert(formData);
	    }
	
	    return(
	        <div>
	            <form onSubmit={formSubmit}>
	                <button type="submit">전송</button>
	                <hr/>
	                <label>이름</label>
	                <input type="text" onChange={(evt)=> setName(evt.target.value)} value={name}/><br/>
	                <label>메세지</label>
	                <textarea cols={20} rows={2} onChange={(evt)=> setMessage(evt.target.value)}>{message}</textarea><br/>
	                <label>여행 갈 나라는?</label>
	                <select onChange={(evt)=>setTrevel(evt.target.value)}>
	                    <option>외국</option>
	                    <option>한국</option>
	                    <option>부탄</option>
	                    <option>옆나라</option>
	                </select><br/>
	                <label>성별</label>
	                <input type="radio" name="gender" value="남자" onChange={(evt)=>setGender(evt.target.value)} checked/>남자
	                <input type="radio" name="gender" value="여자" onChange={(evt)=>setGender(evt.target.value)}/>여자
	            </form>
	        </div>
	    );
	}
	
	function App(){
	    return <My_form/>
	}
	
	export default App;
```
### React 부모 자식 containment
```
	import { useState } from "react";
	import "./temp.css";
	
	function FancyBorder(props){
	    return (
	        <div className="FancyBorder">
	            {props.children}
	        </div>
	    );
	}
	
	function TextPart(props){
	    return (
	        <FancyBorder>
	            <h1 className="Dialog-title">{props.title}</h1>
	            <p className="Dialog-message">{props.message}</p>
	            {props.children}
	        </FancyBorder>
	    );
	}
	
	function WelcomeDialog(props){
	    return (
	        <TextPart title="환영합니다" message="당신은 행운~~~~~"/>
	    );
	}
	
	function MorningDialog(props){
	    let [nickName, setNickName] = useState("");
	
	    return (
	        <div>
	            <TextPart title="좋은아침" message="행운행운">
	                <label>별명: </label>
	                <input type="text" value={nickName} onChange={(evt)=>setNickName(evt.target.value)}></input><br/>
	                <button onClick={(evt)=>{alert(`어서오세요 ${nickName}`);}}>등록</button>
	            </TextPart>
	        </div>
	    );
	}
	
	function App(){
	    return (
	        <div>
	            <WelcomeDialog/>
	            <hr/>
	            <MorningDialog/>
	        </div>
	    );
	}
	
	export default App;
```
### React immer 불변성 라이브러리
```
	import { useState } from "react";
	import produce from "immer";
	
	// immer : 불변성 라이브러리
	const App = () => {
	
	    const [todo, setTodo] = useState([
	        {item : "밥먹기", done : true},
	        {item : "잠자기", done : false},
	        {item : "놀기", done : true}
	    ]);
	
	    const listData = () => {
	        console.log("0>", todo);
	    }
	
	    // 2번째 item을 "공부하기" 로 수정
	    const modifyData1 = () => {
	        setTodo(()=>{
	            return todo[2].item = "공부하기";
	        });
	    }
	
	    const modifyData2 = () => {
	        const temp = todo.map((data, idx)=>{
	            return (idx === 2) ? {...data, item : "공부하기2"} : data;
	        });
	        setTodo(temp);
	    }
	
	    const modifyData3 = () => {
	        const temp = produce(todo, (data)=>{
	            data[2].item = "공부하기3";
	        });
	        setTodo(temp);
	    }
	
	    return (
	        <div>
	            <button onClick={listData}>확인</button>
	            <hr/>
	            <button onClick={modifyData1}>수정1</button><br/>
	            <button onClick={modifyData2}>수정2</button><br/>
	            <button onClick={modifyData3}>수정3</button><br/>
	        </div>
	    );
	}
	
	export default App;
```
### React immer 불변성 라이브러리
```
	import { useState } from "react";
	import produce from "immer";
	
	const App = () => {
	
	    let [student, setStudent] = useState([{
	        names : ["홍길동", "박길동", "한길동"],
	        major : [
	            { dept : "컴공", title : "자바", score : 3 },
	            { dept : "소공", title : "파이썬", score : 2 },
	            { dept : "컴공", title : "리엑트", score : 1 },
	            { dept : "컴공", title : "스프링", score : 3 }
	        ]
	    }]);
	
	    const handleList = () => {
	        console.log("확인: ", student);
	    }
	
	    /*
	        일반방식 버튼을 클릭하면 '리엑트' 대신에 'DB' 로 변경
	        immer 방식 버튼을 클릭하면 '리엑트' 대신에 'ES6' 으로 변경
	    */
	    const normalBtn = () => {
	        const temp = student.map((data, idx)=>{
	            return {
	                ...data,
	                major: data.major.map(major => 
	                    major.title === "리엑트" ? { ...major, title: "DB" } : major
	                )
	            }
	        });
	        setStudent(temp);
	    }
	
	    const immerBtn = () => {
	        const temp = produce(student, (data)=>{
	            data[0].major[2].title = "DB";
	        });
	        setStudent(temp);
	    }
	
	    return (
	        <div>
	            <button onClick={handleList}>확인</button>
	            <hr/>
	            <button onClick={normalBtn}>일반</button>
	            <br/>
	            <button onClick={immerBtn}>immer</button>
	        </div>
	    );
	}
	
	export default App;
```
### React immer 불변성 라이브러리
```
	import { useRef, useState } from "react";
	import "../App.css";
	import produce from "immer";
	
	const App = () => {
	    // 입력 값들
	    const [formData, setFormData] = useState({ userId : "", userName : "" }); 
	
	    // 입력 값들 저장
	    const [data, setData] = useState({
	        array : [],
	        uselessValue : null
	    });
	
	    // 입력 값들 저장 번호
	    const nextId = useRef(1);
	
	    // 입력 값이 바뀔 때
	    const onChange = (evt) => {
	        const { name, value} = evt.target;
	        //console.log(name, " : ", value);
	        //setFormData({...formData, [name] : [value]});
	        setFormData(produce(formData, draft => {draft[name] = value;} ));
	    }
	
	    // 등록 버튼 클릭
	    const onSubmit = (evt) => {
	        evt.preventDefault();
	        const info = {
	            id : nextId.current,
	            userId : formData.userId,
	            userName : formData.userName
	        };
	
	        nextId.current += 1;
	
	        // setData( {...data, array : data.array.concat(info)} );
	        // setFormData({ userId : "", userName : "" });
	
	        setData(produce(data, draft => {
	            draft.array.push(info);
	        }));
	    };
	
	    // 항목 삭제함수
	    const onRemove = (id) => {
	        // alert(id);
	        // setData({ ...data,
	        //     array : data.array.filter((info)=>{
	        //         return info.id !== id;
	        //     })
	        //  });
	        setData(produce(data, (draft)=>{
	            draft.array.splice(draft.array.findIndex( info => info.id===id), 1);
	        }));
	
	    };
	
	    return (
	        <div>
	            <form onSubmit={onSubmit}>
	                <input type="text" name="userId" placeholder="아이디" onChange={onChange} value={formData.userId}></input><br/>
	                <input type="text" name="userName" placeholder="이름" onChange={onChange} value={formData.userName}></input><br/>
	                <button type="submit">등록</button>
	            </form>
	            <hr/><hr/>
	            <div>
	                <ul>
	                    {
	                        data.array.map((info)=>{
	                            return <li key={info.id} onClick={()=>{
	                                onRemove(info.id);
	                            }}>{info.userId} : {info.userName}</li>        
	                        })
	                    }
	                </ul>
	            </div>
	        </div>
	    );
	};
	
	export default App;
```
### React route 화면
```
	설치
		npm install react-router-dom
	App.js
		import "../App.css";
		import Home from "./pages/Home";
		import First from "./pages/First";
		import Second from "./pages/Second";
		import Menu from "./pages/Menu";
		
		// 여러개 받아올 때 {} 필요
		import {
		    BrowserRouter,
		    Routes,
		    Route
		} from "react-router-dom";
		import { useState } from "react";
		import Third from "./pages/Third";
		import Fourth from "./pages/Fourth";
		
		function App(){
		
		    const [data, setData] = useState([
		        { title : "영화0", img : "movie0.jpg"},
		        { title : "영화1", img : "movie1.jpg"},
		        { title : "영화2", img : "movie2.jpg"},
		        { title : "영화3", img : "movie3.jpg"},
		        { title : "영화4", img : "movie4.jpg"},
		        { title : "영화5", img : "movie5.jpg"}
		    ]);
		
		    return (
		        <div className="App">
		            <BrowserRouter>
		            <Menu/>
		                <Routes>
		                    {/* 어떤 경로에 어떤 엘리먼트를 연결할건지 */}
		                    <Route path="/" element={<Home/>}/>
		                    <Route path="/first" element={<First msg="리엑트 세계에 오신것을 환영합니다."/>}/>
		                    <Route path="/second" element={<Second msg="리엑트 만세"/>}/>
		                    <Route path="/third/*" element={<Third datas={data}/>}></Route>
		                    <Route path="/Fourth/:idx/:name" element={<Fourth datas={data}/>}></Route>
		                </Routes>
		            </BrowserRouter>
		        </div>
		    );
		}
		
		export default App;
```
### React route 화면
```
	Menu.js
		import { Link } from "react-router-dom";
		import "./Menu.css";
		
		const Menu = (props) => {
		    return (
		        <div className="nav">
		            <Link to={"/"}>홈</Link>            
		            <Link to={"/first"}>첫번째</Link>
		            <Link to={"/second"}>두번째</Link>
		            <Link to={"/Third"}>세번째</Link>
		        </div>
		    );
		}
		
		export default Menu;
	First.js
		const First = (props) => {
		    return (
		        <div>
		            여기는 First 페이지입니다.
		            <hr/>
		            {props.msg}
		        </div>
		    );
		}
		
		export default First;
	Second.js
		const Second = (props) => {
		    return (
		        <div>
		            여기는 Second 페이지입니다.
		            <hr/>
		            {props.msg}
		        </div>
		    );
		}
		
		export default Second;
	Third.js
		import { Link } from "react-router-dom";

		const Third = (props) => {
		
		    //console.log(props.datas);
		    let list = props.datas.map((data,idx)=>{
		    console.log(`imgs/${data.img}`);
		        return (
		            <div key={idx}>
		                <img src={`/imgs/${data.img}`}></img>
		                <br/>
		                <h3>{data.title}</h3>
		                {/* 링크는 <a>태그 대신 <Link> */}
		                <Link to={`/fourth/${idx}/${data.title}`} style={{TextDecoder : "none"}}>
		                    {data.title}
		                </Link>
		            </div>
		        );
		    });
		
		    return (
		        <div>
		            여기는 세번째 페이지입니다.
		            <hr/>
		            <div>
		                <ul>
		                    {
		                        list
		                    }
		                </ul>
		            </div>
		        </div>
		    );
		}
		
		export default Third;
	Fourth.js
		import { useParams } from "react-router-dom";

		const Fourth = (props) => {
		    
		    //console.log(props.datas);
		
		    const {idx, name} = useParams();
		
		    return (
		        <div>
		            여기는 네번째 페이지입니다.
		            <hr/>
		            <div>
		                <div>{idx} : [ {name} ]</div>
		                <img src={`/imgs/${props.datas[idx].img}`}></img>
		            </div>
		        </div>
		    );
		}
		
		export default Fourth;
```
### React fetch
```
	import { useEffect, useState } from "react";
	import "../App.css";
	
	const App = () => {
	    const [temp, setTemp] = useState("");
	    const [humidity, setHumidity] = useState("");
	    const [weather, setWeather] = useState("");
	    const [isReady, setIsReady] = useState(false);
	
	    useEffect(()=>{
	        getData();
	
	        // 다른 작업이 있는 경우
	
	    }, []);
	
	    const getData = async () => {
	        await fetch("https://api.openweathermap.org/data/2.5/weather?q=Seoul,KR&appid=1db47184ebbc18af53fd996be840d270")
	        .then( result => result.json())
	        .then(jsonResult => {
	            setTemp(jsonResult.main.temp);
	            setHumidity(jsonResult.main.humidity);
	            setWeather(jsonResult.weather[0].main);
	
	            // 준비 끝
	            setIsReady(true);
	        });
	    }
	
	    if(isReady){
	        return (
	            <div className="App">
	                <p>온도 : {temp}</p>
	                <p>습도 : {humidity}</p>
	                <p>날씨 : {weather}</p>
	            </div>
	        );
	    }else{
	        return (
	            <div className="App">
	                로딩중.....
	            </div>
	        );
	    }
	}
	
	export default App;
```
### React axios
```
	설치
		npm install axios
	weather.js
		import { useEffect, useState } from "react";
		import "../App.css";
		
		import axios from "axios";
		
		const App = () => {
		    const [temp, setTemp] = useState("");
		    const [humidity, setHumidity] = useState("");
		    const [weather, setWeather] = useState("");
		    const [isReady, setIsReady] = useState(false);
		
		    useEffect(()=>{
		        getData();
		
		        // 다른 작업이 있는 경우
		
		    }, []);
		
		    const getData = async () => {
		        await axios.get("https://api.openweathermap.org/data/2.5/weather?q=Seoul,KR&appid=1db47184ebbc18af53fd996be840d270")
		        .then(jsonResult => {
		            setTemp(jsonResult.data.main.temp);
		            setHumidity(jsonResult.data.main.humidity);
		            setWeather(jsonResult.data.weather[0].main);
		
		            // 준비 끝
		            setIsReady(true);
		        });
		    }
		
		    if(isReady){
		        return (
		            <div className="App">
		                <p>온도 : {temp}</p>
		                <p>습도 : {humidity}</p>
		                <p>날씨 : {weather}</p>
		            </div>
		        );
		    }else{
		        return (
		            <div className="App">
		                로딩중.....
		            </div>
		        );
		    }
		}
		
		export default App;
```
### React axios
```
	App.js
		import { useEffect, useState } from "react";
		import axios from "axios";
		import Movie from "./components/Movie";
		
		function App(){
		    const [isLoading, setIsLoading] = useState(true);
		    const [movies, setMovies] = useState([]);
		
		    useEffect(()=>{
		        getMovies();
		    }, []);
		
		    const getMovies = async () => {
		        await axios.get("https://yts.mx/api/v2/list_movies.json")
		        .then(result => {
		            console.log();
		            setMovies(result.data.data.movies)
		            setIsLoading(false);
		        })
		        .catch( err => console.log("ERROR", err));
		    }
		
		    return (
		        <div>
		            { isLoading ? "로딩중" : 
		                movies.map((movie, idx)=>{
		                    return (
		                        <Movie
		                            key={movie.id}
		                            id={movie.id}
		                            year={movie.year}
		                            title={movie.title}
		                            summary={movie.summary}
		                            poster={movie.medium_cover_image}
		                            genres={movie.genres}
		                        />
		                    );
		                })
		            }
		        </div>
		    );
		}
		
		export default App;
	Movie.js
		const Movie = ({ title, year, summary, poster, genres }) => {
			return (
				<div>
				    <img src={poster} title={title}></img>
				    <div>
					<h3>{title}</h3>
					<h5>{year}</h5>
					<p>{summary}</p>
					<p>{genres}</p>
				    </div>
				</div>
			);
		}
		
		export default Movie;
```
### React 연동 node.js mysql
```
	설치
		back
			npm install express cors mysql nodemon
		front
			create-react-app .
			npm install axios
	// server_start.js
		D:\xWork\react\5_node_mysql\back>

		const express = require('express');
		const cors = require('cors');
		const mysql = require('mysql');
		const dbconfig = require('./config/database.js');
		const conn = mysql.createConnection(dbconfig);
		const app = express();
		// Express에서 정적파일 제공
		// app.use('/static', express.static('static'));
		
		const PORT = 8000
		app.listen(PORT, () => {
			console.log("Express 서버 시작 포트는 >>> : ", PORT)
		});
		
		// [1] 실행확인
		//		node  server_start.js
		// =========================================================
		
		
		// [2] 디비연결확인
		conn.connect( err => {
			if(err) console.log("연결실패: ", err)
			console.log('연결성공')
		})
		
		// =========================================================
		// 다른 주소와 데이타를 주고 받기 위해
		app.use(cors()) // *********************
		
		// [3] 전체 조회
		app.get('/api/get', (req, res) => {
			// const sql =   " SELECT 	BNUM, BTITLE, BNAME, "
			// 			+ " 		BCONTENT, MID, BPW, "
			// 			+ " 		DATE_FORMAT(INSERTDATE,'%Y-%m-%d') INSERTDATE,"
			// 			+ " 		DATE_FORMAT(UPDATEDATE,'%Y-%m-%d') UPDATEDATE " 
			// 			+ " FROM 	NODE_BOARD ";
			// 화면에 출력할 내용만 검색
			// 여기서 대문자로 컬럼명을 지정하면 화면에서도 대문자로 지정해야 한다
			const sql =   " SELECT 	BNUM, BTITLE, BNAME, MID "
						+ " FROM 	NODE_BOARD ";
			conn.query(sql, function(err, result, fields) {
				if (err) throw err;		
				console.log(result);
				res.send(result);
				// [브라우저 확인] http://localhost:8000/api/get	
			});
		});
		
		// =========================================================
		// [4] 입력 화면 
		
		// json 객체로 주고받기 위해?
		// app.use(cors()) - 위에 코드함
		app.use(express.json())  // *********************
		
		app.post('/api/insert', (req, res) => {
			console.log(req.body)
			const btitle = req.body.btitle;
			const bname = req.body.bname; 
			const bcontent = req.body.bcontent; 
			const mid = req.body.mid; 
			const bpw = req.body.bpw; 
			const param = [btitle, bname, bcontent, mid, bpw];
			const sql =   " INSERT INTO node_board (BTITLE, BNAME, BCONTENT, MID, BPW, INSERTDATE, UPDATEDATE) " 
			            + " VALUES (?, ?, ?, ?, ?, now(), now()) ";
			conn.query(sql, param,function(err, result, fields){
				if (err) throw err;
				console.log(result);	
				res.send('success')	;
			});
		});
		
		
		// ==================================================
		// [5] 삭제
		app.delete('/api/delete/:bnum', (req, res) => {
			const sql = "DELETE FROM  node_board WHERE bnum = ? ";
			conn.query(sql, [req.params.bnum], (err, result, fields) => {
				if (err) throw err;
				console.log('delete:' + req.params.bnum)
				console.log(result);
				res.send('success')
			});
		});
		
		// 조회
		// app.get('/edit/:bnum', (req, res) => {
		// 	const sql =   " SELECT 	BNUM, BTITLE, BNAME, "
		// 				+ " 		BCONTENT, MID, BPW, "
		// 				+ " 		DATE_FORMAT(INSERTDATE,'%Y-%m-%d') INSERTDATE,"
		// 				+ " 		DATE_FORMAT(UPDATEDATE,'%Y-%m-%d') UPDATEDATE " 
		// 				+ " FROM 	node_board "
		// 				+ " WHERE 	BNUM = ? " ;	
		// 	const bnum = req.params.bnum;	
		// 	console.log("bnum >>> : " + bnum);						
		// 	conn.query(sql, [bnum], (err, result, fields) => {
		// 		if (err) throw err;
		// 		console.log("조회 >>> : ", result);
		// 		res.render('board_edit', {users: result});
		// 	});
		// });
		
		// 수정
		// app.post('/update/:bnum', (req, res) => {	
		// 	const bnum = req.body.bnum;
		// 	const btitle = req.body.btitle; 
		// 	const bname = req.body.bname; 
		// 	const bcontent = req.body.bcontent; 
		// 	const sql =     " UPDATE node_board SET btitle = ?, bname = ?, bcontent = ?, UPDATEDATE=now() WHERE bnum = ? " ;
		// 	conn.query(sql, [btitle, bname, bcontent, bnum], (err, result, fields) => {
		// 		if (err) throw err;
		// 		console.log(result);
		// 		res.redirect('/');
		// 	});
		// });
	boardSample.js
		D:\xWork\react\5_node_mysql\front>

		import '../css/board.css'
		import axios from "axios";
		import { useEffect, useState } from 'react';
		
		function App(){
		    // 목록보기 변수
		    const [viewContent, setViewContent] = useState([]);
		
		    useEffect(()=>{
		        boardList();
		    }, []);
		
		    const boardList = async () => {
		        await axios.get("http://localhost:8000/api/get")
		        .then((res)=>{
		            setViewContent(res.data);
		        });
		    }
		
		    // 입력 함수
		    const insertBoard = () => {
		        axios.post("http://localhost:8000/api/insert", {
		            btitle : boardContent.btitle,
		            bname : boardContent.bname,
		            bcontent : boardContent.bcontent,
		            mid : boardContent.mid,
		            bpw : boardContent.bpw
		        })
		        .then((res)=>{
		            console.log(res);
		            boardList();
		        });
		    }
		
		    // [1-2] useState로 상태값 지정
		    const [boardContent, setBoardContent] = useState({
		        btitle : '',
		        bname : '',
		        mid : '',
		        bpw : '',
		        bcontent : ''
		    })
		
		    const getValue = (e) => {
		        const {name, value} = e.target;
		        setBoardContent({
		            ...boardContent,
		            [name] : value
		        })
		        // 값변경시 (키보드 누를 때마다) 확인한다면
		        // console.log(boardContent)
		    }
		
		    // ----------------------------------------------------
		    // 0. 화면 출력
		    return (
		        <div>               
		                <table>
		                    <tr>
		                        <td><label>글제목</label></td>  {/* [1-1] 입력값의 상태가 변경시 */}
		                        <td><input type="text" name="btitle" onChange={getValue}/></td>
		                    </tr>
		                    <tr>
		                        <td><label>작성자</label></td>
		                        <td><input type="text" name="bname" onChange={getValue}/></td>
		                    </tr>   
		                    <tr>
		                        <td><label>아이디</label></td>
		                        <td><input type="text" name="mid" onChange={getValue}/></td>
		                    </tr>
		                    <tr>
		                        <td><label>비밀번호</label></td>
		                        <td><input type="text" name="bpw" onChange={getValue}/></td>
		                    </tr>
		                    <tr>
		                        <td><label>내용</label></td>
		                        <td>
		                            <textarea name="bcontent" id="bcontent" cols="30" rows="5" onChange={getValue}></textarea>
		                        </td>
		                    </tr>  
		                    <tr>
		                        <td colSpan="2">                            
		                            <input type="submit" onClick={insertBoard} value="입력"/>
		                        </td>
		                    </tr>
		                </table>
		
		                {/* [2-2] 화면출력 */}
		                <hr/>
		                <div className='App'> [ 목록 ] </div>
		                <table>
		                    {
		                        viewContent.map((item, idx)=>{
		                            return (
		                                <tr className="listBox">
		                                    <td>{item.BNUM}</td>
		                                    <td>{item.BNAME}</td>
		                                    <td>{item.MID}</td>
		                                </tr>
		                            )
		                        })
		                    }
		                </table>
		               
		        </div>
		    ); 
		
		}
		
		export default App;
```
### React Context
```
	color.js
		// 매개체 역할을 하는 context
		const { createContext, useState} = require("react");
		const ColorContext = createContext({
		    state : { color : "black", subcolor : "red" },
		    actions : {
		        setColor : () => {},
		        setSubcolor : () => {}
		    }
		});
		
		// 생산자 (제공자)
		const ColorProvider = ({children}) => {
		    const [color, setColor] = useState("yellow");
		    const [subcolor, setSubcolor] = useState("green");
		
		    const value = {
		        state : { color, subcolor },
		        actions : { setColor, setSubcolor }
		    }
		
		    return (
		        <ColorContext.Provider value={value}>{children}</ColorContext.Provider>
		    );
		}
		
		// 소비자
		// 개념적으로 const ColorConsumer = ColorContext.Consumer; 같은 의미 필요
		const { Consumer : ColorConsumer} = ColorContext;
		
		export { ColorProvider, ColorConsumer};
		export default ColorContext;
	ColorBox.js
		import { useContext } from "react";
		import ColorContext, { ColorConsumer } from "../context/color";
		
		const ColorBox = () => {
		    const {state} = useContext(ColorContext);
		    return (
		        <div>
		            {
		                <div>
		                    <div style={{ width : "100px", height : "100px", background : state.color }}></div>
		                    <div style={{ width : "100px", height : "100px", background : state.subcolor }}></div>
		                </div>
		            }
		        </div>
		    );
		}
		
		export default ColorBox;
	SelectColor.js
		import { useContext } from "react";
		import ColorContext, { ColorConsumer } from "../context/color";
		
		// 색깔 변수 배열
		const colors = ["red", "orange", "yellow", "green", "blue", "indigo", "violet"];
		
		// 컴포넌트
		const SelectColor = () => {
		    const {actions} = useContext(ColorContext);
		    return (
		        <div>
		            {
		                // ColorConsumer(소비자)는 ColorContext 매개체로 전달받을 때 actions만 받음
		                <div style={{display:"flex"}}>
		                    {
		                        colors.map(color => (
		                            <div
		                                key={color}
		                                style={{background : color,
		                                    width : "50px",
		                                    height : "50px",
		                                    cursor : "pointer"
		                                }}
		                                // 왼쪽마우스클릭
		                                onClick={()=>actions.setColor(color)}
		                                onContextMenu={(evt)=>{
		                                    evt.preventDefault();
		                                    actions.setSubcolor(color);
		                                }}
		                            />
		                        ))
		                    }
		                </div>
		            }
		        </div>
		    );
		}
		
		export default SelectColor;
	App.js
		import ColorBox0 from "./components/ColorBox0";
		import ColorBox from "./components/ColorBox";
		import SelectColor0 from "./components/SelectColor0";
		import SelectColor from "./components/SelectColor";
		import { ColorProvider } from "./context/color";
		
		const App = () => {
		    return (
		        <ColorProvider>
		            <div>
		                <ColorBox0/>
		                <hr/>
		                <SelectColor0/>
		                <hr/><hr/><hr/><hr/><hr/>
		                <ColorBox/>
		                <hr/>
		                <SelectColor/>
		            </div>
		        </ColorProvider>
		    );
		}
		
		export default App;
```
### React Context
```
	index.js
		import App from './2_todolist_context/components/App';
		import {TodoProvider} from "./2_todolist_context/TodoContext";
		<TodoProvider>
			<App />
		</TodoProvider>
	TodoContext.js
		import { createContext, useState } from "react";
		const TodoContext = createContext();
		// 생성자
		const TodoProvider = (props) => {
		    const [todoList, setTodoList] = useState([
		        { no : 1, todo : "일어나기", done : true},
		        { no : 2, todo : "씻기",    done : false},
		        { no : 3, todo : "옷입기",  done : false},        
		    ]);
		
		    // [0] 함수 기존 구조만
		    const addTodo       = (todo) =>{ 
		        // map 함수
		        // let newTodoList = todoList.map((todo)=>{return {...todo}});
		        // newTodoList.push({no:new Date().getTime(), todo:todo, done:false});
		        // setTodoList(newTodoList);
		
		        // ...연산자
		        // let newTodoList = [...todoList, {no:new Date().getTime(), todo:todo, done:false}];
		        // setTodoList(newTodoList);
		
		        // immer 이용
		        let newTodoList = produce(todoList, (draft)=>{
		            draft.push({no:new Date().getTime(), todo:todo, done:false});
		        });
		        setTodoList(newTodoList);
		    }
		    const deleteTodo    = (no)  => {
		        let newTodoList = todoList.filter((todoList)=>todoList.no !== no);
		        setTodoList(newTodoList);
		    }
		    const toggleDone    = (no)   => {
		        // map함수와 ...연산자
		        // let newTodoList = todoList.map((todo)=>{
		        //     if(todo.no === no){
		        //         todo.done = !todo.done;
		        //     }
		        //     return {...todo}
		        // });
		        // setTodoList(newTodoList);
		
		        // immer
		        let idx = todoList.findIndex((todo)=>{
		            return todo.no === no;
		        });
		        let newTodoList = produce(todoList, (draft)=>{
		            draft[idx].done = !draft[idx].done;
		        });
		        setTodoList(newTodoList);
		    }
		
		    // return(<App todoList={todoList}
		    //             addTodo={addTodo}
		    //             deleteTodo={deleteTodo}
		    //             toggleDone={toggleDone} />);
		
		    const values = {
		        state : { todoList },
		        actions : { addTodo, deleteTodo, toggleDone }
		    }
		
		    return (
		        <TodoContext.Provider value={values}>
		            {props.children}
		        </TodoContext.Provider>
		    );
		}
		
		export {TodoProvider};
		export default TodoContext;
	InputTodo.js
		import { useContext, useState } from "react";
		import TodoContext from "../TodoContext";
		
		const InputTodo = (props) => {
		    // [0] 화면 구성 확인
		    const [todo, setTodo] = useState('');
		
		    const value = useContext(TodoContext);
		
		    // 입력
		    const changeTodo = (evt) => {
		        setTodo(evt.target.value);
		    }
		
		    // 추가
		    const addBtn = (evt) => {
		        value.actions.addTodo(todo);
		    }
		    // 입력창 enter
		    const enterInput = (evt) => {
		        if(evt.key === "Enter" && evt.target.value !== ""){
		            console.log(evt.target.value);
		            props.addTodo(todo);
		        }
		    }
		
		    return(
		        <div className="row">
		            <div className="col">
		                <div className="input-group">
		                    <input type='text' id='msg' name='msg' 
		                        value={todo} placeholder="여기에 입력" 
		                        className="form-control"
		                        onChange={changeTodo}
		                        onKeyUp={enterInput}
		                    />
		                    <span className="btn btn-primary input-group-addon" onClick={addBtn}> [ 추가 ] </span>    
		                </div>
		            </div>
		        </div>
		    );
		
		 
		}
		
		export default InputTodo;
	TodoList.js
		import { useContext } from "react";
		import TodoListItem from "./TodoListItem";
		import TodoContext from "../TodoContext";
		
		const TodoList = (props) => {
		
		    const value = useContext(TodoContext);
		
		    let items = value.state.todoList.map((item)=>{
		        return <TodoListItem key={item.no} 
		                    todoItem={item} 
		                    deleteTodo={value.actions.deleteTodo}
		                    toggleDone={value.actions.toggleDone}
		        />
		    });
		
		    return(
		        // [0] 기존 구조
		        <div className="row">
		            {" "}
		            <div className="col">
		                <ul className="list-group">{items}</ul>
		            </div>
		        </div>
		     
		    );
		}
		
		export default TodoList;
	TodoListItem.js
		const TodoListItem = (props) => {
		    // [0] 기존 구조
		    let itemClassName = "list-group-item";
		
		    if(props.todoItem.done){
		        itemClassName += " list-group-item-success";
		    }
		
		    const deleteBtn = () => {
		        props.deleteTodo(props.todoItem.no);
		    }
		
		    return (
		        <li className={itemClassName}>
		            <span className={props.todoItem.done ? "todo-done pointer" : "pointer"} onClick={()=>{
		                props.toggleDone(props.todoItem.no);
		            }}>
		                {props.todoItem.todo}
		                {props.todoItem.done ? " (완료)" : ""}
		            </span>
		            <span className="bg-secondary badge pointer" onClick={deleteBtn}> [ 삭제 ] </span>
		        </li>
		    );
		
		   
		}
		
		export default TodoListItem;
	App.js
		import InputTodo    from "./InputTodo";
		import TodoList     from "./TodoList";
		
		const App = (props) =>{
		    return (
		        // [0] 기존 구조
		        <div className="container">
		            <div className="card card-body bg-light">
		                <div className="title">할일목록</div>
		            </div>
		            <div className="card card-default">
		                <div className="card-body">
		                    <InputTodo/>
		                    <TodoList/>
		                </div>
		            </div>
		        </div> 
		    );
		}
		
		export default App;
	
```
### react typescript - 자바스크립트 와는 달리 자료형 검사
```
	node.js 버전 18버전으로 낮춤
		https://nodejs.org/en/download/prebuilt-installer
	자바스크립트 파일
		js ---> jsx (리엑트 권장)
	자바스크립트 특성
		자료형에 유연하다
	자바스크립트에서 자료형을 철저하게 하자
		1. PropTypes
			개발하는동안 모르고 실행할 때 잘못된 것을 알 수 있음
		2. typescript
			컴파일 시 자료형을 검사 후 경고 및 오류 출력
	cmd 설치
		create-react-app . --template typescript
		npm install -g typescript
		npm install -g ts-node
	확장자가 다르다
		ts, tsx
```
### react typescript
```
	App.tsx
		import { useState } from "react";
		import Cals from "./2_Cals";
		
		// 2_App.tsx
		const App = () => {
		    const [x, setX] = useState(100);
		    const [y, setY] = useState(200);
		
		    return (
		        <div>
		            <Cals x={x} y={y} op={"+"}/>
		            <Cals x={1} y={2} op={"*"}/>
		            <Cals x={1}/>
		        </div>
		    );
		}
		
		export default App;
	Cals.tsx
		// props 타입을 지정해줘야 한다
		type CalsType = {
		    x : number;
		    y : number;
		    op : string;
		}
		
		const Cals = (props:CalsType) => {
		
		    let result = 0;
		
		    switch(props.op){
		        case "+": result = props.x + props.y; break;
		        case "*": result = props.x * props.y; break;
		    }
		
		    return (
		        <div>
		            <h1>연산결과</h1>
		            <div>
		                {props.x} {props.op} {props.y} = {result}
		            </div>
		        </div>
		    );
		}
		
		Cals.defaultProps = {
		    op : "+",
		    x : 1,
		    y : -1
		}
		
		export default Cals;
```
### react typescript
```
	AppContainer.tsx
		import { useState } from "react";
		import App from './components/App';
		
		import produce from 'immer';
		
		// type
		export type TodoListItemType = {
		    no : number;
		    todo : string;
		    done : boolean;
		}
		
		const AppContainer = () => {
		    const [todoList, setTodoList] = useState([
		        { no : 1, todo : "일어나기", done : true},
		        { no : 2, todo : "씻기",    done : false},
		        { no : 3, todo : "옷입기",  done : false},        
		    ]);
		
		    
		
		    // [0] 함수 기존 구조만
		    const addTodo       = (todo:string) =>{ 
		        // map 함수
		        // let newTodoList = todoList.map((todo)=>{return {...todo}});
		        // newTodoList.push({no:new Date().getTime(), todo:todo, done:false});
		        // setTodoList(newTodoList);
		
		        // ...연산자
		        // let newTodoList = [...todoList, {no:new Date().getTime(), todo:todo, done:false}];
		        // setTodoList(newTodoList);
		
		        // immer 이용
		        let newTodoList = produce(todoList, (draft)=>{
		            draft.push({no:new Date().getTime(), todo:todo, done:false});
		        });
		        setTodoList(newTodoList);
		    }
		    const deleteTodo    = (no:number)  => {
		        let newTodoList = todoList.filter((todoList)=>todoList.no !== no);
		        setTodoList(newTodoList);
		    }
		    const toggleDone    = (no:number)   => {
		        // map함수와 ...연산자
		        // let newTodoList = todoList.map((todo)=>{
		        //     if(todo.no === no){
		        //         todo.done = !todo.done;
		        //     }
		        //     return {...todo}
		        // });
		        // setTodoList(newTodoList);
		
		        // immer
		        let idx = todoList.findIndex((todo)=>{
		            return todo.no === no;
		        });
		        let newTodoList = produce(todoList, (draft)=>{
		            draft[idx].done = !draft[idx].done;
		        });
		        setTodoList(newTodoList);
		    }
		
		    return(<App todoList={todoList}
		                addTodo={addTodo}
		                deleteTodo={deleteTodo}
		                toggleDone={toggleDone} />);
		
		}
		
		export default AppContainer;
	InputTodo.tsx
		import { useState } from "react";

		type InputTodoType = {
		    addTodo : (todo:string) => void;
		}
		
		const InputTodo = (props:InputTodoType) => {
		    // [0] 화면 구성 확인
		    const [todo, setTodo] = useState('');
		
		    // 입력
		    const changeTodo = (evt:React.ChangeEvent<HTMLInputElement>) => {
		        setTodo(evt.target.value);
		    }
		
		    // 추가
		    const addBtn = () => {
		        props.addTodo(todo);
		    }
		    // 입력창 enter
		    const enterInput = (evt:React.KeyboardEvent) => {
		        if(evt.key === "Enter"){
		            props.addTodo(todo);
		        }
		    }
		
		    return(
		        <div className="row">
		            <div className="col">
		                <div className="input-group">
		                    <input type='text' id='msg' name='msg' 
		                        value={todo} placeholder="여기에 입력" 
		                        className="form-control"
		                        onChange={changeTodo}
		                        onKeyUp={enterInput}
		                    />
		                    <span className="btn btn-primary input-group-addon" onClick={addBtn}> [ 추가 ] </span>    
		                </div>
		            </div>
		        </div>
		    );
		
		 
		}
		
		export default InputTodo;
	TodoList.tsx
		import TodoListItem from "./TodoListItem";
		import { TodoListItemType } from "../AppContainer";
		
		type TodoListProps = {
		    todoList : Array<TodoListItemType>;
		    deleteTodo : (no:number) => void;
		    toggleDone : (no:number) => void;
		}
		
		const TodoList = (props:TodoListProps) => {
		
		    let items = props.todoList.map((item)=>{
		        return <TodoListItem key={item.no} 
		                    todoItem={item} 
		                    deleteTodo={props.deleteTodo}
		                    toggleDone={props.toggleDone}
		        />
		    });
		
		    return(
		        // [0] 기존 구조
		        <div className="row">
		            {" "}
		            <div className="col">
		                <ul className="list-group">{items}</ul>
		            </div>
		        </div>
		     
		    );
		}
		
		export default TodoList;
	TodoListItem.tsx
		import { TodoListItemType } from "../AppContainer";
		
		type TodoListItemProps = {
		    todoItem : TodoListItemType;
		    deleteTodo : (no:number) => void;
		    toggleDone : (no:number) => void;
		}
		
		const TodoListItem = (props:TodoListItemProps) => {
		    // [0] 기존 구조
		    let itemClassName = "list-group-item";
		
		    if(props.todoItem.done){
		        itemClassName += " list-group-item-success";
		    }
		
		    const deleteBtn = () => {
		        props.deleteTodo(props.todoItem.no);
		    }
		
		    return (
		        <li className={itemClassName}>
		            <span className={props.todoItem.done ? "todo-done pointer" : "pointer"} onClick={()=>{
		                props.toggleDone(props.todoItem.no);
		            }}>
		                {props.todoItem.todo}
		                {props.todoItem.done ? " (완료)" : ""}
		            </span>
		            <span className="bg-secondary badge pointer" onClick={deleteBtn}> [ 삭제 ] </span>
		        </li>
		    );
		
		   
		}
		
		export default TodoListItem;
```
### 리눅스
```
	1. 리눅스 설치
		https://centos.org/
		http://mirror.anigil.com/CentOS/7.9.2009/isos/x86_64/
	2. 가상경로
		https://www.vmware.com/
		https://www.techspot.com/

	vmware 세팅
		키보드
			영어, 한국어
		소프트웨어
			개발 및 창
		설치대상
			/boot 만 남겨놓기
			swap 5g로 생성
			root 생성 용량 선택 x
		네트워크호스트
			이더넷 켜주기
		설치시작
		root암호
			admin1234
		사용자생성
			centos
	읽는방법
		/ 루트 위치
		~ 홈 위치
		r 읽기
		w 쓰기
		x 실
		- 파일
		d 디렉토리
		. 숨김파일
	권한
		# 심볼릭(기호) 모드에서 사용되는 문자와 기호의 종류
			1) 사용자 카테고리 문자
				` u (user)  : 파일 소유자
				` g (group) : 파일 소유자가 속한 그룹
				` o (other) : 파일 소유자와 그룹 이외의 기타 사용자
				` a (all) : 파일을 사용하려는 전체 사용자
		
			2) 연산자 기호
				` + 파일 접근 권한 부여
				` -  파일 접근 권한 제거
				` = 파일 접근 권한 설정 ( ex. u=rwx : 사용자에게 모든 권한을 부여 )
		​
			3) 접근권한 문자
				` r 파일 읽기 권한
				` w 파일 쓰기 권한
				` x 파일 실행 권한
		
		# 심볼릭 모드에서 다양한 파일 접근 권한 조합 ( 설명 보지 말고 읽을 수 있어야 한다 )
			` u+w : 파일 소유자에게 쓰기 권한 부여
			` u-w : 파일 소유자에게 쓰기 권한 제거
			` u=rwx : 파일 소유자에게 쓰기, 읽기, 실행 권한 설정
			` u+x, go+w : 소유자에게 실행 권한 부여와 그룹 및 기타 사용자에게 쓰기 권한 부여
			` g+w : 파일 그룹에게 쓰기 권한 부여
			` g+wx : 파일 그룹에게 쓰기와 실행 권한 부여
			` go+w : 그룹과 기타사용자에게 쓰기 권한 부여
			` +wx : 파일을 사용하려는 모든 사용자에게 쓰기와 실행 권한 부여
			` a+rwx : 모든 사용자에게 쓰기, 읽기, 실행 권한 부여
			` o-r : 기타 사용자에게 읽기 권한 제거

		--- 0 아무것도 안됨
		--x 1
		-w- 2
		-wx 3
		r-- 4
		r-x 5
		rw- 6
		rwx 7
		
		chmod 
			권한바꾸기
		
		예 - rw r-- r--
			소유자권한 그룹권한 기타사용자권한
			읽고쓰기  읽기만  읽기만
			
	명령어
		ls
			목록보기
		ls -l
			자세히 보기
		ls -l /
			루트 디렉토리 안 파일들을 자세히 보기
		ls -la
			모든 걸 자세히 보기 (숨김 파일까지 볼 수 있음)
		ls -R
			자식들까지 목록들이 다보임
		ls -li
			인덱스까지 자세히보기기
		man
			메뉴얼
		pwd
			나의 현재 위치
		cd
			폴더 이동
		cd ..
			현재 디렉토리에서 부모 디렉토리로 이동
		cd ~
			한번에 나의 계정으로 이
		history
			내가 입력했던 명령어나 내용들을 보여준다.
		mkdir
			폴더 만들기
		mkdir -p
			폴더/하위폴더/하위폴더 식으로 폴더 생성
		gedit
			파일 만들기???
		cat
			실행????
		cp
			복사하기
		touch
			빈파일 만들거나 파일명이 같을 때는 수정시간이 변경 됨
		mv
			원본을 옮긴다 또는 이름을 바꿀수도 있다
		rmdir
			비어있는 디렉토리 지우기
		rm -r
			강제로 지우지만 물어보면 y 입력해줘야 됨
		rm -rf
			그냥 지워버리기
		su
			계정 바꾸기
		vi
			메모장
				입력하기
					i 키를 누르면 입력 가능
				저장
					입력 후 :wq 하면 저장
				저장 없이 나가기
					:q!
				밖으로 나가기
					ctrl + z
				밖으로 나가기 취소
					fg
				왼쪽에 번호 보이기
					:set nu
				왼쪽 번호로 이동하기
					:숫
				줄 지우기
					dd
				맨 앞 줄 이동
					gg
				맨 마지막 줄 이동
					G
				검색
					/단어
				다음단어
					n
				이전단어
					N
				줄 복사
					:7,11y
				단어 바꾸기
					%s/October/May/g - October를 May 로 바꿈
	유저만들기
		useradd user1
			home 디렉토리 user1 생성
		passwd user1
			user1 비밀번호 생성
		tail /etc/shadow
			유저에 대한 안보이는 정보들 보기
		chmod g+r,g+w user2
			동일 그룹 사용자 읽고 쓰기 가능하게 권한 변경
		userdel user1
			user1 사용자 삭제
		userdel -r user2
			폴더까지 전부 지운
		groupadd centosGroup
			centosGroup 생성
		useradd -g centosGroup user3
		useradd -g centosGroup user4
			user3 user4를 centosGroup 으로 묶어서 생성
		chown user3 imsi
			imsi 파일의 소유주를 user3으로 바꿈
		usermod -g professor pro_002
			pro_002 폴더 그룹 professor 추가
		ps
			프로세스 보기
		ps -ef | grep 파일명
			실행중인 프로세스 검색해서 보기
		kill -9 파일명
			실행중인 프로세스를 강제로 죽이기
		chown -R hadoop:hadoop /opt/hadoop
			소유주 바꾸기
	링크
		하드링크
			ln basefile hardlink
				같은 주소를 참조하면서 파일 생성
		심볼릭링크 - 바로가기 랑 비슷
			ln -s basefile hardlink
				주소가 달라졌지만 basefile을 참조
	다운로드
		rpm -qa
			전체 설치한 목록
		rpm -qa |grep jdk
			전체 설치한 jdk 목록
		yum remove java*
			자바 전체 삭제하기
		yum install -y wget unzip
			물어보지 않고 wget 이랑 unzip 파일 설치
		jdk
			wget --no-check-certificate --no-cookies - --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8u131-b11/d54c1d3a095b4ff2b6607d096fa80163/jdk-8u131-linux-x64.tar.gz
		tomcat
			wget https://archive.apache.org/dist/tomcat/tomcat-9/v9.0.17/bin/apache-tomcat-9.0.17.tar.gz
		tar zvxf 파일명
			압축 풀기
		source /etc/profile
			설정파일 설정후 실행
		Putty 다운로드
			
		yum install openssh
			ssh 설치 (보안)
		which sshd
			ssh 설치 위치 확인
		firewall-cmd --add-port=22/tcp --permanent
			방화벽 풀기
		firewall-cmd --reload
			방화벽 다시 실행
		ifconfig
			리눅스의 ip 찾기(192.168.181.128)
		Putty 접속
			IP입력 후 이름 저장 후 접
		winscp 설치
			파일을 서버 리눅스쪽으로 옮길 수 있음
			https://winscp.net/eng/docs/lang:ko
	가상장치 만들기
		virtualbox
			https://www.virtualbox.org/ - 다운로드 - VirtualBox older builds - VirtualBox 6.1 - Windows hosts
				설치
		hashicorp
			[https://developer.hashicorp.com/](https://developer.hashicorp.com/vagrant/install) - Version: 2.2.19
				설치
			CMD
				c:\HashiCorp
				vagrant init
			C:\HashiCorp
				Vagrantfile 세팅
					VAGRANTFILE_API_VERSION = "2"

					Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
					
					     config.ssh.insert_key = false
					     config.vm.define :nn01 do |nn01_config|
					        nn01_config.vm.box = "centos/7"
					        nn01_config.vm.hostname = "nn01"
					        nn01_config.vm.network "private_network", ip: "192.168.56.101"
					        nn01_config.vm.provider :virtualbox do |vb|
					            vb.name = "nn01"
					            vb.memory = "4096"
					        end
					
					     end
					
					    config.vm.define :dn01 do |dn01_config|
					        dn01_config.vm.box = "centos/7"
					        dn01_config.vm.hostname = "dn01"
					        dn01_config.vm.network "private_network", ip: "192.168.56.102"
					        dn01_config.vm.provider :virtualbox do |vb|
					            vb.name = "dn01"
					            vb.memory = "4096"
					        end
					    end
					
					
					
					config.vm.define :dn02 do |dn02_config|
					        dn02_config.vm.box = "centos/7"
					        dn02_config.vm.hostname = "dn02"
					        dn02_config.vm.network "private_network", ip: "192.168.56.103"
					        dn02_config.vm.provider :virtualbox do |vb|
					            vb.name = "dn02"
					            vb.memory = "4096"
					        end
					    end
					
					
					end
			CMD
				vatrant up
			nn01
				ip addr 로 ip 확인
			설정 파일
				vi /etc/ssh/sshd_config
			ESC - /Password 입력
				(검색기능)
			systemctl restart sshd
				재시작
			putty 로 접속
				ip 입력 후 접속
	가상장치 푸티 말고 접속
		https://mobaxterm.mobatek.net/download-home-edition.html
			설치
		yum update
			업그레이드
		systemctl stop firewalld
			방화벽 멈추기
		systemctl disable firewalld
			방화벽 연결 끊기
		
			
									
```
### 파이썬 머신러닝 붓꽃
```
	# (1) 데이타 읽어오기
	import numpy as np
	from sklearn import datasets
	iris = datasets.load_iris()
	
	# (2) 데이터와 레이블 분리 변수 선언 ( 이미 데이터와 레이블이 정해짐 )
	X = iris["data"]
	print(X[:10])
	print("*"*100)
	
	y = iris["target"]
	print(y[:10])
	print("*"*100)
	
	# (3) 훈련데이터와 테스트 데이터로 분리하기
	from sklearn.model_selection import train_test_split
	X_train,X_test,y_train,y_test = train_test_split(X,y,random_state=0)
	
	# (4) 모델에 데이터를 학습하기
	# 훈련데이타와 훈련레이블를 인자로 넣어 학습한 결과 knn 객체를 리턴한다
	# n_neighbors : 이웃갯수 지정
	from sklearn.neighbors import KNeighborsClassifier
	knn = KNeighborsClassifier(n_neighbors=3)
	knn.fit(X_train,y_train) # 학습
	
	# (5) 새로운 샘플 데이타가 들어왔을 때 label 예측하기
	# 너무 동떨어진 데이타 입력하면 결과 예측 성능이 낮기에 기존 샘플과 유사하게 만듬
	newData = np.array([[5.1, 2.9, 1., 0.3]])
	y_predict = knn.predict(newData) # 예측
	print(y_predict)
	print("*"*100)
	print(iris["target_names"][y_predict])
	print("*"*100)
	
	# 검증
	print("훈련데이타 검증: {:.2f}".format(knn.score(X_train,y_train)))
	print("테스트데이타 검증: {:.2f}".format(knn.score(X_test,y_test)))
	print("*"*100)
	
	# 정확도 측정
	y_predict = knn.predict(X_test)
	print(np.mean(y_test == y_predict))
	print("*"*100)
```
### 리눅스 분산 환경 구축
```
	모든 사용자를 위한 java를 설치할 예정이니, root 계정으로 로그인한다.
	설치되었는지 확인하기 
	[root@nn01 ~]$ which java
	
	(1)설치전 필요 툴 ( root 계정에서 )
		$ yum install -y autoconf automake libtool curl gcc-c++ unzip
	2. JDK 8 설치 (nn01,dn01,dn02)
	
	***** zeppline 0.10 버전에서 jdk 1.8.151 이상을 요구한다
	
	그래서 jdk 버전을 여기서 높히자!!!!!!!!
	           a. cd /tmp
	           b. yum install -y vim wget unzip
	           c. wget --no-check-certificate --no-cookies - --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8u131-b11/d54c1d3a095b4ff2b6607d096fa80163/jdk-8u131-linux-x64.tar.gz
	                       ( Local에 이미 다운로드 한 경우 Winscp를 이용하여 업로드 )
	           d. ls jdk*
	           e. tar -xvzpf jdk-8u131-linux-x64.tar.gz
	           f. mkdir -p /opt/jdk/1.8.0_131
	           g. mv jdk1.8.0_131/* /opt/jdk/1.8.0_131/
	           h. ln -s /opt/jdk/1.8.0_131 /opt/jdk/current
	           i. install java with alternatives (에러)
	alternatives명령어 : centos의 yum을 통해 java를 install하게 되면 버젼관리 대상으로 들어간다.  
	그리고 centos는 버젼관리를 위한 명령어를 제공하는데 그것이 바로 alternatives라는 명령어이다.
	alternatives --install /usr/bin/java java /opt/jdk/1.8.0_131/bin/java 2
	alternatives --config java
	There is 1 program that provides 'java'.
	Selection Command
	
	-----------------------------------------------
	
	*+ 1 /opt/jdk1.8.0_131/bin/java
	Enter to keep the current selection[+], or type selection number:1  (입력)
	javac와 jar 명령어 경로도 alternatives 적용 권장
	At this point JAVA 8 has been successfully installed on your system. 
	We also recommend to setup javac and jar commands path using alternatives
	alternatives --install /usr/bin/jar jar /opt/jdk/1.8.0_131/bin/jar 2
	alternatives --install /usr/bin/javac javac /opt/jdk/1.8.0_131/bin/javac 2
	alternatives --set jar /opt/jdk/1.8.0_131/bin/jar
	alternatives --set javac /opt/jdk/1.8.0_131/bin/javac
	
	java -version

	*******************************************************************************
	--------------------------------------------------------------------------------
	3. Hadoop 설치 (nn01 / dn01 / dn02)
		a. cd /tmp
		b. wget  https://archive.apache.org/dist/hadoop/common/hadoop-2.7.7/hadoop-2.7.7.tar.gz
		c. tar -xvzf hadoop-2.7.7.tar.gz	
		d. mkdir -p /opt/hadoop/2.7.7	
		e. mv hadoop-2.7.7/* /opt/hadoop/2.7.7/	
		f. ln -s /opt/hadoop/2.7.7 /opt/hadoop/current
	4. Hadoop 사용자 추가
		a. useradd hadoop
		b. passwd hadoop   ( 비밀번호도 hadoop 으로 - 비밀번호 입력시는 글자표시 안됨  )
		c. chown -R hadoop:hadoop /opt/hadoop/  ( 루트에서 만든 파일의 권한을 hadoop에게 권함)
		d. su - hadoop
	5. 자바 및 Hadoop 환경 변수 추가
	 ( 설정파일 수정할 때는 MultiExe 보다 하나씩 하는 것이 나을 수도 있다 )
	     a. vi ~/.bash_profile
	#### HADOOP 2.7.7 start ############	
		PATH=$PATH:$HOME/bin	
		export HADOOP_HOME=/opt/hadoop/current	
		export PATH=$PATH:$HADOOP_HOME/bin	
		export PATH=$PATH:$HADOOP_HOME/sbin
	
	#### HADOOP 2.7.7end############
	#### JAVA 1.8.0 start#############
		export JAVA_HOME=/opt/jdk/current
		export PATH=$PATH:$JAVA_HOME/bin
	#### JAVA 1.8.0 end##############
		b.  source ~/.bash_profile
	9. 자바 및 hadoop 버전 확인
	    a. java -version
	    b. hadoop version
	10. 비밀번호없이 각노드를 접속할 수 있도록 공개키 공유(SSH)
	(0) 아래부분은 가상머신에서  직접해야 한다. (*****)
	     vi 강제 종료  :q!
	vi /etc/hosts (root 권한으로 ) - localhost 꼭 지운다 ( 모든 노드 다 )
		192.168.56.101 nn01
		192.168.56.102 dn01
		192.168.56.103 dn02
	(1) 키만들기 (Hadoop 계정에서 )
	( MultiExec 에서 하면 다른 키값을 생성되는 것을 볼 수 있다 )
		[hadoop@nn01 ~]$ ssh-keygen
		[hadoop@dn01 ~]$ ssh-keygen
		[hadoop@dn02 ~]$ ssh-keygen
		엔터만 3번친다
	2.키복사하기  
	( 여기서는 MultiExec 풀고 작업 - 각 노드별로 작업)
	( 자기 자신에게도 복사를 해야 됨 )		​	
		[hadoop@nn01 ~]$ ssh-copy-id hadoop@dn01	
		[hadoop@nn01 ~]$ ssh-copy-id hadoop@nn01	
		[hadoop@nn01 ~]$ ssh-copy-id hadoop@dn02		 	
		[hadoop@dn01 ~]$ ssh-copy-id hadoop@dn01	
		[hadoop@dn01 ~]$ ssh-copy-id hadoop@nn01	
		[hadoop@dn01 ~]$ ssh-copy-id hadoop@dn02		​	
		[hadoop@dn02 ~]$ ssh-copy-id hadoop@dn01	
		[hadoop@dn02 ~]$ ssh-copy-id hadoop@nn01	
		[hadoop@dn02 ~]$ ssh-copy-id hadoop@dn02		​
		yes >  비밀번호 hadoop

	---------------------------------------
	
	****패스워드없이 이동이 가능하다.  ( 나올 때는 exit 또는 logout 으로 나온다 )
		[hadoop@nn01 ~]$ ssh dn01
		[hadoop@nn01 ~]$ ssh dn02
		[hadoop@dn01 ~]$ ssh nn01
		[hadoop@dn01 ~]$ ssh dn02
		[hadoop@dn02 ~]$ ssh nn01
		[hadoop@dn02 ~]$ ssh dn01
		
	-----------------------------------------------
	
	[ su 명령어로 계정변경 가능하도록 ] - 각 노드에서 모두 수정		​	
		root->vagrant->hadoop	
		hadoop에서   su -    가 인증실패됨
		이을 해결하기위해
		/etc/pam.d/su 파일의 vagrant포함되어 있는 부분 3줄삭제 또는 hadoop으로 변경
		가상머신에서 root 계정에서 직접수정	
		[root@nn01 ~]# vi /etc/pam.d/su	
	​	10,11,12 라인에 vagrant 라고 보이는 3줄 주석처리
		[root@nn01 ~]# su - hadoop  //가능해짐 
		[hadoop@nn01 ~]​
	
	----------------------------------------------------
	
	* sudo 명령어 안될 때 
		root 계정에서 visudo -f /etc/sudoers
		ecs :100 라인  root  ALL=(ALL) ALL 을 yy로 복사하고 바로 p 눌려서 붙이고
		root를 hadoop으로 변경
		root   ALL=(ALL) ALL
		hadoop ALL=(ALL) ALL
		여기에 패스워드까지 묻지 않고 연결하고 싶으면 
		hadoop ALL=(ALL) NOPASSWD: ALL  ( 계정 등록 ) 
		%hadoop ALL=(ALL) NOPASSWD: ALL ( 그룹 등록 )
	
	​**************************************************	
	*** 나갈 때 제발 > stop-all.sh  꼭	
	**************************************************
```
