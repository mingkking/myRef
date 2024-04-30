# myRef
```
윤년
	y % 4 == 0 && y % 100 != 0 || y % 400 == 0
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
