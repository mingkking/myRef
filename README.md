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
	리눅스
		.으로 시작하는 파일들은 숨김파일이다.
		맨 앞쪽에 - 로 시작하면 그건 파일이다.
		맨 앞쪽에 d 로 시작하면 그건 폴더이다.
		/
			최상위 위치
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
					%s/October/May/g - October를 May 로 바

				
```
