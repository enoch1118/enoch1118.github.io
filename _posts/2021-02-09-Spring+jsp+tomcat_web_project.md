---
layout: posts
title: Spring-spring+jsp+tomcat 웹프로젝트 1
categories:
- spring
tags:
- spring
- jsp
- tomcat
---
### Spring+JSP+tomcat 을 이용한 웹프로젝트 만들기 (intellj) 1



* File-New Project-Maven

![image-20210209151754996](https://i.loli.net/2021/02/09/safYRIo95C18XkO.png)

* 프로젝트 이름설정.

![image-20210209151945410](https://i.loli.net/2021/02/09/Vn1XtMNQohKE7lF.png)

* 프로젝트 이름에서 프레임워크 추가

![image-20210209152034793](https://i.loli.net/2021/02/09/MAwgk7lFruWznQX.png)

* Spring Mvc 선택

![image-20210209152139624](https://i.loli.net/2021/02/09/zQY18vVDRWpAsPj.png)

* 인텔리제이 우상단에 Project Structure 클릭

![image-20210209152238889](https://i.loli.net/2021/02/09/TzbEuvPLaW5h4Yq.png)

* Artifacts로 들어간다음 Available Elements 에서 두개의 스프링 라이브러리를 더블클릭해서 왼쪽으로 옮겨줍니다



![image-20210209152455610](https://i.loli.net/2021/02/09/mtuVT87YDIxziWJ.png)

* 적용한다음 OK

* 이제 서블릿 매핑을 바꿔볼텐데요 일단 프로젝트 창에서 web/web-inf/web.xml 클릭

![image-20210209152707137](https://i.loli.net/2021/02/09/vqVFAN1PfCln58j.png)

* 서블릿 매핑 부분의 url-pattern 을 /으로 바꾸어 줍니다

![image-20210209152756224](https://i.loli.net/2021/02/09/cMAZn9oKEWuPQsR.png)

* 그리고 dispatcher-servlet.xml의 설정을 바꾸어주어야 되는데요

![image-20210209153259033](https://i.loli.net/2021/02/09/CQxW2OwBXPzEvKA.png)

* 먼저 src/main/java에 자바 패키지를 한개 생성해주시고

![image-20210209153406714](https://i.loli.net/2021/02/09/mhf5IAHDG9YOgU1.png)

* dispatcher-servlet.xml로 와서 위에처럼 추가해주시면 됩니다

```xml
    <mvc:annotation-driven></mvc:annotation-driven>
    <context:component-scan base-package="com.springweb.common"/>

    <bean class="org.springframework.web.servlet.view.InternalResourceViewResolver">
        <property name="prefix" value="/WEB-INF/views/"></property>
        <property name="suffix" value=".jsp"></property>
    </bean>
```

* 윗부분 신경쓸거 없이 인텔리제이에선 mvc:ann정도까지만 쓰면 자동완성이 되면서 스키마 네임스페이스는 자동으로 추가되어서 위에 보이시는 코드만 추가하시면 됩니다.



* 그리고 프리픽스가 바뀌어졌기때문에 web에있던 index.jsp는 web-inf 에 views폴더를 만들어서 집어넣어 주시면 됩니다

![image-20210209153736208](https://i.loli.net/2021/02/09/zeiVcLrAOxTRZgk.png)

* 그리고 스프링에선 request가 되어지면 매핑된 자바클래스에서 return 을 해줘야 jsp가 열리기때문에 간단하게 클래스를 추가시켜주면 됩니다. 제가 강조한 부분이외에 부분은 전부 마음대로 이름을 지으셔도 상관없습니다.

![image-20210209154155833](https://i.loli.net/2021/02/09/iN9rFjXHfBxIbQl.png)

* 위에 임포트 부분은 자동으로 완성되기때문에 신경안쓰셔도되고 대충 루트 경로는 index.jsp가 된다 라는 뜻의 코드입니다!



* 이제 프로젝트 셋팅은 끝이났고 tomcat 서버와 maven 설정을 시작해봅시다!
  먼저 인텔리제이 우상단에 add Configuration 을 클릭!

![image-20210209154640737](https://i.loli.net/2021/02/09/GIW64v5sKSHkhQL.png)

* 플러스 버튼을 눌러서 tomcat-local 추가

![image-20210209154742307](https://i.loli.net/2021/02/09/bkST9BjAh7JwmxV.png)

![image-20210209154807124](https://i.loli.net/2021/02/09/Kc9hQw28SdugMq3.png)

* 만약 밑에 fix버튼이 보인다면 한번 클릭하시고 ok 하시면 끝!

* 이제 빌드해보시면 끝!



### 주의!

1. dispatchr-servlet.jsp 에서 <mvc:annotation-driven/> 를 작성할때 제대로 안보고 자동완성하시면!! 빌드할때 cache-manager 어쩌구 저쩌구 가 뜨면서 에러가 납니다 꼭 잘보시고 위에 xmlns:mvc 가 잘 생성되는지 확인!  확인방법은 url뒤쪽에 cache라고 적혀있는게 있으면 잘못된것!!

2. 분명 잘따라했는데도 빌드 이후에 404 가뜨시는 경우가 있는데 그건 원래 spring에서 jsp 를 지원을 해주지 않기때문이라고 하더라고요..
   근데 어쩔때는 그냥 되서 참 이상하긴 합니다만 이럴땐 프로젝트에서 pom.xml 로 가신다음에

![image-20210209155827609](https://i.loli.net/2021/02/09/zW1gV6T7XPpnHrB.png)

메이븐 설정을 해주시면됩니다

![image-20210209160124162](https://i.loli.net/2021/02/09/vCnDXmogWARz7hc.png)

이것 역시 자동완성 기능을 사용하면되는데요 문제는 버전!!
버전 선택 팁은

1. 배우고있는 책이나 따라하고있는 게있다면 그책 그대로 버전을 따라하시면되고
2. 먼저https://mvnrepository.com/ 로 접속!

![image-20210209160811249](https://i.loli.net/2021/02/09/4MngKQcjzsPvhCJ.png)

검색창에 groupid나 artifactsid를 치시면

![image-20210209160916689](https://i.loli.net/2021/02/09/PzB4feQjibrcxM2.png)

원하시는거를 선택

![image-20210209160949697](https://i.loli.net/2021/02/09/4ldSj5bqiCIQsAa.png)

usages가 가장 높은 버전을 사용하시면됩니다.
---