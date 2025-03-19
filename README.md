자바는 **표준 스펙(Standard Specification)**과 **구현(Implementation)** 으로 나눌 수 있다.

![](https://velog.velcdn.com/images/songbeom00/post/fd87d5ec-43af-4f7c-aa70-67871d4946f5/image.png)


1. 표준 스펙(Standard Specification)

표준 스펙은 자바 플랫폼에서 반드시 따라야 하는 규칙과 인터페이스를 정의합니다. 대표적으로는 다음과 같은 것들이 있습니다.

- (1) 자바 컴파일러(Java Compiler) : Java 소스코드(.java)를 바이트코드(.class)로 변환하는 역할을 합니다.
대표적인 컴파일러 : javac (JDK에서 제공)

![](https://velog.velcdn.com/images/songbeom00/post/5027f398-737d-41fb-9d8d-19c43bbee29e/image.png)


- (2) 자바 실행 라이브러리(Java Standard Library) : java.lang, java.util, java.io 등의 표준 라이브러리(클래스 및 API)들이 포함됩니다. 
개발자가 프로그램을 쉽게 개발할 수 있도록 제공되는 라이브러리입니다.

- (3) 자바 가상 머신(JVM, Java Virtual Machine) : 바이트코드(.class)를 실행하는 런타임 환경입니다.
Java 프로그램이 다양한 운영체제에서 실행할 수 있도록 해줍니다. (MacOS, Window, Linux 등)
JVM은 표준 스펙을 기반으로 여러 벤더(Oracle, OpenJDK, Azul 등)에서 구현할 수 있습니다.

![](https://velog.velcdn.com/images/songbeom00/post/3477e233-754f-4c62-8566-23d7e91190a4/image.png)


2. 구현(Implementiation)

표준 스펙을 기반으로 실제 동작하는 구현체들이 있습니다. 대표적인 것들은 다음과 같습니다.

- (1) JDK(Java Development Kit) : Java 애플리케이션을 개발할 수 있도록 지원하는 개발 도구 모음입니다.
Javac(컴파일러), Java(JVM 실행기), 표준라이브러리, 개발도구(JConsole, JDB)등이 포함됩니다.
대표적인 JDK 구현체 : Oracle JDK, OpenJDK(자바의 오픈소스 구현), Amazon Corretto(AWS에서 제공), Azul Zulu, GraalVM 등이 있습니다.

- (2) JVM 구현체 : Java 바이트코드를 실행하는 가상 머신 입니다.
대표적인 구현체 : HotSpot JVM(Oracle, OpenJDK에서 사용), OpenJ9(IBM에서 개발), GraalVM(Oracle에서 제공하는 최적화된 JVM)이 있습니다.


 ## ✅ 정리 
 - 표준 스펙 : 자바 컴파일러, 실행 라이브러리, JVM의 규칙과 인터페이스 정의
 
 - 구현 : 표준 스펙을 따라 만들어진 실제 JDK 및 JVM 구현체 (Oracle JDK, OpenJDK, HotSpot, GraalVM 등)
 
 > **“표준 스펙”**은 레시피(요리법) 같은 것이고, **“구현”**은 그 레시피를 사용해 만든 실제 요리(Oracle JDK, OpenJDK 등) 라고 볼 수 있습니다. 


자바 변수 시작

패키지(package) : 패키지는 관련된 클래스와 인터페이스를 그룹화하는 기능을 합니다. 쉽게 말해, 폴더(디렉토리)처럼 클래스들을 체계적으로 관리하는 방법입니다.
- `variable`이라는 패키지를 만들었다면, 해당 패키지에 들어가는 자바 파일 첫줄에 `package variable;`와 같이 소속된 패키지를 선언해주어야 합니다.

- 자바 파일이 위치하는 패키지와 `package variable` 선언 위치가 같아야 합니다.


1 . 패키지의 역할

(1) 클래스 간의 충돌 방지 : 동일한 이름의 클래스를 서로 다른 패키지에 만들 수 있습니다.
예) com.example.User와 org.company.User는 서로 다른 패키지에서 존재 가능합니다.

(2) 코드의 가독성과 유지보수성 향상 : 관련된 기능을 가진 클래스들을 한 패키지에 묶어 관리할 수 있습니다.
예) java.util 패키지는 유틸리티 관련 클래스들을 모아둡니다.

(3) 접근 제어(Access Control) : public, protected, default, private 등의 접근 제한자를 통해 클래스의 접근 범위를 관리할 수 있습니다.

(4) 클래스 및 인터페이스 효율적인 관리 : 대규모 프로젝트에서 코드 관리가 용이합니다. javax.servlet, java.sql처럼 표준 패키지를 제공합니다.



2. 자바의 대표적인 표준 패키지 

| 패키지명         | 설명                                      | 주요 클래스 예시 |
|-----------------|--------------------------------|------------------------------|
| `java.lang`     | 기본 클래스 (자동 임포트)       | `String`, `Math`, `System`, `Object`, `Thread` |
| `java.util`     | 유틸리티 및 컬렉션 프레임워크  | `ArrayList`, `HashMap`, `Collections`, `Date`, `Random` |
| `java.io`       | 입출력 스트림                 | `File`, `BufferedReader`, `BufferedWriter`, `InputStream`, `OutputStream` |
| `java.nio`      | 새로운 입출력 (NIO)           | `ByteBuffer`, `FileChannel`, `Path`, `Files` |
| `java.net`      | 네트워크 프로그래밍           | `Socket`, `ServerSocket`, `URL`, `HttpURLConnection` |
| `java.sql`      | 데이터베이스 연동 (JDBC)      | `Connection`, `Statement`, `PreparedStatement`, `ResultSet` |
| `javax.servlet` | 웹 애플리케이션 개발          | `HttpServlet`, `ServletRequest`, `ServletResponse`, `RequestDispatcher` |
| `javax.swing`   | GUI (그래픽 사용자 인터페이스) | `JFrame`, `JButton`, `JLabel`, `JPanel` |
| `java.time`     | 날짜 및 시간 API (Java 8 이후) | `LocalDate`, `LocalTime`, `LocalDateTime`, `DateTimeFormatter` |
| `java.security` | 보안 및 암호화                 | `MessageDigest`, `SecureRandom`, `KeyPair`, `Signature` |



```java
package variable; //패키지 선언

public class Var1 {
    public static void main(String[] args) {
        System.out.println(10);
        System.out.println(10);
        System.out.println(10);
    }
}
```
실행 결과
```
10
10
10
```
단순히 숫자 10을 3번 출력하는 코드이다. 그런데 여기서 숫자 10을 3번 출력하는 대신에 숫자 20을 3번 출력하도록 코드를 변경해보면?

```java
package variable;

public class Var1 {
    public static void main(String[] args) {
        System.out.println(20); //변경 10 -> 20
        System.out.println(20); //변경 10 -> 20
        System.out.println(20); //변경 10 -> 20
    }
}
```
숫자가 10이라고 적혀 있는 곳을 모두 찾아서 숫자 20으로 변경해야 한다. 만약 여기서 숫자 10을 출력하는 부분이 100개라면 100개의 코드를 모두 변경해야 한다!!

그래서 모든 프로그래밍 언어는 이런 문제를 해결하기 위해 **변수(variable)**라는 기능을 제공한다. 변수는 이름 그대로 변할 수 있다는 뜻이다.

변수(variable)란? **데이터를 저장하는 메모리 공간**을 의미합니다.
자바에서는 변수를 선언할 때 **자료형(Data Type)**을 명시해야 하며, 변수는 특정한 값(데이터)을 저장하고 관리하는 역할을 합니다.

```java
package variable;

public class Var2 {
    public static void main(String[] args) {
        int a; // 변수 선언
        a = 10; //변수 초기화
        System.out.println(a);
        System.out.println(a);
        System.out.println(a);
    }
}
```
![](https://velog.velcdn.com/images/songbeom00/post/fdfc0d02-4970-40bb-b7d0-328edab19d0a/image.png)

a = 10 실행 결과
```
10
10
10
```

![](https://velog.velcdn.com/images/songbeom00/post/d499505b-57e6-47ca-9a4a-06ebe70d38ce/image.png)


![](https://velog.velcdn.com/images/songbeom00/post/cdb5cb2b-57d3-4bf1-8a09-d30589dee794/image.png)



이번에는 `a = 20` 으로 변경해서 실행해보자

```java
package variable;

public class Var2 {
    public static void main(String[] args) {
        int a; // 변수 선언
        a = 20; //10 -> 20으로 변경
        System.out.println(a);
        System.out.println(a);
        System.out.println(a);
    }
}
```

a = 20 실행 결과
```
20
20
20
```
이처럼 변수(variable) a의 값을 변경하면 출력결과가 모두 함께 변경되는 것을 확인할 수 있다.

변수를 선언하고, 선언한 변수에 처음으로 값을 저장하는 것을 변수 초기화라 합니다.

```java
package variable;

public class Var5 {
    public static void main(String[] args) {
        // 1. 변수 선언, 초기화 각각 따로
        int a;
        a = 1;
        System.out.println("a = " + a);

        int b = 2; // 2. 변수 선언과 초기화를 한번에
        System.out.println("b = " + b);

        int c = 3 , d = 4; // 3. 여러 변수 선언과 초기화를 한번에
        System.out.println("c = " + c);
        System.out.println("d = " + d);
    }
}
```

변수는 초기화 해야 합니다.

- 만약 변수를 초기화 하지 않고 사용하면 어떻게 될까?

```java
package variable;

public class Var6 {
    public static void main(String[] args) {
        int a;
        System.out.println(a); //주석을 풀면 컴파일 에러 발생
    }
}
```
다음과 같은 컴파일 에러가 발생합니다.

`java: variable a might not have been initialized`

변수가 초기화되지 않았다는 오류가 발생합니다.

왜 이런 오류가 발생할까? 컴퓨터에서 메모리는 여러 시스템이 함께 사용하는 공간이다. 그래서 어떠한 값들이 계속 저장됩니다. 변수를 선언하면 메모리상의 어떤 공간을 차지하고 사용합니다. 그런데 그 공간에 기존에 어떤 값이 있었는지는 아무도 모른다. 따라서 초기화 하지 않으면 이상한 값이 출력될 수 있습니다. 이런 문제를 예방하기 위해 자바는 변수를 초기화 하도록 강제합니다.

**지역 변수(Local variable)**

메서드 내부에서 선언되며, 해당 블록에서만 사용 가능합니다.

반드시 초기화 후 사용해야 합니다.

```java
public class Main {
    public static void main(String[] args) {
        int number = 10;  // 지역 변수
        System.out.println("지역 변수: " + number);
    }
}
```

Java 변수 타입

1. 기본 데이터 타입 (Primitive Type)
자바에서 기본 데이터 타입(Primitive Type)은 메모리에 **직접 값을 저장**하는 타입입니다.

| 자료형  | 크기      | 기본값  | 설명 |
|--------|----------|--------|--------------------------------|
| `byte`   | 1바이트 | `0` | 정수형 (-128 ~ 127) |
| `short`  | 2바이트 | `0` | 정수형 (-32,768 ~ 32,767) |
| `int`    | 4바이트 | `0` | 정수형 (-2³¹ ~ 2³¹-1) |
| `long`   | 8바이트 | `0L` | 정수형 (-2⁶³ ~ 2⁶³-1) |
| `float`  | 4바이트 | `0.0f` | 실수형 (소수점 이하 표현 가능) |
| `double` | 8바이트 | `0.0d` | 실수형 (더 정밀한 소수 표현 가능) |
| `char`   | 2바이트 | `'\u0000'` | 문자형 (유니코드 기반) |
| `boolean`| 1바이트 | `false` | 논리형 (참/거짓) |

![](https://velog.velcdn.com/images/songbeom00/post/50cb2a82-5061-4888-9324-183e1f9fcd18/image.png)


**기본 타입 사용 예시**

```java
int number = 10; //정수
double pi = 3.14; //실수
boolean isJavaFun = true; //불리언(boolean) true, false 입력 가능
char grade = 'A'; //문자 하나
```

2. 참조 데이터 타입 (Reference Type)

자바에서 **참조 타입(Reference Type)**은 변수에 직접 값을 저장하는 것이 아니라, **객체의 메모리 주소(참조값)를 저장**하는 타입입니다.

---

1. 참조 타입의 종류

| 참조 타입   | 설명 |
|------------|-----------------------------------------------|
| `String`   | 문자열을 저장하는 객체 |
| `Array`    | 같은 타입의 여러 값을 저장하는 배열 |
| `Class`    | 사용자 정의 클래스를 저장하는 타입 |
| `Interface` | 인터페이스를 구현하는 객체를 저장 |
| `Object`   | 모든 클래스의 최상위 타입 |

---

**참조 타입 사용 예시**

```java
String name = "Alice";  // 문자열 리터럴
String greeting = new String("Hello"); // 명시적 객체 생성
```

**리터럴**

코드에서 개발자가 직접 적은 `100`,`10.5`,`true`,`'A'`,`"Hello Java"`와 같은 고정된 값을 프로그래밍 용어로 리터럴(literal)이라 합니다.

```java
int a = 100; //정수 리터럴
double b = 10.5; //실수 리터럴
boolean c = true; //불리언 리터럴
char d = 'A'; //문자 하나 리터럴
String e = "Hello Java"; //문자열 리터럴
```
변수의 값은 변할 수 있지만 리터럴은 개발자가 직접 입력한 고정된 값이다. 따라서 리터럴 자체는 변하지 않습니다.


## ✅ **정리** 

자바(Java)에서는 변수는 크게 **기본 타입(Primitive Type)**과 **참조 타입(Reference Type)**으로 나뉩니다. 

| 비교 항목      | 기본 타입 (Primitive Type) | 참조 타입 (Reference Type) |
|--------------|--------------------------|--------------------------|
| **저장 방식** | 변수에 직접 값 저장 | 객체의 메모리 주소 저장 |
| **기본값**   | `0`, `false`, `'\u0000'` 등 | `null` |
| **메모리 영역** | **스택(Stack)**에 저장 | **힙(Heap)**에 저장 (주소만 스택에 저장) |
| **속도** | 상대적으로 빠름 | 상대적으로 느림 (객체 생성 필요) |
| **사용 예제** | `int num = 10;` | `String str = "Hello";` |
| **비교 연산** | `==` 연산자로 값 비교 | `==` 연산자는 주소 비교, `.equals()`로 값 비교 |
| **메모리 관리** | JVM이 자동 관리 | 가비지 컬렉터(GC)가 객체 삭제 |
| **유형** | `byte`, `short`, `int`, `long`, `float`, `double`, `char`, `boolean` | `String`, `Array`, `Class`, `Interface`, `Object` |

- 기본 타입은 직접 값을 저장하고 스택(Stack) 메모리에서 관리되므로 속도가 빠름.
- 참조 타입은 객체의 메모리 주소를 저장하며, 힙(Heap)에서 관리되므로 **가비지 컬렉션(GC)**이 필요.
- 기본 타입은 == 비교가 가능하지만, 참조 타입은 .equals()를 사용하여 값을 비교해야 함.
- **참조 타입의 기본값은 null**이며, null 체크가 필수.


## 연산자

`+`,`-`,`*`,`/`와 같이 계산을 수행하는 기호를 연산자라 한다. 자바에는 다음과 같은 다양한 연산자가 있다.

연산자 종류

- 산술 연산자 `+`,`-`,`*`,`/`,`%`(나머지 연산자)

- 증감(증가 및 감소 연산자) : `++`, `--`

- 비교 연산자 : `==`, `!=`, `>`, `<`, `>=`, `<=`

- 논리 연산자 : `&&` (AND), `||`(OR), `!`(NOT)

- 대입 연산자 : `=`, `+=`, `-=`, `*=`, `/=`, `%=`

- 삼항 연산자 : `? :`


```java
package operator;

public class Operator1 {


    public static void main(String[] args) {
        // 변수 초기화
        int a = 5;
        int b = 2;

        // 덧셈
        int sum = a + b;
        System.out.println("sum = " + sum); // 출력 : a + b = 7

        // 뺄셈
        int sub = a - b;
        System.out.println("sub = " + sub); // 출력 : a - b = 3

        // 곱셈
        int mul = a * b;
        System.out.println("mul = " + mul); // 출력 : a * b = 10

        // 나눗셈
        int div = a / b;
        System.out.println("div = " + div); // 출력 : a / b = 2

        // 나머지
        int mod = a % b;
        System.out.println("mod = " + mod); // 출력 : a % b = 1

    }


}
```

**실행 결과**

```
sum = 7
sub = 3
mul = 10
div = 2
mod = 1
```

- `5/2`의 결과는 `2.5`가 되어야 하지만 결과는 소수점이 제거된 `2` 가 나왔다.
	- 자바에서 같은 `int`형끼리 계산하면 계산 결과도 같은 `int`형을 사용한다. `int`형은 정수이기 때문에 소수점 이하를 포함할 수 없다.
    
    
- 나머지 연산자(`%`) : 이름 그대로 나머지를 구하는 연산자이다. `5 / 2`는 몫이 2 나머지가 1이다. 따라서 나머지 연산자 `5 % 2`의 결과는 `1`이 된다.


**주의!! 0으로 나누기**

`10 / 0` 과 같인 숫자는 0으로 나눌 수 없다. (수학에서 허용하지 않는다.)
방금 예제에서 변수 `b = 0`을 대입하면 `5 / 0`이 된다. 이 경우 프로그램에 오류가 발생한다.


`Exception in thread "main" java.lang.ArithmeticException: / by zero
	at operator.Operator1.main(Operator1.java:24)`
    
  
  
## 문자열 더하기

- 자바는 특별하게도 문자열에도 `+`연산자를 사용할 수 있다. 문자열에 `+`연산자를 사용하면 두 문자를 연결할 수 있다.

```java
package operator;

public class Operator2 {
    public static void main(String[] args) {

        //문자열과 문자열 더하기
        String result1 = "hello" + " world";
        System.out.println("result1 = " + result1);

        //문자열과 문자열 더하기2
        String s1 = "string1";
        String s2 = "string2";
        String result2 = s1 + s2;
        System.out.println("result2 = " + result2);
        
        //문자열과 숫자 더하기
        String result3 = "a + b = " + 10;
        System.out.println("result3 = " + result3);

        //문자열과 숫자 더하기
        int num  = 20;
        String str = "a + b  = " ;
        String result4 = str + num;
        System.out.println("result4 = " + result4);

    }
}
```

**실행 결과**

```
result1 = hello world
result2 = string1string2
result3 = a + b = 10
result4 = a + b  = 20
```

문자열과 숫자 더하기1 

다음 식은 문자열과 숫자를 더한다. 자바에서 **문자와 숫자를 더하면 숫자를 문자열로 변경한 다음에 서로 더한다.**
`"a + b = " + 10`
- 문자 `"a + b = "`

- 숫자 : `10`

**계산 과정**

```java
"a + b = "(String) + 10(int) //문자열과 숫자 더하기
"a + b = "(String) + "10"(int -> String) //숫자를 문자열로 변경
"a + b = " + "10" //문자열과 문자열 더하기
"a + b = 10" //결과
```
    
문자열과 숫자 더하기2 

```java
int num  = 20;
String str = "a + b  = " ;
String result4 = str + num;
System.out.println(result4);
"a + b  = 20" //결과
```

마찬가지로 변수에 담겨 있어도 문자와 숫자를 더하면 문자가 된다.

즉 자바는 문자열은 `String` 타입에 다른 타입을 더하는 경우 대상 타입을 문자열로 변경한다. 쉽게 이야기해서 **문자열에 더하는 것은 다 문자열이 된다.**
    
    
## 연산자 우선순위 (높음 -> 낮음)   

| 우선순위 | 연산자 | 설명 | 결합 방향 |
|---------|--------|---------------------|----------|
| 1 | `()`, `[]`, `.` | 괄호, 배열 접근, 멤버 접근 | 왼→오 |
| 2 | `++`, `--` | 단항 증가/감소 (후위) | 왼→오 |
| 3 | `++`, `--`, `+`, `-`, `~`, `!` | 단항 연산자 (전위), 부호 연산, 비트 NOT, 논리 NOT | 오→왼 |
| 4 | `new`, `(타입)` | 객체 생성, 형변환 | 오→왼 |
| 5 | `*`, `/`, `%` | 곱셈, 나눗셈, 나머지 | 왼→오 |
| 6 | `+`, `-` | 덧셈, 뺄셈 | 왼→오 |
| 7 | `<<`, `>>`, `>>>` | 비트 이동 | 왼→오 |
| 8 | `<`, `<=`, `>`, `>=`, `instanceof` | 비교, instanceof 연산자 | 왼→오 |
| 9 | `==`, `!=` | 동등 비교 | 왼→오 |
| 10 | `&` | 비트 AND | 왼→오 |
| 11 | `^` | 비트 XOR | 왼→오 |
| 12 | `|` | 비트 OR | 왼→오 |
| 13 | `&&` | 논리 AND | 왼→오 |
| 14 | `||` | 논리 OR | 왼→오 |
| 15 | `? :` | 삼항 연산자 | 오→왼 |
| 16 | `=`, `+=`, `-=`, `*=`, `/=`, `%=`, `&=`, `^=`, `|=`, `<<=`, `>>=`, `>>>=` | 대입 연산자 | 오→왼 |


- 연산자 우선순위는 상식선에서 생각하고, 애매하면 괄호를 사용하자!

## 증감 연산자

- 증가 및 감소 연산자를 줄여서 증감 연산자라 한다.

- 증감 연산자는 `++`와 `--`로 표현되며, 이들은 변수의 값을 1만큼 증가시키거나 감소시킨다.


전위, 후의 증감 연산자

증감 연산자는 피연산자 앞에 두거나 뒤에 둘 수 있으며, 연산자의 위치에 따라 연산이 수행되는 시점이 달라진다.

- `++a`: 증감 연산자를 피연산자 앞에 둘 수 있다. 이것을 앞에 있다고 해서 **전위(Prefix) 증감 연산자**라 한다.

- `a++`: 증감 연산자를 피연산자 뒤에 둘 수 있다. 이것을 앞에 있다고 해서 **후위(Postfix) 증감 연산자**라 한다.


```java
package operator;

public class OperatorAdd2 {

    public static void main(String[] args) {
        //전위 증감 연산자 사용 예
        int a = 1;
        int b = 0;
        b =  ++a; // a의 값은 먼저 증가시키고, 그 결과를 b에 대입합니다.
        System.out.println("a = " + a + ", b = " + b); // 결과: a = 2, b = 2


        //후위 증감 연산자 사용 예
        a = 1; // a를 다시 1로 초기화
        b = 0; // b를 다시 0으로 초기화
        b = a++; // a의 값을 먼저 b에 대입하고, 그 다음 a의 값을 증가시킵니다.
        System.out.println("a = " + a + ", b = " + b); // 결과: a = 2, b = 1


    }
}
```
**실행 결과**

```
a = 2, b = 2
a = 2, b = 1
```

## 비교 연산자

- 비교 연산자는 두 값을 비교하는데 사용한다. 비교 연산자는 주로 조건문과 함께 사용한다.


- `==`: 동등성(equal to)

- `!=`: 불일치(not equal to)

- `>`: 크다(greater than)

- `<`: 작다(less than)

- `>=`: 크거나 같다(greater than or equal to)

- `<=`: 작거나 같다(less than or equal to)

비교 연산자를 사용하면 참(`true`)또는 거짓(`false`)이라는 결과가 나온다. 참 거짓은 `boolean`형을 사용한다.

여기서 주의할 점은 `=`와 `==`(`=`x2)이 다르다는 점이다.

- `=`:대입 연산자, 변수에 값을 대입한다.

- `==`:동등한지 확인하는 비교 연산자


문자열 비교

- 문자열이 같은지 비교할 때는 `==`이 아니라 `.equals()` 메서드를 사용해야 한다.

- `==`를 사용하면 성공할 때도 있지만 실패할 때도 있다.


```java
package operator;

public class Comp2 {

    public static void main(String[] args) {
        String str1= "문자열1";
        String str2= "문자열2";

        boolean result1 = "hello".equals("hello"); //리터럴 비교
        boolean result2 = str1.equals("문자열1"); //문자열 변수, 리터럴 비교
        boolean result3 = str1.equals(str2); //문자열 변수 비교

        System.out.println("result1 = " + result1);
        System.out.println("result2 = " + result2);
        System.out.println("result3 = " + result3);
    }
}
```
**실행 결과**

```
result1 = true
result2 = true
result3 = false
```


## 논리 연산자

- 논리 연산자는 `boolean`형인 `true`, `false`를 비교하는데 사용한다.


`&&`(그리고) : 두 피연산자가 모두 참이면 참을 반환, 둘중 하나라도 거짓이면 거짓을 반환

`||`(또는) : 두 피연산자가 중 하나라도 참이면 참을 반환, 둘다 거짓이면 거짓을 반환

`!`(부정) : 피연산자의 논리적 부정을 반환. 즉, 참이면 거짓을, 거짓이면 참을 반환

```java
package operator;

public class Logical1 {

    public static void main(String[] args) {
        System.out.println("&&: AND 연산");
        System.out.println("true && true : " + (true && true));
        System.out.println("true && false : " + (true && false));
        System.out.println("false && false : " + (false && false));

        System.out.println("||: OR 연산");
        System.out.println("true || true : " + (true || true));
        System.out.println("true || false : " + (true || false));
        System.out.println("false || false : " + (false || false));

        System.out.println("!: NOT 연산");
        System.out.println("!true : " + (!true));
        System.out.println("!false : " + (!false));

        System.out.println("변수 활용");
        boolean a = true;
        boolean b = false;
        System.out.println("a && b : " + (a && b));
        System.out.println("a || b : " + (a || b));
        System.out.println("!a : " + (!a));
        System.out.println("!b = " + (!b));

    }

}
```
**실행 결과**
```
&&: AND 연산
true && true : true
true && false : false
false && false : false
||: OR 연산
true || true : true
true || false : true
false || false : false
!: NOT 연산
!true : false
!false : true
변수 활용
a && b : false
a || b : true
!a : false
!b = true
```

## 대입 연산자

- 대입 연산자(`=`)는 값을 변수에 할당하는 연산자다. 이 연산자를 사용하면 변수에 값을 할당할 수 있다.
예를 들어, `int a = 1`는 `a`라는 변수에 `1`이라는 값을 할당한다.


**축약(복학) 대입 연산자**
산술 연산자와 대입 연산자를 한번에 축약해서 사용할 수 있는데, 이것을 축약(복합) 대입 연산자라 한다.

연산자의 종류: `+=`, `-=`, `*=`, `/=`, `%=`

```java
package operator;

public class Assign1 {

    public static void main(String[] args) {
        int a = 5; // 5
        a += 3; // 8 ( 5 + 3 ) : a = a + 3;
        a -= 2; // 6 ( 8 - 2 ) : a = a - 2;
        a *= 4; // 24 ( 6 * 4 ) : a = a * 4;
        a /= 3; // 8 ( 24 / 3 ) : a = a / 3;
        a %= 5 ; // 3 ( 8 % 5 ) : a = a % 5;
        System.out.println("a = " + a);
    }
}
```
**실행 결과**

```
a = 3
```

## ✅ 정리

자주 사용하는 연산자

| 종류 | 연산자 | 설명 |
|------|--------|------|
| **산술 연산자** | `+`, `-`, `*`, `/`, `%` | 덧셈, 뺄셈, 곱셈, 나눗셈, 나머지 |
| **증가 및 감소 연산자** | `++`, `--` | 값 1 증가/감소 |
| **비교 연산자** | `==`, `!=`, `>`, `<`, `>=`, `<=` | 값 비교 |
| **논리 연산자** | `&&`, `||`, `!` | 논리 AND, OR, NOT |
| **대입 연산자** | `=`, `+=`, `-=`, `*=`, `/=`, `%=` | 변수에 값 할당 및 연산 |

---

추가적으로 자주 사용하는 연산자

| 종류 | 연산자 | 설명 |
|------|--------|------|
| **삼항 연산자** | `? :` | 조건에 따라 값 선택 |
| **instanceof 연산자** | `instanceof` | 객체 타입 확인 |
| **기타** | `new`, `[]`, `.`, `()` | 객체 생성, 배열 인덱스, 객체 멤버 접근, 메서드 호출 |

---

비트 연산자 (실무에서 거의 사용되지 않음)

| 종류 | 연산자 | 설명 |
|------|--------|------|
| **비트 연산자** | `&`, `|`, `^`, `~`, `<<`, `>>`, `>>>` | 비트 단위 연산 |

