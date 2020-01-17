# [코틀린] Kotlin GUIDE
본 문서의 오류나 오타가 있다면 이메일(itggood2420@gmail.com)로 연락주세요.
<a id="index"></a>
# 1. 목차

1. [목차](#index)
2. [개요](#summary)
    1. [장점](#advantages)
    2. [주의사항](#precautions)
    3. [Java와 다른점](#different-from-java)
    4. [활용분야](#field)
    5. [로고](#logo)
    6. [버전](#version)
3. [Hello World 예제](#hello-world-exam)
4. [코틀린 입출력 메서드](#kotlin-io-method)
    1. [출력](#output)
    2. [입력](#input)
    3. [문자열 템플릿](#output-in-specified-format)
5. [기본 문법](#basic-grammar)
    1. [주석](#remark)
    2. [자료형](#data-type)
    3. [변수](#variables)
    4. [상수](#constant)
    5. [조건문](#conditional-statement)
    6. [반복문](#loop-statement)
    7. [함수](#method)
    8. [Null 안전](#null-safety)
    9. [예외처리](#exception)
    


<br/>

<a id="summary"></a>
# 2. 개요
    JetBrains에서 2011년에 공개한 프로그래밍 언어이다.
    JVM 기반의 언어이며, Java와의 상호 운용이 100% 지원된다.
    문법이 Java보다 간결하다.
    2017년에 구글이 안드로이드의 공식 언어로 추가하여 많은 관심과 사랑을 받아오고 있다.



<a id="advantages"></a>
## 1. 장점
    실용성
        Java의 불편한 점들을 개선한 언어이다.

    간결성
        코틀린은 간결한 문법을 가지고 있다.

    경제성
        코틀린은 오픈 소스이다.

    이해성
        코틀린의 문법은 이해하기 쉽다.

    코틀린은 함수형 프로그래밍이 가능하다.
    안드로이드 개발을 할때 Anko 라이브러리를 사용하면 코드를 줄일 수 있다.
     
<a id="precautions"></a>
## 2. 주의사항
    코틀린에서의 ;(세미콜론)
        코틀린에서 ;(세미콜론)은 두 문장을 작성할 때 사용합니다.
        즉, 코틀린에서 ;(세미콜론)은 필수가 아닙니다.
    
<a id="different-from-java"></a>
## 3. Java와 다른점

Java에서는 함수(method)가 class안에 있어야합니다.
하지만 Kotlin에서는 꼭 class안에 있을 필요가 없습니다. 그냥 함수만 사용해도 됩니다.

Java에서의 함수 사용법
```java
public class Exam {
    public static void main(String[] args) {

    }
}
```
Kotlin에서의 함수 사용법
```kotlin
fun main(args: Array<String>) {

}
```

<a id="field"></a>
## 4. 활용분야
    Android
    Spring
    JavaScript
    HTML5
    ios
    Java EE
    Raspberry PI

<a id="logo"></a>
## 5. 로고
![](https://w.namu.la/s/3ff8fb808d84672e56b8e38de0b98b2985080f2b83cec3ed465563c3b7bb9b26dfe74c7d2f4e5d155fcdbef8162c840b45b08fe094c1d168632cf95cff2182de2df85ca67ddf6710d55267737c5c014323116736d54e180aba5dec2c1768a528)

<a id="version"></a>
## 6. 버전
    현재 최신 버전 : 1.3.21

<br/>

<a id="hello-world-exam"></a>
# 3. Hello World 예제
```kotlin
fun main() {
    println("Hello, World!")
}
```
<br/>

<a id="kotlin-io-method"></a>
# 4. 코틀린 입출력 메서드

<a id="output"></a>
## 출력

kotlin에서 출력은 print를 사용합니다.
```kotlin
fun main() {
    print("Kotlin!")
}
```
출력 결과
```
Kotlin!
```
<br/>

print는 개행(아래 줄로 내리는 것)을 하지 않고 출력해줍니다.
```kotlin
fun main() {
    print("Kotlin!")
    print("Kotlin!")
    print("Kotlin!")
}
```
출력 결과
```
Kotlin!Kotlin!Kotlin!
```
<br/>

자동으로 개행을 하고싶다면 println을 사용하면 됩니다.
```kotlin
fun main() {
    println("Kotlin!")
    println("Kotlin!")
    println("Kotlin!")
}
```
출력 결과
```
Kotlin!
Kotlin!
Kotlin!
```

<br/>

<a id="input"></a>
## 입력

Kotlin에서 입력은 Java와 비슷합니다.
Scanner 객체에 System.in을 넣어서 생성한 인스턴스를 사용합니다.

하지만 코틀린에서 [in 연산자](#in-operator)가 따로 있기 때문에 in을 `(그레이브 액센트)로 감싸줍니다.
```kotlin
import java.util.Scanner

fun main() {
    val scanner = Scanner(System.`in`)

    println(scanner.nextInt())
}
```

입력
```
7
```

출력
```
7
```

<br/>

하지만 nextInt() 메서드는 정수형만 받을 수 있습니다. 문자열이나 문자를 받고 싶다면 nextLine() 메서드를 사용하시면 됩니다.

```kotlin
import java.util.Scanner

fun main() {
    val scanner = Scanner(System.`in`)

    println(scanner.nextLine())
}
```
입력
```
Apple
```

출력
```
Apple
```
<br/>

Scanner에서 사용하는 주요 메소드의 종류는 다음과 같습니다.

|  <center>메소드(Method)</center> |  <center>설명</center> |
|:--------|:--------:|
|**nextByte()** | <center>Byte 타입으로 리턴</center> |
|**nextShort()** | <center>Short 타입으로 리턴</center> |
|**nextInt()** | <center>Int 타입으로 리턴</center> |
|**nextLong()** | <center>Long 타입으로 리턴</center> |
|**nextFloat()** | <center>Float 타입으로 리턴</center> |
|**nextDouble()** | <center>Double 타입으로 리턴</center> |
|**next()** | <center>String 타입으로 리턴</center> |
|**nextLine()** | <center>'\n'을 포함한 한 문장을 읽고<br/> '\n'을 버린 문자열을 String 타입으로 리턴</center> |

<br/>
<a id="output-in-specified-format"></a>

## 문자열 템플릿

Kotlin에서는 문자열 템플릿을 제공합니다. $나 ${}로 사용가능 합니다.

```kotlin
fun main() {
    val name = "ImTae"

    println("Nice to meet you, $name !")
}
```
출력 결과
```
Nice to meet you, ImTae !
```
<br/>


```kotlin
import java.util.Scanner

fun main() {
    val scanner = Scanner(System.`in`)

    println("Nice to meet you, ${scanner.nextLine()}!")
}
```

입력
```
ImTae
```

출력 결과
```
Nice to meet you, ImTae!
```
<br/>
<a id="basic-grammar"></a>

# 기본 문법

<a id="remark"></a>

## 주석

Kotlin에서 주석 사용법은 Java와 동일하게 //을 사용합니다.

```kotlin
fun main() {
    println("안녕하세요. 이것은 주석이 아닙니다.")
    //println("안녕하세요. 이것은 주석입니다.")
}
```

<br/>
<a id="data-type"></a>

## 자료형

|  <center>정수 자료형</center> |  <center>크기</center> |
|:--------|:--------:|
|**Byte** | <center>1 Byte</center> |
|**Short** | <center>2 Byte</center> |
|**Int** | <center>4 Byte</center> |
|**Long** | <center>8 Byte</center> |
<br/>

|  <center>실수 자료형</center> |  <center>크기</center> |
|:--------|:--------:|
|**Float**| <center>4 Byte</center> |
|**Double**| <center>8 Byte</center> |
<br/>

|  <center>문자 자료형</center> |  <center>크기</center> |
|:--------|:--------:|
|**Char**| <center>2 Byte</center> |
<br/>

|  <center>문자열 자료형</center> |  <center>크기</center> |
|:--------|:--------:|
|**String**| <center></center> |
<br/>

\+ 자료형에 별명을 붙일 때에는 typealias를 사용하면됩니다.

```kotlin
typealias Human = String

val name: Human = "ImTae"
```

<br/>
<a id="variables"></a>

## 변수

Java에서는 " 자료형 변수이름 " 형태를 사용하지만, Kotlin에서는 " var 변수이름 : 자료형 " 형태를 사용합니다.

```kotlin
fun main() {
    var name: String = "ImTae!"
}
```

<br/>
<a id="constant"></a>

## 상수

kotlin에서 상수는 자바의 final 변수의 개념과 같습니다. 따라서 한번 초기화 해주면 값이 바뀌지 않습니다. <br/>
" val 변수이름: 자료형 " 형태를 사용합니다.

```kotlin
fun main() {
    val name: String = "ImTae!"
}
```

<br/>
<a id="conditional-statement"></a>

## 조건문

### if-else

if-else 조건문은 다른 언어와 동일합니다.

```kotlin
fun main() {
    val num = 77

    if (num >= 90) {
        println("90점이 넘어요!")
    } 
    else {
        println("90점 보다 낮아요!")
    }
}
```

출력 결과
```
90점 보다 낮아요!
```
<br/>

```kotlin
fun main() {
    val num = 77

    if (num >= 90) {
        println("90점이 넘어요!")
    }
    else if (num >= 70) {
        println("70점이 넘어요!")
    }
    else {
        println("재시험이 필요해요!")
    }
}
```

출력 결과
```
70점이 넘어요!
```
<br/>

### switch-case

switch-case 조건문 또한 동일합니다.

```kotlin
fun main() {
    val num = 7

    switch(num) {
        case 1:
        println("숫자가 1입니다.")
        break;

        case 7:
        println("숫자가 7입니다.")
        break;

        default:
        println("모르겠어요!")
    }
}
```
출력 결과
```
숫자가 7입니다.
```
<br/>

### when

코틀린에는 when 조건문이라는 것이 있습니다. switch-case와 같다고 보시면 됩니다.

```kotlin
fun main() {
    val name = "임태"

    when(name) {
        "임태" -> println("안녕하세요! 임태님!")
        "성범" -> {
            println("안녕하십니까?")
            println("이성범님!")
        }
        else -> {
            println("누구시죠?")
        }
    }
}
```

출력 결과
```
안녕하세요! 임태님!
```
<br/>

when 조건문을 아래와 같이 쓸수도 있습니다.
```kotlin
fun main() {
    val name = "임태건"
    
    val num = when(name) {
        "임태건" -> 7
        else -> 1
    }

    println(num)
}
```

출력 결과
```
7
```

<br/>
<a id="loop-statement"></a>

## 반복문

