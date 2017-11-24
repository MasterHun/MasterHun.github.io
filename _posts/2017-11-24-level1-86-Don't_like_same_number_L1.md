---
layout: post
title: Level1 같은 숫자는 싫어
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
<b>Level1 같은 숫자는 싫어</b>

<h2 style="color:#819FF7">문제</h2>
![](http://MasterHun.github.io/img/Don't_like_same_number_L1.png)



- <b>같은 숫자는 싫어</b>
	- 숫자로된 문자열을 인자로 받는다.
	- 반복되는 숫자를 제외하여 리스트로 리턴한다.


<h2 style="color:#819FF7">어떻게?</h2>
1. 문자열을 받아와서 index[0]번째 부터 차근차근 찾아간다.
2. 현제 index i에서 i+1 씩 하여서 비교연산자를 통하여 비교한 값을 리턴한다. (리스트 컴프리헨션 사용)

<h2 style="color:#819FF7">나의 풀이</h2>

~~~python
def no_continuous(s):
    # 함수를 완성하세요
    a = [s[i] for i in range(0, len(s)) if i+1!=len(s) if s[i]!=s[i+1] ]
    a.append(s[len(s)-1])
    return  a
print( no_continuous("11112420000"))
~~~
<br>

<h2 style="color:#819FF7">다른 사람의 풀이</h2>
<h4>`continue`를 사용한다. 이런 방법도 좋네.. ㅎㅎ</h4>
~~~python
def no_continuous(s):
    a = []
    for i in s:
        if a[-1:] == [i]: continue
        a.append(i)
    return a
~~~
<h4>아래의 풀이 값은 경우에는 파이썬의 세밀한 부분을 파고 들어간 것이라 할 수 있다.</h4><br>
~~~python
def no_continuous(s):
    return [s[i] for i in range(len(s)) if s[i] != s[i+1:i+2]]
~~~
<br>

<h2 style="color:#819FF7">배운 점</h2>
- 리스트에서 인덱싱을 하는 부분에 대해서 다시 학습해보자
~~~python
i = "12345"
#i의 인덱싱 할때의 최대 값은 i[4] 이다.
>>>i[4]
>>>'5'
#당연히 i[4] i의 4인덱스에 해당하는 값을 보여준다.
>>>i[4:]
>>>'5'
#4번째 인덱스 이상의 값들은 보여준다. (5가 마지막이기에 5까지만 출력)
>>>i[5:]
>>>''
#5번째 인덱스는 값이 없다. 그러나 5: 이렇게 인덱싱을 해주면 에러를 출력하지 않고 '' 빈 문자열을 리턴한다.
>>>i[5]
>>>IndexError
#그러나 없는 인덱스를 입력하면 IndexError 이 출력된다.
~~~
- 솔직히 리스트 컴프리헨션으로 한줄 코딩을 하려 하였지만 .. 인덱싱에 막혀버려서 두줄을 추가하는 아까움을 선사하였다.
- 아는 것이 힘이다. 이것이 핵심으로 생각된다. 잊지말자. 인덱싱

