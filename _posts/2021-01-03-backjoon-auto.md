---
layout: posts
title: “백준파이썬 파일생성기”
categories:
  - 알고리즘
tags:
  - 알고리즘
  - 백준
---

백준풀때마다 느끼는건데 파일만들기 엄청 귀찮다.
해당파일을 파이썬으로 만들어준다음 폴더에서 터미널을 실행시켜보자

```
  python ().py
```
분명히 파이썬이깔려있는데도 안되는경우가있는데
그럴땐 python3로 해보자

필요한건 

```
  pip install requests bs4
```
이것도 안된다면 pip3라고 쳐보자
그럼 백준 문제번호만 친다면 쨔짠하고 파일을 만들어준다 
그럼이만

```
  import requests
  from bs4 import BeautifulSoup as bs

  while True:
      print("set directory")
      m_dir = input()
      token = ""
      print("current directory")
      print(m_dir)
      while True:
          print("enter number,! to quit")
          p = input()
          if p == "!":
              break
          if not p.isdigit:
              print("error")
              continue
          req = requests.get('https://www.acmicpc.net/problem/'+p)
          html = req.text
          soup = bs(html, 'html.parser')
          title = soup.select(
              '#problem_title'
          )[0].contents[0]

          filename = p+"_"+title+".py"
          print(filename)
          f = open(m_dir+'/'+filename, 'w')
          f.close
```
