---
layout: post
title:  "아무거나 써보는 컴퓨터 상식01 - '|'의 기원을 찾아서"
date:   2021-01-13 02:07:29 +0900
categories: CS_About_Everything
---

# 사건의 발단
---
<br>
>안녕하세요
<br>
>직접적인 노드관련 질문은 아니지만 혹시 왜 |를 쓰게 됐는지 아시는 분 있나요?
<br>
> (예, 파이썬에서 ||의 경우 or로 쓰이는데 이유가 있을까요?) 갑자기 궁금해져서 질문합니다.
<br>
>저장하기 아이콘이 플로피디스캣 모양인것처럼 이 키의 사용이 유래가 있는 사용인지 궁금합니다!
<br>
>찾아봐도 사용법은 나오는데 언제부터 사용하기 시작했다는 글은 못찾겠네요.
<br>

기존에 있던 AIFFEL 1기 slack에서 AIFFEL 통합 slack으로 이사를 오게 되었는데, 2기 AIFFEL 학생분 중에 한 분이 이런 질문을 하셨다.  
이걸 딱 봤을 때 **"어..? 진짜 기원이 뭐지?"** 생각이 들었다.
<br>
<br>
생각해보면 수상하긴한게, **and**는 **&**가 기호로 자주 쓰이니까 그렇다고 해도, **or**은 도대체 왜 **|**를 쓰게 됐는지 아무리 생각해도 연관성을 찾아보기 어려웠다.
 <br>
 <br>
 모양도 전혀 비슷하지 않은데 이걸 왜 쓰기 시작했지? 생각이 들어 검색을 해봤다.
 <br>
 <br>

![image](/public/img/capture00.png){: width="50%" height="50%"}{: .center} 
<br>
_그당시 검색기록. 거의 3시간 정도 검색을 한거 같다. 스마트폰은 캡쳐하진 않았지만 친구랑 밥먹으면서도 찾다가 욕먹었다_
<br>
<br>

<br><br>
**그러던 중에 StackOverFlow에서 이 글을 발견했다.**
<br>
<br>
<https://stackoverflow.com/questions/15056896/why-is-the-symbol-for-or>

<br>
<br>
![image](/public/img/stackoverflow_about_or.png){: width="100%" height="100%"}{: .center}
<br>
<br>
일단 내용을 한줄 요약하자면, 포트란 창시자인 Backus가 프로그래밍 언어의 문법을 수학적인 수식으로 나타내기 위해 BNF(Backus–Naur form, 배커스-나우르 표기법)란 걸 만들었는데, 터미널 환경에서 요소를 나누기 위해 사용한 **|**가 굳어져 오늘날의 or이 되었다는 이야기.
<br>
<br>
\<BNF 예시 - RHS\>
<br>
>\<digit\> -> 0 \| 1 \| 2 \| 3 \| 4 \| 5 \| 6 \| 7 \| 8 \| 9

이런식으로 표기한다고 한다.
<br>
<br>
### 이후 시간순서를 이해하기 위해 알아보는 언어 출시순서 (C/C++)  
---
ALGOL58(IAL, 우리가 흔히 A언어라 부르는) -> ALGOL60 ->  CPL -> BCPL(Basic Combined Programming Language) ->  B -> C -> K&R C -> C with Classes(클래식 C++) -> C++ -> C++ 2.0 -> ANSI C/ISO C -> C++98 -> C99 -> C++03 -> C++TR1(여기부터 모던 C++) -> C++11/C11 -> C++14 -> C++17 -> C18 -> C++20   
-> (진행중) 
<br>
<br>
# 정리
---
1950년대부터 시간순으로 흐름을 정리해보자면 이렇다.
<br>
<br>
포트란 개발팀을 이끌 었던 John Warner Backus가 IBM에서 프로그래밍 언어 디자이너로 재직하던 당시, metalinguistic formulas로 새로운 프로그래밍 언어인 IAL의 문법을 기술하게 되는데, 이때 쓰인 metalinguistic formulas(문법무관 표기법)가 최초의 BNF이고, 이때 만든 IAL이 우리에게는 A언어라 알려진 ALGOL 58이다.
<br>
<br>
그런데 ALGOL58 때는 아직 **or** 연산자로 **v**를 사용했었고, ALGOL60에서 Naur가 표준 키보드에서 칠 수 있도록 몇몇 문자를 수정하게 되는데, __이때부터 |가 or로 쓰이기 시작한다.__
<br>
<br>
이 와중에도 기존 or 인 **v** 를 지원하기 위해 **\\** 와 **/** 를 조합해 **\\/** 이런식으로 사용할 수 있게 했다고 한다. (기존 유저를 배려하는 갓패치. 근데 불편해서 쓰긴 썼을까...?)
<br>
<br>
### 1964년 Article에서 확인할 수 있는 ALGOL 60에서의 표기법 변경 
---
![image](/public/img/algol60.png){: width="100%" height="100%"}{: .center}


<br>
<br>
### 논리연산자 || 의 기원
---
이후 시간이 흘러 1969년 B언어에서 bitwise 연산자와 논리연산자를 문맥으로 유추해서 일반적인 상황에서는 bitwise 연산자로, if나 조건문에서는 논리연산자로 사용해왔었는데,
<br>
<br> 
if (e1 | e2)
<br>
<br>
이 경우 논리연산자로 적용할건지, bitwise 연산자로 적용할건지를 헷깔리는 일이 많아져서, C언어가 나오면서 이부분을 고쳐서, 사용자들이 더 직관적으로 쓸 수 있도록 기존에 bitwise 연산자 **|**과 논리연산자 **||**를 분리해 사용하기 시작했다고 한다.
<br>
<br>
### The Development of the C Language 발췌
---
![image](/public/img/developement_c.png){: width="100%" height="100%"}{: .center}

<br>
이후에 C에 영감을 받은 현대 언어들이 연산자를 그대로 사용하면서, 비트연산자 | 와 논리연산자 ||가 대부분의 언어에서 사용하고 있다고 한다.
<br>
<br>
내가 자주쓰는 Python 같은 경우에는, **and**, **or** 과 **||**, **|**, **&**를 모두 지원하는데, 주의해야할 점이 연산자 우선순위가 다르다. (and , or이 | , || , &보다 뒤에 있어 예상과 다르게 나올 수도 있음)

# 후기
---
버그나 프로그래밍 스킬 관련 질문은 아니었지만, 오랜만에 호기심을 **강하게** 자극하는(?) 질문이었다.
정말 스쳐지나가듯 들은 A언어(ALGOL58,60)이나 BCPL, B언어도 겸사겸사 알게되었고, 유사전공인데 보면서 한번도 궁금하다고 생각하지 않았던 질문을 보니까 너무 내가 생각없이 외우기만 한건 아닌가 반성하게 됐다. 다음에도 재밌는 질문이 있었으면 좋겠다.
<br>

# refrerence
---
[ASCII character history](http://jkorpela.fi/latin1/ascii-hist.html#7C)
<br>
[B (프로그래밍 언어) - 위키백과](https://ko.wikipedia.org/wiki/B_(%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D_%EC%96%B8%EC%96%B4))
<br>
[알골 (프로그래밍 언어) - 위키백과](https://ko.wikipedia.org/wiki/%EC%95%8C%EA%B3%A8_(%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D_%EC%96%B8%EC%96%B4))
<br>
[ALGOL - wikipedia](https://en.wikipedia.org/wiki/ALGOL)
<br>
[BCPL - 위키백과](https://ko.wikipedia.org/wiki/BCPL)
<br>
[Why is “||” the symbol for or? [closed] - stakoverflow](https://stackoverflow.com/questions/15056896/why-is-the-symbol-for-or)
<br>
[\<프로그래밍 언어론\> 배커스-나우르 형식 - N.A의 자료실](https://naturaaurum.tistory.com/entry/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D-%EC%96%B8%EC%96%B4%EB%A1%A0-%EB%B0%B0%EC%BB%A4%EC%8A%A4-%EB%82%98%EC%9A%B0%EB%A5%B4-%ED%98%95%EC%8B%9D)
<br>
[배커스-나우어 형식(BNF) -  코딩스낵](https://gusdnd852.tistory.com/307)