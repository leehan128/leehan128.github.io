# JAVA

자바는 다른 플래폼에서 실행되어도 프로그래머는 동일한 방식으로 언어를 기수랗ㅂ니다. 자바의 확장자는 `.java`이며 어떤 프로그램은 하나의 파일이지만 다른 프로그램은 수백개의 파일로 구성되어있을 수도 있습니다.

자바에 대해 아주 기본적인 것들은 제쳐둡시다.

### Compiling

![](https://s3.amazonaws.com/codecademy-content/courses/learn-java/revised-2019/Java+M1L1-+Compilation+Process+ART+409.png)

java의 컴파일러는 인간에게 친숙한 프로그래밍 언어를 기계에게 친숙한 기계어로 번역해주는 일을 합니다.

컴파일 과정은 코드를 번역하여 실행하기 전에 코드 내적인 실수를 잡아 우리에게 보여줍니다.

이러한 컴파일은 터미널을 사용할 수도 있습니다. 예를 들어 터미널에 `javac Placktom.java`라고 입력하면 그 파일에 대한 컴파일을 수행합니다.

성공적인 컴파일은 `Plankton.class`을 생성하며 터미널 명령으로 실행됩니다.

실패한 컴파일은 오류 목록을 생성합니다. 오류가 정정되고 컴파일 명령이 다시 실행될 때까지 .class 파일이 작성되지 않습니다.

### JAVA 기본 규칙

* JAVA 프로그램에는 하나 이상의 클래스와 하나의 `main()` 메소드가 있습니다. 각 class는 하나의 실제 아이디어를 나타냅니다. `main`은 실질적으로 프로그램의 작업을 실행합니다.
* JAVA 주석은 에디터에게 유용한 코멘트를 추가합니다. `//` 그리고 `/* */`
* JAVA의 공백은 사람이 쉽게 코드를 읽을 수 있도록 합니다.
* 중괄호는 class 및 메소드의 범위를 표시합니다.
* 세미콜론은 문장의 끝을 표시합니다.

### JAVA  변수

JAVA는 객체 지향이지만 모든 유형이 객체인 것은 아닙니다. 기본 요소라고 하는 기본 변수 유형 위에 구축됩니다.

다음은 JAVA의 모든 기본 변수타입 목록입니다.

**byte** (number, 1 byte)

**short** (number, 2 bytes)

**int** (number, 4 bytes)

**long** (number, 8 bytes)

**float** (float number, 4 bytes)

**double** (float number, 8 bytes)

**char** (a character, 2 bytes)

**boolean** (true of false, 1 byte)

자바는 정형화된 언어로서 우리가 변수를 사용하기 전에 반드시 미리 정의되어야 합니다.

float의 경우엔 사용하고 싶다면 캐스팅을 해줘야 합니다.

Ex)

```java
float f = (float) 4.5;
```

```java
flaot f = 4.5f;
```



char에 관한 사용은 C/C++과 별로 다를바 없습니다.

그러나 String은 기본이 아닙니다. 실제하는 type이지만 JAVA에는 String에 대한 특별한 처리가 있습니다.

문자열을 사용하는 방법은 다음과 같습니다.

```java
//Create a string with a constructor
String s1 = new String("Who let the dogs out?");
//Just using "" creates a string, so no need to wite it the previoes way
String s2 = "Who Who Who Who!";
//Java defined the operator + on Strings to concatenate
String s3 = s1 + s2;
//문자열을 Primitive에 연결할 수도 있습니다.
int num = 5;
String s = "I hava" + num + "cookies";
```

### == and equals

연산자 `==`은 equals과 약간 다르게 동작합니다. 객체를 사용하고, 객체가 같은지를 확인하고 싶을 때는 ==를 사용하고 논리적으로 같은지를 확인하고 싶을 때는 equals 메소드를 객체에서 사용해야 합니다.

```java
String a = new String("Wow");
String b = new String("Wow");
String sameA = a;

boolen r1 = a == b; //False, 두 객체는 같지 않습니다.
boolen r2 = a.equals(b); //True, 둘이 논리적으로 Wow로 같습니다.
boolen r3 = a == SameA; //True, 둘은 같은 객체입니다.
```

### Foreach

For 반복문의 또 다른 버전은 `Foreach`문입니다.

배열 내부의 요소를 반복하려면 간단히 사용할 수 있습니다.

```java
int[] arr = {2, 0, 1, 3};
for(int el : arr)
{
    System.out.println(el);
}
//위는 아래와 같은 결과입니다.
int[] arr = {2, 0, 1, 3};
for(int i=0; i<arr.length; i++)
{
    int el = arr[i];
    System.out.println(el);
}
```

### Functions

`Static` 이 메소드는 Main 클래스가 아니라 Main 클래스에 속함을 의미합니다. 이것은 다른 클래스에서 이 메소드를 호출할 수 있음을 의미합니다.

`void` 이 메소드는 값을 리턴하지 않음을 의미합니다. 그러나 return 메소드 자체를 사용하여 메소드를 종료할 수는 있습니다.

객체에서만 실행할 수 있는 메소드를 비정적 메소드라고 합니다. 비정적 메소드는 객체의 필드에 액세스하고 변경할 수 있습니다.

```java
//객체 생성
public class Student {
    private String name;
    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }
}
//비정적 메소드 사용
Student s = new Student();
s.setName("Danielle");
String name = s.getName();

Student.setName("Bob"); // Will not work!
Student.getName(); // Will not work!
```

모든 JAVA 메소드는 클래스 내에 있어야 합니다.

정적 메소드는 클래스에 속하고 비정적 메소드는 객체에 속합니다.

함수에 대한 모든 매개 변수는 값으로 전달되고 기본 내용은 복사됩니다. 그러나 객체는 복사되지 않으며 일부는 '참조로 전달'됩니다.