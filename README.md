# learn_operator

import java.util.Scanner;

public class Operator {
	public void operatorTest( ) {
	/* *증감 연산자 연습
	   *단항 연산자
	   증감 연산자 : ++, --
	   피연산자의 값에 1을 더하거나 빼는 연산자로 위치레 따라 결과 값이 다르게 나타남
	   **전위 연산 : 먼저 연산 후 다른 연산 실행
	   ex) int a = 10;
	       int b = ++a; // 전위 연산의 경우 ++a를 먼저 계산하여 밑의 a값은 10+1한 11, b도 11이다
	       System.out.print(a + " , " + b);
	   **후위 연산 : 다른 연산 우선 실행 후 연산
	   ex) int a = 10;
	       int b = a++; // 후위 연산의 경우 a를 b에 먼저 대입하여 밑의 b값은 10, a는 이후에 더하여 11이다 
	       System.out.print(a + " , " + b);
	*/	
		int a = 5;
		int b = 10;
		
		int c = (++a) + b; // a:6 b:10 c:16
		int d = c / a;     // d:2
		int e = c % a;     // e:4 모듈러 연산은 나머지값
		int f = e++;       // f:4 e:5
		int g = (--b) + (d--); // b:9 d:1 g:11
		int h = 2;
		h *= e; // h값은 2고 e의 값인 5를 곱한값이 되어 h:10
		
		System.out.println("a = " + a);
		System.out.println("b = " + b);
		System.out.println("c = " + c);
		System.out.println("d = " + d);
		System.out.println("e = " + e);
		System.out.println("f = " + f);
		System.out.println("g = " + g);
		System.out.println("h = " + h);
	}
	
	//*단항 연산자
	//*논리 부정 연산자 : !
	// 논리 값을 부정하여 반대 값으로 변경
	// 제어문을 활용할 때 많이 쓰임
	// ex) boolean bool1 = true;
	//     boolean bool2 = !bool1;
	//     System.out.println(bool2); 
	
	//*산술 연산자
	// 일반 수학과 동일한 연산 방법, 단, %(Modular)는 나누기의 나머지 값을 구하는 연산
	
	//*비교 연산자1
	// 데이터가 같은지, 다른지 비교할 떄 쓰이며 항상 논리 값(true, false)이 결과 값임
	// 모든 자료형(기본형, 참조형) 사용 가능
	// ex) a == b , a와 b가 같으면 true
	//     a != b , a와 b가 다르면 true
	
	// 비교 연산자2
	// 두 피연산자의 값의 크기 비교
	// 기본형 boolean과 참조형을 제외하고 나머지 자료형에 모두 사용 가능
    // ex) if(a < b){} a가 b보다 작은경우 true가 되어 실행되고 작지 않은 경우 실행되지 X
	// < , > 크거나 작다가 =다 보다 앞에 나와야 함 ex) =< 는 X
	
	//*논리 연산자
	// 논리 값 두 개를 비교하는 연산자
	// && : 두 피연산자가 모두 true일 때 true 반환 (AND)
	// || : 두 피연산자 중 하나만 true여도 true 반환 (OR)
	
	/*복합 대입 연산자
	  다른 연산자와 대입 연산자가 결합한 것으로
	  자기 자신과 연산 후 연산 결과를 자기 자신에게 대입
	  ex) a += 10 -> a = a+10
	      a -= 10 -> a = a-10
	*/

	public void operatorTest2() {
		/* 산술 연산자 % : 나누었을 때 나머지를 구하는 연산자
		   **짝수 -> 값 % 2 == 0 , 값을 2로 나누었을때 나머지가 0이면 짝수
		   **홀수 -> 값 % 2 == 1 , 값을 2로 나누었을때 나머지가 1이면 홀수
		   **n의 배수 -> 값 % n == 0 , 값을 배수를 알아내고자 하는 수로 나누었을때 나머지가 0이면 배수
		   int num1 = 10;
		   int num2 = 3;
		   System.out.println("num1 % num2 = " + (num1%num2)); */
		
		/* 논리 연산자
		ex) 1과 100사이의 수?
		1 < 수 < 100 (X) 컴퓨터에선 이렇게 처리하지 않음
		변수 > 1 && 변수 < 100 (O) */
		Scanner sc = new Scanner(System.in);
		System.out.print("정수 입력 : ");
		int num3 = sc.nextInt();
		
		System.out.println("1과 100사이의 수 ? " + (num3 > 1 && num3 < 100));
		
		// 복합 대입 연산자
		// 코드가 간결하며 메모리에 직접 연산을 수행하여 연산속도도 빠름
		int num4 = 5;
		num4 += 10;
		System.out.println("num4 : " + num4); //15
		
		num4 -= 10;
		System.out.println("num4 : " + num4); //5
		
		num4 *= 10;
		System.out.println("num4 : " + num4); //50
		
		num4 /= 10;
		System.out.println("num4 : " + num4); //5
		
		num4 %= 10;
		System.out.println("num4 : " + num4); //5		
	}
	
	public void operatorTest3() {
		/*삼항 연산자
		사용 방법 : 조건식 ? 식1 : 식2;
		조건식의 결과 값에 따라 연산을 처리하는 방식으로 결과 값이 참일 경우 식1, 거짓일 경우 식2 수행
		삼항 연산자 안에 삼항 연산자를 중첩하여 쓰는 것도 가능
		ex) int result1 = a > b ? a++ : b--;
		    조건식인 a가 b보다 크다면 식1의 a++이 실행되어 a가 result1 값에 대입되고 후에 a값 1증가
		           a보다 b가 크지 않다면 식2의 b--가 실행되어 result1 값에 대입디고 후에 b값 1감소 */
		
		// 사용자에게 값을 받아서 그 값이 양수인지 음수인지 0인지 판별
		Scanner sc = new Scanner(System.in);
		System.out.print("정수 하나 입력 : ");
		int num = sc.nextInt();
		
		String result = num > 0 ? "양수다" : num == 0 ? "0이다" : "음수다";
		System.out.println(result);
	}	
}
