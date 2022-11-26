---
layout: posts
title: "[DOCS] Pandas read_csv 함수 분석하기"
classes: wide
---

라이브러리의 자주 쓰는 함수를 직접 뜯어보는 DOCS 시리즈 첫 게시글이다.

첫 게시글은 파이썬 pandas 라이브러리의 read_csv이다.

공식 documentation인 [링크](https://pandas.pydata.org/docs/reference/api/pandas.read_csv.html)를 많이 참고했다.

# read_csv

말 그대로 csv 파일을 읽어 `pd.DataFrame` object를 반환하는 함수이다.
`json.load`를 사용할 때와 다르게 `with open() as f`구문이 필요없다.

