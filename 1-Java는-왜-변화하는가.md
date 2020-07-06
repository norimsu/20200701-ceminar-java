# Java는 왜 변화하는가



---

Java의 변화를 통해서보는 우리의 변화

- Java의 입지
- Java의 위기
- Java의 진화

2020-07-01 (수) 13:00 ~ 13:20
솔루션연구팀 플랫폼연구담당 이상현 | 캐모마일 프레임워크 개발

---

Java의 입지

Java의 위기

Java의 진화





<!-- -->

---

## Java의 특징

> * 객체 지향 언어
> * 높은 이식성
> * 메모리 관리의 이점
> * 풍부한 라이브러리 생태계

**Java**는 시작부터 유용한 라이브러리를 제공하는 잘 설계된 객체 지향 언어로 시작했습니다.

**객체 지향 언어**는 캡슐화를 통해 소프트웨어 엔지니어링적인 문제를 최소화 할 수 있었고, 객체 지향적인 패러다임은 상대적으로 *WIMP* 프로그래밍 모델에 쉽게 대응이 가능했습니다.

**Java**는 **WORA** (`Write once, run anywhere`) 라는 슬로건에 걸맞게 다양한 장치에서 표준 바이트코드로 컴파일이 되고, 해당 바이트코드를 다시 컴파일할 필요없이 **JVM**이 설치 된 모든 환경에서 실행할 수 있도록 지원했습니다.

메모리 관리 측면에서 **Java**는 사용하고자 하는 객체를 필요한 시점에 자동으로 로딩할 수 있고 사용하지 않는 데이터는 GarbegeCollector(GC)에 의해 자동으로 메모리상에서 해제해서 관리해줍니다.

기본적으로 Java가 제공하는 표준 라이브러리도 풍부하지만 추가적으로 매우 많은 라이브러리가 있습니다. 그리고 Maven이나 Gradle 같은 도구를 통해 쉽게 빌드가 가능합니다.

---

## Java의 인기

> * 세계 및 국내 점유율
> * 개발자 구인 통계

* TIOBE INDEX  2위 (2020.06)

<img src="https://i.imgur.com/ycJ8xxZ.png" style="max-height:500px; max-width:1000px;" />

> 이미지 직접 캡처: [https://www.tiobe.com/tiobe-index/](https://www.tiobe.com/tiobe-index/)

---

* 구인공고
  * 사람인 검색 결과

<img src="https://github.com/norimsu/20200701-ceminar-java/raw/develop/1-Java%EB%8A%94-%EC%99%9C-%EB%B3%80%ED%99%94%ED%95%98%EB%8A%94%EA%B0%80.assets/image-20200629061932167.png" style="max-height:500px; max-width:1000px;" />

> 이미지 직접 캡처: 사람인

---

## Java의 2가지 측면

> * 언어로서의 자바
> * 플랫폼으로서의 자바

* Java Language

<img src="https://docs.oracle.com/javase/tutorial/figures/getStarted/helloWorld.gif" style="max-height:500px; max-width:1000px;" />

* Java Platform
  * JVM, Java API (JDK, JRE)
  * JVM 위에서 사용되는 언어 : Java, Kotlin, Groovy, Skala 등

<img src="https://docs.oracle.com/javase/tutorial/figures/getStarted/getStarted-jvm.gif" style="max-height:500px; max-width:1000px;" />

> 이미지 링크: https://docs.oracle.com/javase/tutorial/getStarted/intro/definition.html

---

<!-- -->

---

# 변화의 바람

> Java 를 위협하는 기술 트랜드
>
> * 빅데이터, 병렬처리, 분산처리
> * 간결한 코드를 사용하는 언어와 기술
> * 자바 표준의 실패

---

## BigData

* 1.0 부터 스레드 모델을 제공해 멀티 스레드 프로그래밍을 지원했지만  
  BigData(테라바이트 이상 데이터셋) 처리에 필요한 병렬 프로세싱에는 충분하지 못했다.

<img src="https://miro.medium.com/max/1400/1*crYMLTlfzREkCvyYRE6q1w.png" style="max-height:500px; max-width:1000px;" />

> 이미지 링크: https://towardsdatascience.com/programming-languages-for-data-scientists-afde2eaf5cc5

---

## Cloud Native

* CNCF 재단
  * 컨테이너 생태계를 확산하기 위해 만들어진 리눅스 재단 산하 단체
  * 상위 프로젝트 중 Java 언어로 이루어진 프로젝트나 Java 관련 프로젝트가 거의 없음

<img src="https://raw.githubusercontent.com/norimsu/20200701-ceminar-java/develop/1-Java는-왜-변화하는가.assets/landscape-1.jpg" style="max-height:500px; max-width:1000px;" />

> 이미지 직접 캡처: [cncf.io](https://landscape.cncf.io/)

---

# Java Ecosystem

* Java ME : Android 의 등장으로 사실상 입지가 사라짐
* 기존 EJB 같은 무거운 스펙은 거의 사용되지 않고 하락세
  * 대안 기술 및 패러다임의 변화에 Java 표준의 대응이 느림
* 자바를 위협하는 간결한 다른 언어들 (node.js, python, go 등)
* 릴리즈 주기가 길어 하위호환성 및 안정성이 높지만 **빠른 변화**에 대응하기는 어려움

| Java 릴리즈 | 릴리즈 날짜 |
| :---------: | :---------: |
|  Java SE 6  | 2006.12.23  |
|  Java SE 7  | 2011.07.28  |
|  Java SE 8  | 2014.03.18  |

---

<!-- -->

---

## 릴리즈

OpenJDK

* 기존에는 Oracle이 주도하는 OracleJDK → 이제는 커뮤니티 주도의 OpenJDK 가 메인

<img src="https://raw.githubusercontent.com/norimsu/20200701-ceminar-java/develop/1-Java%EB%8A%94-%EC%99%9C-%EB%B3%80%ED%99%94%ED%95%98%EB%8A%94%EA%B0%80.assets/image-20200701060744126.png" style="max-height:500px; max-width:1000px;" />

> 이미지 캡처 : [Java.next() : 박성철](https://www.slideshare.net/OracleDeveloperkr/main-session-java)

* 6개월마다 정기 릴리즈

<img src="https://dzone.com/storage/temp/11772392-screen-shot-2019-05-02-at-41652-pm.png" style="max-height:500px; max-width:1000px;" />

> 이미지 링크: [DZone: Beyond Java 8](https://dzone.com/articles/beyond-java-8)

---

## 스펙

Java 1.2에서 나눠졌던 스펙인 ME, SE,  EE를 다시 통합 -> SE 하나로

* Java ME : ...
* Java EE : 이클립스 재단 (Jakarta EE)
  * 클라우드 네이티브 지향

<img src="https://www.oracle.com/ocom/groups/public/@otn/documents/digitalasset/2167990.jpg" style="max-height:500px; max-width:1000px;" />

> 이미지 링크: https://docs.oracle.com/javase/8/docs/index.html

---

## 패러다임

|  버전   | 기능                | 패러다임                |
| :-----: | ------------------- | ----------------------- |
| Java 8  | 람다, 스트림        | 함수형 프로그래밍       |
| Java 9  | 모듈                | 경량화                  |
| Java 9  | Reactive Stream API | 반응형 프로그래밍       |
| Java 9  | JShell              | 인터프리터 언어 같이... |
| Java 9  | AOT 컴파일러        | 빠른 실행               |
| Java 10 | `var` 추가          | 지역 타입 추론          |
| Java 11 | HTTP Client 표준화  | 신규 표준               |
| Java 14 | `Record` 추가       | 데이터 프로그래밍       |

```java
// 신규 예약어 var
// Java SE 10 에서 강화된 타입 추론
BufferdReader reader = new BufferedReader(new FileReader(file));

var reader = new BufferedReader(new FileReader(file));

URL url = new URL("http://openjdk.java.net");
URLConnection conn = url.openConnection();
Scanner scanner = new Scanner(conn.getInputStream(), "UTF-8");

var url = new URL("http://openjdk.java.net");
var conn = url.openConnection();
var scanner = new Scanner(conn.getInputStream(), "UTF-8");
```

```java
// Java SE 14 에서 추가된 record
record Point(int x, int y) { }
record Rectangle(int length, int breadth) { }
```

---

## 플랫폼

>  GrallVM

* Java로 만들어진 Java 실행환경
* 고성능
  * JIT 컴파일러 및 메모리 구조

<img src="https://3.bp.blogspot.com/-ePS4BXWiiQU/W6oRErdDe1I/AAAAAAAAAao/xJPIE56lenwahwDbqm3OhFrDXaqX_a-KACLcBGAs/s640/GraalVsHotSpot.png" style="max-height:500px; max-width:1000px;" />

> 이미지 링크: [DZone: GraalVM Database Stream Performanc](https://dzone.com/articles/graalvm-database-stream-performance)

* 클라우드 지향 자바
  * 짧은 구동 시간, 적은 메모리 사용
    * 네이티브 컴파일을 통해 사전에 컴파일한 프로그램은 시작시간이 빨라지고 사용하는 메모리가 적다.
  * 서버리스, 마이크로서비스

<img src="https://www.graalvm.org/resources/img/ms_startup_time.png" style="max-height:500px; max-width:1000px;" />

> 이미지 링크: [graalvm.org](https://www.graalvm.org/docs/why-graal/)

* 폴리그랏 실행 환경
  * 다양한 언어를 제공하므로 다른 언어의 인기 라이브러리를 직접 호출하여 사용할 수 있고 다양한 언어로 작성된 코드를 함께 구동이 가능

<img src="https://www.graalvm.org/docs/img/graalvm_architecture.png" style="max-height:500px; max-width:1000px;" />

> 이미지 링크: [graalvm.org](https://www.graalvm.org/docs/)

---

<!-- -->

---

# References

> 라울-게이브리얼 우르마, 마리오 푸스코, 앨런 마이크로프트 저 / 우정은 역, ["모던 자바 인 액션"](https://www.yes24.com/Product/Goods/771259870), 한빛미디어 (2019) | 원제 : Morden Java in Action  
> 이일민, ["Java 9과 Spring 5로 바라보는 Java의 변화와 도전"](https://www.youtube.com/watch?v=BFjrmj4p3_Y&t=901s), Oracle Korea Youtube (2017.09.08)  
> Martin Reinhold, ["Java, Today and Tomorrow"](https://www.youtube.com/watch?v=Csc2JRs6470), Devoxx Youtube (2018.11.14)  
> 박성철, ["미래의 Java 미리보기 - 앰버와 발할라 프로젝트를 중심으로"](https://www.slideshare.net/OracleDeveloperkr/main-session-java), Oracle Korea SlideShare (2018.03.20)  
> 양수열, ["OpenJDK 새대 개막과 함께 Graalvm이 가지는 의미를 소개합니다"](https://www.youtube.com/watch?v=C6AQTky9ka4), Oracle Korea Youtube (2019.07.31)
> 김태완, ["GraalVM의 포지션과 역할에 대하여.."](http://taewan.kim/post/position_of_graalvm/), TAEWAN.KIM 블로그 (2018.06.16)  


> END
