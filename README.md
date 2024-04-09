# myRef

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
	
	
	
1. 변수 설정 
	var byeunsu = "문자열";
2. 웹화면 출력
	document.writeln("변수의 값: " + byeunsu);
3. 콘솔창 출력
	console.log("변수의 값: " + byeunsu + "<br/>");
4. for
	for(var i = 0; i < arr.length; i++)
	for(var i in arr) - i가 출력
	for(var i of arr) - 값이 출력
5. 함수
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
