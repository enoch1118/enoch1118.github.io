```
---
layout: posts  
title: react-native(1)
category: react-native 
---
```





# React-Native(1)

> 우분투 환경에서 React-native 환경 만들기

일단 mac 과 ubuntu 컴퓨터 두대가 있는데다가 내가 마음대로 쓸수 없는 환경이기때문에 어떤컴퓨터에 뭐가 깔려있는지 약간 헷깔리는 상태

yarn 설치가 mac 에는 되어있는데 ubuntu 에서 yarn 을 설치하면 add 명령어를 인식을 못하는 이상한 상황이 생김

왜인지는 잘모르겠지만 

`apt remove yarn`

`apt remove cmdtest`

한다음에 다시 

```
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
```

```
sudo apt update && sudo apt install yarn
```

이렇게 해주니깐 문제가 해결됨 

다른건 뭐 인터넷에 다나와있으니깐 패스



