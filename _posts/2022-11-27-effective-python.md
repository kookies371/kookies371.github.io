---
layout: posts
title: "파이썬 코딩의 기술 정리"
classes: wide
---

# 10. 대입식을 이용해 반복을 피하라

대입식은 `a = b`꼴의 대입문(assignment statement)와는 다르게, 
평가가 필요한 구문(ex. if문) 안에 대입문을 쓸 수 있게 만들어준다.

예를 들어 아래와 같이, 레몬이 있을 경우에만 레모네이드를 만들어주는 코드를 보자.

<script src="https://gist.github.com/kookies371/7b3717c14b82e111720fa7d273093507.js"></script>

<script src="https://gist.github.com/kookies371/8572bfc3b25029d1d14352b3f78f6f97.js"></script>

이 코드는 if문 바로 위에 `count` 변수를 선언하기 때문에,
코드에서 레모네이드를 만들 수 있는 조건이 무엇인지 한 눈에 파악하기 어렵다.

만약 `count` 변수를 if문 안에서 선언하는 동시에 로직을 적용해줄 수 있다면 가독성이 더 좋아질 것이며,
이것을 가능하게 해주는 것이 **대입식(assignment expression)**이며, `:=`는 **왈러스 연산자**라고 부른다.

아래는 사과dml 갯수를 세는 `count` 변수를 선언하는 동시에 4개보다 많거나 같은지 체크하는 코드이다.
(대입식을 괄호로 둘러싸야 한다.)

<script src="https://gist.github.com/kookies371/fde6810d76db314e47d07bcfd6174917.js"></script>

아래 두 코드는 파이썬에는 없는 switch/case문과, do/while문을 왈러스 연산자로 대체하는 예시이다.
(do/while문에서 왈러스 연산자를 적용하면, 매 왈러스 연산자의 대상 변수를 매 루프마다 재계산한다.)

<script src="https://gist.github.com/kookies371/cba1e9fdb826650675f072371f3a3e73.js"></script>

<script src="https://gist.github.com/kookies371/1e4b768d657bd8c952199e12d45f1cd5.js"></script>

# 기타

- 왈러스 연산자를 이용해 선언된 변수는 선언된 블록 외에서도 여전히 유효한 변수이다.