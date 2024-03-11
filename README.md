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
