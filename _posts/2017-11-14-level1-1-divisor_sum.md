---
layout: post
title: Level1 약수의합
categories:
   - Python
tags:
   - python
   - programmers
   - 알고리즘
   - 파이썬

#프로그래머스 <b style="font-size:20px">https://programmers.co.kr</b><br><b style="font-size:20px; color:#71717991;">Code_Challenge </b><br><b>Level1 약수의 합</b>
---
[TOC]
####문제
![](http://MasterHun.github.io/img/all_sum_l1.jpg)

~~~
약수의 합
	- 어떤 수를 입력받는다.
	- 어떤 수의 약수를 모두 더한 수를 리턴하는 함수를 만들어라.
	- 예를 들어 12가 입력 된다면 12의 약수 [1,2,3,4,6,12]의 합인 28을 리턴하면 된다.
~~~
####==어떻게?==
- <b>"약수"란 어떠한 정수를 나머지 없이 나눌 수 있는 수를 말한다.</b>
- 약수를 어떻게 구할 것인가? 
	- 1에서 부터 입력 받은 숫자의 크기만큼 증가시켜 나누었을 경우 떨어지는 숫자를 저장한다.
    - 나눈 값을 sum = sum + a 의 형식으로 더해준다.
- 리스트 컴프리헨션을 이용하여 <b>[변수+i for i in range(1,num+1) if num%i==0]</b> 이런 느낌적인 느낌이다.
<br>

####==나의 풀이==
~~~python
def sumDivisor(num):
    sum1=0
    answer = [sum1+i for i in range(1, num+1) if num%i==0]
return sum(answer)
~~~
<br>

####==다른 사람의 풀이==
~~~python
def sumDivisor(num):
    return num + sum([i for i in range(1, (num // 2) + 1) if num % i == 0])
~~~
~~~python
def sumDivisor(num):
    return sum([i for i in range(1, num+1) if num % i == 0])
~~~
<br>

####==배운 점==
- sum을 사용하는 법에 있어서 쓸데없이 소모하였다는 생각이다.
- 리스트 컴프리헨션에 바로 sum을 적용하는 것이 코드에서는 더 수월하였다. 굳이 변수를 더 주지 않았어도 된다는 것이다.
- 약수를 구할때 항상 자신의 숫자의 /2의 초과 숫자들은 약수가 될수 없다는 점을 깨닫는다.
