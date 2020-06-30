# 모던 자바의 시작, Java 8

---
<!-- 헤더 -->

Java 8의 새로운 기능과 Java 8 도입을 위한 기초 가이드

- Java 버전 전환의 필요성
- Java 8 주요 기능 소개
- Java 8 전환 방법 소개

2020-07-01 (수) 13:20 ~ 13:40
솔루션연구팀 플랫폼연구담당 이상현

---
<!-- 섹션 -->


Java 버전 전환의 필요성

Java 8 주요 변화

Java 8 전환 방법

---

<!-- Java 버전 전환의 필요성 -->

## Java 버전 히스토리

* Java 8 출시 : **2014년**

* Java 9 이후로 6개월 마다 릴리즈 (3월, 9월)

|  Java 릴리즈  |  릴리즈 날짜   |
| :-----------: | :------------: |
|   Java SE 6   |   2006.12.23   |
|   Java SE 7   |   2011.07.28   |
| **Java SE 8** | **2014.03.18** |
|      Java SE 9       |   2017.09.21   |
|      Java SE 10      |   2018.03.20   |
| **Java SE 11** | **2018.09.25** |
|      Java SE 12      |   2019.03.19   |
|      Java SE 13      |   2019.09.17   |
|      Java SE 14      |   2020.03.17   |

---

* LTS: Long Term Support (↔ non-LTS)
* MTS: Medium Term Support

![oracle-java-support](https://imgur.com/IiiZvt0.png)

> 이미지 1-1. Oracle Java SE Support Roadmap (2020.05.13)
> 이미지 직접 캡쳐: [Oracle Java SE Support Roadmap](https://www.oracle.com/java/technologies/java-se-support-roadmap.html)

---

![LTS release chart](https://dzone.com/storage/temp/11772392-screen-shot-2019-05-02-at-41652-pm.png)

> 이미지 1-2. Oracle의 정책. 6개월마다 신규 버전 릴리즈, 3년마다 신규 LTS 버전 릴리즈
> 이미지 링크: [DZone: Beyond Java 8](https://dzone.com/articles/beyond-java-8)

---

* [Moving Java Forward Faster](https://mreinhold.org/blog/forward-faster) - [Mark Reinhold](https://mreinhold.org/)(오라클 자바 플랫폼 그룹 최고 아키텍트)

  > I propose that after Java 9 we adopt a strict, time-based model with a *new feature release every six months*, update releases every quarter, and a **long-term support** release *every three years*.

* JDK 측면

  * 빠른 기능 추가 (피드백, 딜레이 방지)
  * 유연한 표준 (프리뷰)
  * Cost

* 사용자 측면

  * 충격 완화 (모든 이해관계자 - 적응 및 준비)
  * 혁신 vs 안정성

---

## Mordern Java

Java 8에서 추가된 큰 변화를 때문에, Java 8 이전을 `클래식 자바` Java 8 이후를 `모던 자바`로 분류하기도 한다.

* 클래식 자바
* 모던 자바

![image-20200629103115369](https://github.com/norimsu/20200701-ceminar-java/raw/develop/2-%EB%AA%A8%EB%8D%98-%EC%9E%90%EB%B0%94%EC%9D%98-%EC%8B%9C%EC%9E%91%2C-Java-8.assets/image-20200629103115369.png)

> 이미지 검색: 도서 검색 "Modern Java"

---

## 성능

> 높은 버전의 JDK일 수록 컴파일의 최적화, JVM의 하드웨어 최적화나 GC 알고리즘의 개선 등을 통해 더 나은 성능을 보여준다.

![](https://cl4es.github.io/images/hellolambda.png)

> 이미지 1-3. 버전이 증가할 수록 최적화가 이루어진다.
> 이미지 링크: [OpenJDK Startup From 8 Through 11](https://cl4es.github.io/2018/11/29/OpenJDK-Startup-From-8-Through-11.html)

---

## 라이브러리

> 라이브러리들도 자바 버전의 상승에 따라 최소 지원 버전이 상승하고 있다.

* Maven 3.3+ - 최소 Java 1.7 이상
* Gradle - 기본 Java 8 이상 구동
* Spring 5 - 최소 Java 8 이상
* 클라우드 서비스 ([MS Azure](https://docs.microsoft.com/ko-kr/azure/developer/java/sdk/java-sdk-azure-get-started), [AWS](https://aws.amazon.com/ko/sdk-for-java/)) - Java 8+

> [스프링 5 피드백](https://spring.io/blog/2015/06/10/feedback-welcome-spring-5-system-requirements) 내용 中
>
> "우리는 JDK 8+로 최소값을 올릴 것입니다.
> 이는 프레임워크 전반에 걸쳐 보다 깨끗한 코드 기반을 구축하고, 핵심 인터페이스에 기본 메서드 구현을 도입하며, 우리의 코어 추상화에서 JDK 8 API(예: Completetable, java.util.function 인터페이스)에 의존할 수 있기 때문에 필수 조건입니다.

---

## 문제점은?

> Java 9부터 제거된 API들이 존재하고, 모듈 방식을 지원하면서 코드 작성이 필요한 부분이 발생한다.

* Java 8은 거의 모든 OS 에서 지원한다. Java 9은?
* Java 9의 모듈 시스템 (Project Jigsaw)
* Java 9, 10 에서 제거된 deprecated API

![](http://cr.openjdk.java.net/~mchung/jigsaw/graphs/jdk8-b48-nobase.png)

> 이미지 1-4. 너무 커져버린 `rt.jar`. 향후 project jigsaw를 통해 격리된 모듈별로 참조할 수 있도록 개선됨.
> 이미지 링크: [https://openjdk.java.net/projects/jigsaw/](http://openjdk.java.net/projects/jigsaw/doc/jdk-modularization.html)

---

## 버전?

![image-20200701032206564](https://raw.githubusercontent.com/norimsu/20200701-ceminar-java/develop/2-%EB%AA%A8%EB%8D%98-%EC%9E%90%EB%B0%94%EC%9D%98-%EC%8B%9C%EC%9E%91%2C-Java-8.assets/image-20200701032206564.png)

> 이미지 1-5. 어떤 버전의 자바가 많이 사용될까? 3/4의 개발자가 Java8을 사용한다.
> 이미지 직접 캡처 : [JetBrains: 2020년도 개발자 에코시스템의 현황](https://www.jetbrains.com/ko-kr/lp/devecosystem-2020/java/)

**Java 8의 호환성**

* 바이너리 호환성
  * 기본적으로 Java SE 7 컴파일러로 작성된 클래스 파일은 Java 8에서 실행됩니다.
* 소스 호환성
* 동작 호환성
  * Java 8은 하위호환성을 (대체로) 보장하므로, 동작의 오류는 사용중인 라이브러리의 문제이거나 기존 코드에서도 발생할 수 있었던 잠재적인 문제일 가능성이 있다.

> [Compatibility Guide for JDK 8](https://www.oracle.com/java/technologies/javase/8-compatibility-guide.html)

---



<!-- -->

---

# New Feature

[What's New in JDK8](https://www.oracle.com/java/technologies/javase/8-whats-new.html)

## Interface의 변화

> 자바 인터페이스에서도 구현 메서드를 작성할 수 있게 되었다.

* defaut method
* static method

```java
public interface Vehicle {

    String getBrand();

    String speedUp();

    String slowDown();

    default String turnAlarmOn() {
        return "Turning the vehice alarm on.";
    }

    default String turnAlarmOff() {
        return "Turning the vehicle alarm off.";
    }

    static int getHorsePower(int rpm, int torque) {
        return (rpm * torque) / 5252;
    }
}
```

---

>전환 방법

* 자식 클래스마다 중복되는 코드 정리

* 의미 없는 추상 클래스 패턴 제거

---

>전환시 고려사항

* 다중 상속 관계

![](https://upload.wikimedia.org/wikipedia/commons/thumb/8/8e/Diamond_inheritance.svg/440px-Diamond_inheritance.svg.png)

> 이미지 2-1. 다중 상속이 되서 어떤 메소드를 참조해야 하는지 판단할 수 없다면 컴파일 에러가 난다.
> 이미지 링크 : [Wikipedia: Multiple inheritance](https://en.wikipedia.org/wiki/Multiple_inheritance)

## Lambda Expression

> 익명 내부 클래스를 축약하여 표현할 수 있는 방법이 추가되었다.

* 함수형 인터페이스 : 추상 메서드를 1개만 가지고 있는 인터페이스
  * 신규 어노테이션 : `@FunctionalInterface` - 의도와 다른 변경시 컴파일 에러 유발
* 메서드 레퍼런스 : `ClassName::methodName` 
  * 신규 연산자 : `::`
  * 생성자 레퍼런스 : `ClassName::new`
* Lambda Expression은 함수형 인터페이스인 경우에만 적용이 가능하다.

```java
// 일반적인 코드
Runnable runnable = new Runnable() {
    @Override
    public void run(){
        System.out.println("Hello world !");
    }
};

// use Lambda Expression
Runnable runnable = () -> System.out.print("Hello world!");
```

---

> **전환 방법**

* 익명 클래스를 사용하는 부분

---

## Stream

> Stream API 의 도입으로 선언적 프로그래밍이 가능해졌다.
>
> * 생성
>   * 순차 `stream`
>   * 병렬 `parallelStream`
> * 파이프라인
>   * 중간 연산
>   * 최종 연산

```java
list.stream()								// 생성
    .filter(name -> name.startWith("f"))	// 필터링
    .map(String::toUpperCase)				// 변환
    .sorted()								// 정렬
    .forEach(System.out::println);			// 모두+출력 (최종 연산에서 Lazy하게 실행)
```

---

> **전환 방법**

* 반복, 추출, 검색, 확인, 검증 등 모든 상황에서

---

> **전환시 고려사항**

* `Fuctional in nature` - 데이터 소스를 변경하지 않음
* 오직 한번만 처리 - 재사용이 불가
* 성능상의 이득을 보장하지는 않음

---

## Optional\<T>

>빈 객체 (null)을 판단 할 수 있는 새로운 기능이 추가되었다.
>`Optional<T>`는 비어 있을 수도 있고 무엇인가를 담고 있을 수도 있는 객체다.

* 기존 자바에서 `null` 사용으로 발생할 수 있던 문제들
* `java.util.Optional<T>`이 추가됨으로써, 문제를 해결하는 쉬운 방법이 제시됨

```java
// 일반적인 코드
String text = getSomeText();
int length;
if (text != null) {
    length = text.length();
} else {
    length = 0;
}
```

```java
// Optinal을 사용했지만 이렇게 사용하면 결국 일반적인 코드와 같은 상황
String text = getSomeText();
Optional<String> maybeText = Optional.ofNullable(text);
int length;
if (maybeText.isPresent()) {
	length = maybeText.get().length();
} else {
	length = 0;
}
```

```java
// Optinal, Method chain, 메소드 참조 등을 활용
int length = Optional.ofNullable(getSomeText())
    .map(String::length)
    .orElse(0);
```

---

> **전환 방법**

* `null`을 반환하는 부분
* 예외가 발생하는 부분

---

> **전환시 고려사항**

* 오버헤드가 있음
* 리턴하는 경우에 한해서 사용하는 것이 기본
  * 매개변수나 지역변수로 사용하는 것은 지양

---

## Date-Time

> 기존의 Date, Calendar를 대신하는 새로운 날짜, 시간 API가 추가되었다.
> [JSR-310](https://jcp.org/en/jsr/detail?id=310) 구현체

* 기존 API의 설계 결함
* 쉽게 간단하게 날짜와 시간을 정의하는 새로운 API

```java
LocalDate 			// 날짜
LocalTime 			// 시간
LocalDateTime 		// 날짜 + 시간
ZonedDateTime 		// 날짜 + 시간 + 타임존
Instance 			// 기계의 시간 1970.01.01. 00:00:00 이후
Duration			// 시간 기간 (nano second)
Period				// 날짜 기간 (year, month, day)
DateTimeFormatter 	// 문자열 변환
```

```java
LocalDate localDate = LocalDate.now();

LocalDate.of(2020, 07, 01);
LocalDate.parse("2020-07-01");
```

```java
LocalTime now = LocalTime.now();

LocalTime thirteenThirty = LocalTime.parse("13:30");
LocalTime thirteenThirty = LocalTime.of(13, 30);
```

---

>**전환시 고려사항**

* 기존에 사용 중인 라이브러리에서 계속 legacy API 를 사용한다면 우선 호환성 확인이 필요
* 전환하는데 비용이 크게 발생하지 않는다면, 지속적으로 활용될 영역부터 전환을 고려

---

# JVM

기존 HotSpotVM(Java 7 까지)에서 OOM을 방지하기 위해 작성해주어야 했던 JVM 옵션은 아래와 같았다.

```properties
-XX:PermSize=N
-XX:MaxPermSize=N
```

---

>  HotSaptVM 8 에서 Metaspace 영역이 새로 추가되었다.

Java 8 HotSpotVM에서는 Permernant  Heap 영역은 사라지고 Metaspcace 영역이 생겼다.

> **Perm 영역**은 보통 Class의 Meta 정보나 Method의 Meta 정보, Static 변수와 상수 정보들이 저장되는 공간으로 흔히 메타데이터 저장 영역이라고도 한다. 이 영역은 Java 8 부터는 Native 영역으로 이동하여 **Metaspace 영역**으로 변경되었다. (다만, 기존 Perm 영역에 존재하던 Static Object는 Heap 영역으로 옮겨져서 GC의 대상이 최대한 될 수 있도록 하였다)

|                          | Java 7                               | Java 8                                         |
| ------------------------ | ------------------------------------ | ---------------------------------------------- |
| Class 메타 데이터        | 저장                                 | 저장                                           |
| Method 메타 데이터       | 저장                                 | 저장                                           |
| Static Object 변수, 상수 | 저장                                 | Heap 영역으로 이동                             |
| 메모리 튜닝              | Heap, Perm 영역 튜닝                 | Heap 튜닝, Native 영역은 OS가 동적 조정        |
| 메모리 옵션              | `-XX:PermSize`<br/>`-XX:MaxPermSize` | `-XX:MetaspaceSize`<br/>`-XX:MaxMetaspaceSize` |

> 최근 Java 8에서 JVM 메모리 구조적인 개선 사항으로 Perm 영역이 Metaspace 영역으로 전환되고 기존 Perm 영역은 사라지게 되었다. Metaspace 영역은 Heap이 아닌 Native 메모리 영역으로 취급하게 된다. (Heap 영역은 JVM에 의해 관리된 영역이며, Native 메모리는 OS 레벨에서 관리하는 영역으로 구분된다) Metaspace가 Native 메모리를 이용함으로서 개발자는 영역 확보의 상한을 크게 의식할 필요가 없어지게 되었다.

![](http://equj65.net/wp-content/uploads/2014/05/java7-8HotSpotVM.jpg)

> 이미지 2-2. Metaspace 영역은 OS에서 관리하는 Native 영역이다.
> 이미지 링크 : http://equj65.net/tech/java8hotspot

---

> **전환 방법**

Java 8 환경에서의 메모리 관련 옵션은 다음과 같습니다.

```shell
$ Java \
-XX:+HeapDumpOnOutOfMemoryError \
-XX:HeapDumpPath=<<덤프 파일 위치>> \
-Xmx2048m \
-Xms1024m \
-XX:MetaspaceSize=256m \ 			#필요시
-XX:MaxMetaspaceSize=512m \			#필요시
...
```

> 모든 사이즈는 모니터링을 통해 적절한 값을 찾을 필요가 있습니다.

---

<!-- -->

---

# 전환 방법

* 사용하고 있는 도구(CI & CD, IDE, 분석도구 등)가 Java 8을 지원하는지 확인
* 사용하고 있는 라이브러리가 Java 8을 지원하는지 확인
* 제품이 JDK8로 컴파일되고 실행되는지 확인
* 가능하다면 JVM 모니터링 (G1GC, Full GC)을 통해 안정성을 확인
* Java8의 새로운 기능을 적용했다면 원하는 목적을 달성했는지 확인

![img](https://visualvm.github.io/images/visualvm_screenshot_20.png)

> 이미지 3-1. Visual VM

## 일반적인 방법

* [호환성 가이드](https://www.oracle.com/java/technologies/javase/8-compatibility-guide.html) 참고
* 새로운 코드는 Java 8로 작성
* 기존 코드는 Java 8로 컴파일
* 기존 바이너리는 JDK8 환경에서 실행

## 새로운 기능 적용

* 변경 대상 선정
* 목적과 최종 적용 여부 판단
  * 리펙토링
  * 유지보수성
  * 성능
* 목적에 부합하는지 테스트

---

> END









## 레퍼런스

https://www.baeldung.com/java-8-date-time-intro



# 라이센스

# 기술지원



