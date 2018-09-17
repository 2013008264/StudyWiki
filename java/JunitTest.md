# Junit test

Mvn project structure <br>
```
src
  |- main
  |- test
```
에서 test 안에 class 를 만든다.
그럼 class 의 path 는 just like below. <br>
> `{project path}/src/test/{class name}`
이 상황에서 {class name} 을 ClassName 이라 하자.

```java
import org.junit.Test;

public class ClassName {
  
  @Test
  public test0() {
    /*
        ... your tests..
     */
  }

  @Test
  public test1() {
    /*
        ... your tests..
     */
  }
}
```
이렇게 소스를 짜 주면, You can make simple junit test.
*****************************************

#### 이렇게 하면 기본적으로 당신은 test 를 만들 수 있다.
다른 Junit 에 있는 annotation 도 있는데, 상황에 따라 굉장히 쓸만하다.<br>

Before 은 class member 에 대해서, (여러 개의 test 에 대해서 공통적인 환경을 구축할 때) 사용하면 편하다.

```java
import org.junit.Before;
public class ClassName {
  
  private int common;

  @Before
  public before() {
    this.common = 10;
  }

  @Test
  public test0() {
    int tmp = this.common;
    /*
      your tests...
     */
  }

  @Test
  public test1() {
    int tmp = this.common;
    /*
      your tests...
     */
  }
}
```
After annotation 은 test 가 끝나고, 해야할 일들을 해주는 녀석이다.
```java
import org.junit.Before;
public class ClassName {
  
  private int common;

  @Before
  public before() {
    this.common = 10;
  }

  @Test
  public test0() {
    int tmp = this.common;
    /*
      your tests...
     */
  }

  @Test
  public test1() {
    int tmp = this.common;
    /*
      your tests...
     */
  }
  @After
  public after() {
    this.common = 100;
    system.out.println(this.common);
  }
}
```