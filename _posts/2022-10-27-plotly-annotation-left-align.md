---
layout: posts
toc: true
title: "[Plotly] add_vline annotation 왼쪽 정렬하기"
# categories: junk
tags: [plotly]
---

<script src="https://gist.github.com/kookies371/11f29db9371fb819edada551d9290c6d.js"></script>

![사진1](/images/1-1.png)

위와 같은 코드를 실행하면, 그래프의 가운데에 점선이 생기고 점선에 대한 설명을 annotation에 적어줄 수 있다. 하지만 사진과 같이 설명에 여러 줄이 필요한 경우, 설명을 **왼쪽 정렬**할 수 없는 것이 불편했다.

구글에 `add_vline annotation left align`과 같이 검색해봤지만,,, 딱히 만족스러운 검색 결과는 없었다. 요런 [검색 결과](https://stackoverflow.com/questions/69720768/position-add-vline-annotation-text-vertically-and-center-mid-point-on-vertical)는 있었지만 내가 원하는 답은 아니었다.

그래서 직접 코드를 뜯어보니 생각보다 답은 간단했다.

먼저 `add_vline`의 코드를 보자.

<script src="https://gist.github.com/kookies371/37aa313e57880e44e360f21dcc7a49dd.js"></script>

`add_vline`은 몇 개의 인자를 받아 전처리조차 없이 바로 부모클래스의 `add_vline`함수로 넘겨버리는데, 이 때 주석을 보면 `annotation_*`꼴의 인자들은 `go.layout.Annotation`에서 찾을 수 있다고 한다.

그래서 `go.layout.Annotation`을 찾아봤다.

<script src="https://gist.github.com/kookies371/1892f9d92365222a383a5b2f829cea8e.js"></script>

아! 찾았다. 결국 `add_vline`에 `annotation_align` 인자를 줄 수 있고, 인자들은 `'left', 'center', 'right'`중 하나를 줄 수 있다는 것.

결론은 `add_vline`에 `annotation_align='left'`를 추가해주면 원하는 출력을 얻을 수 있다!

<script src="https://gist.github.com/kookies371/1bbf80e78aee9d69da46374e4ded2a69.js"></script>

![사진2](/images/1-2.png)