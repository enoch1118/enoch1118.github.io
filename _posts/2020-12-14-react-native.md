---
layout: posts  
title: react-native(1)
category: react-native 
---


# React-Native(1)


* 렌더

리액트는 뷰를 업데이트 할때 그저 새로운 요소가있을경우 그부분만 갈아끼운다.
이부분을 수행하는것이 render 

<br>render 함수는 DOM에 결과를 반영하기전. 컴포넌트를 비교 결과를 출력해준다.

* DOM

Document Object Model 
> 객체로 문서 구조를 표현하는 방법 XML 이나 HTML 로 작성 
> <br> 동적 ui에서 최적화 되어있지않은 정적인것.
> <br>리액트에서는 Virtual DOM 방식을 사용 DOM 업데이트를 추상화하여 효율적이게 동작

* 특징

리액트는 정말 뷰만을 신경쓴 프레임워크이기때문에 라이브러리를 사용해야한다.

라우팅->react-router
Ajax->axios fetch
상태관리->redux MobX


___
시작하기(JSX)

리액트에서 사용하는 JSX는 브라우저가 실행되었을때 코드를 자바스크립트로 변환해준다.
> * 몇가지 규칙
> <br>컴포넌트안의 요소들은 하나의 부모요소로 감싸져있어야한다.(<Fragment>,<>)
> <br>JSX내의 자바스크립트를 사용할땐 {}를 이용하면된다.
> <br>if문대신에 조건부연산자를 사용하자
> <br>{~~?():()}
> <br>&&을 이용해서 조건부 렌더링을 할수있다
> <br>{조건&&렌더링대상}
> <br>undifined를 리턴할수없다.
> <br>스타일은 카멜표기법을 사용한다.
> <br>class 대신 className을 사용한다.
> <br>태그는 꼭 닫아주어야 한다.
> <br>JSX 내부 주석은 {/**/}으로 사용

___
컴포넌트

* 클래스형? 함수형?
둘의 기능은 같다고 말할수있지만 클래스형 함수는 state기능과 라이프사이클 기능을 사용할수있고 임의 메서드를 정의할수 있다  

* 함수형
> 편리한 선언, 적은 메모리자원, 작은 파일크기
> Hooks 라는 기능으로 state와 비슷하게 동작이 가능하긴 하다.
> 현재 리액트 공식 매뉴얼에서는 hooks의 사용을 권장하고있다.

* 화살표함수.
function()  this.는 자신이 종속된 객체의 this를 가르킨다
  ()=>      this.는 자신이 종속된 인스턴스를 가르킨다.
  
높은가독성.
```java
const triple = (value)=>value*3
```

> vscode에서 reactjs code snippet 플러그인을 설치하면 새로운 컴포넌트에서
> rsc rcc로 빠르게 작성할수있다

 

  