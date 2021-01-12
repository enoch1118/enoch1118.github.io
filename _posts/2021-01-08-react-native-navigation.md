---
layout: posts  
title: react-native-navigation
category: 
    -react-native
tags:
    -react-native
---


###기본적인 것들.
```java
import { createStackNavigator } from '@react-navigation/stack';
import { NavigationContainer } from '@react-navigation/native';
```

*createStackNavigator
> const Stack = createStackNavigator();
> <br>Stack 을 이용해서 스택 생성
* NavigationContainer
> 네비게이션 최상위 컨테이너. 예제를 보면 전부 App.js에서 감싸주고있다
```html
<NavigationContainer>
      <Stack.Navigator initialRouteName="Home">
        <Stack.Screen name="Home" component={Home}
        options = {{title:''}}/>
        <Stack.Screen name="Browser" component={Browser}
        options = {{title:''}}/>
      </Stack.Navigator>
    </NavigationContainer>
```
> 구조는 맨위에 NavigatioContainer가 차지하고있고
> <br>그다음에 router 처럼 Stack.Navigatoer 를 사용하고있다.
> <br>라우터의 페이지처럼 Stack.Screen 을 사용한다.
> optios = {}를 통해 해당 페이지의 타이틀 등을 설정해 줄수있다.

