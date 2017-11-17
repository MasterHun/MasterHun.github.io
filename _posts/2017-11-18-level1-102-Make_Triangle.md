---
layout: post
title: Level1 삼각형 출력하기
categories:
   - Python
tags:
   - python
   - programmers
   - 알고리즘
   - 파이썬
---
<b style="font-size:20px" url="https://programmers.co.kr">프로그래머스(programmers)</b><br>
<b style="font-size:20px; color:#71717991;">Code Challenge </b><br>
<b>Level1 삼각형 출력하기</b>

<h2 style="color:#819FF7">문제</h2>
![](http://MasterHun.github.io/img/Triangle_l1.jpg)



- <b>삼각형 출력하기</b>
	- 일반적으로 프로그래밍을 공부할 때 '별찍기' 라고 하는 일종의 기본 관문이 있다. 그것과 비슷한 방식이다.
    - INPUT으로 랜덤된 숫자가 들어오면 그 숫자에 대한 삼각형은 생성하는 것이다.


<h2 style="color:#819FF7">어떻게?</h2>
- <b>일반적인 별 찍기라 FOR 반목문을 이용한다면 쉽게 만들 수 있을 것 같다.</b>
- 파이썬에서는 print 문을 사용할때 개행이 되기 때문에 print문을 이용하기 위해서는 print("*",end=" ") 이런식으로 만들어 주어야 한다.(다음 라인으로 넘어가지 않겠다는 뜻이다.)<br>

<h2 style="color:#819FF7">나의 풀이</h2>

~~~python
def printTriangle(num):
    a=""
    for i in range(0,num):
        for j in range(0,i+1):
       	    a = a + "*"
        a = a+"\n"
    return a
~~~

~~~python
def printTriangle(num):
    b=[]
    for i in range(0, num):
        a=["*" for _ in range(0, i + 1)]
        a.append("\n")
        b = b+a
    return "".join(b)
~~~
<br>

<h2 style="color:#819FF7">다른 사람의 풀이</h2>
~~~python
def printTriangle(num):
    return ''.join(['*'*i + '\n' for i in range(1,num+1)])
~~~
~~~python
def printTriangle(num):
    s = ""
    for i in range(1,num+1):
        s=s+'*'*i+'\n'
    return s
~~~
<br>

<h2 style="color:#819FF7">배운 점</h2>
- 이중 FOR문을 사용하지 않아도 된다.
- 기존의 별찍기의 고정관념때문에 이중 FOR문을 사용해야 한다는 생각에 빠져있었던 것 이다.
