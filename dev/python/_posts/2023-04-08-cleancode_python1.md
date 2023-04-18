---
layout: post
title:  "PEP-8 , Style Guide for Python Code"
date:   2023-04-08 00:16:26 +0900
related_posts: /dev/python/_posts/2023-04-08-cleancode_python2.md
categories: python basic cleancode

---

# PEP-8 이란?

> PEP 8 – Style Guide for Python Code
>
> Python 코드 스타일 가이드



## PEP-8 특성

### 검색 효율성

- 코드에서 원하는 부분을 빠르게 검색할 수 있도록 도와주는 성질

- 변수에 값을 할당하는 경우와 함수의 키워드 파라미터에 값을 할당하는 경우를 구분한다는 것이 가장 큰 특징

  - 키워드 인자(keyworkd argument) : 띄어쓰기를 사용하지 않음

  ```python
  root@ip-172-31-46-94:/home/ubuntu# grep -nr "location=" .
  ./Clean-Code-in-Python-Second-Edition/book/src/ch03/tests/test_kis.py:14:            id_=42, user="root", location="127.0.0.1", extra="excluded"
  ./Clean-Code-in-Python-Second-Edition/book/src/ch03/src/kis.py:11:    ...    id_=42, user="root", location="127.0.0.1", extra="excluded"
  ./Clean-Code-in-Python-Second-Edition/book/src/ch03/src/kis.py:36:    ...    id_=42, user="root", location="127.0.0.1", extra="excluded"
  ```

  - 변수 : 띄어쓰기를 사용

  ```python
  root@ip-172-31-46-94:/home/ubuntu# grep -nr "location =" .
  ./Clean-Code-in-Python-Second-Edition/book/src/ch10/service/libs/storage/src/storage/status.py:28:        self._current_location = current_location
  ```

### 일관성

- 일정한 포맷을 갖는 것 
- 코드의 레이아웃, 문서화, 이름 작명 규칙 등

### 더 나은 오류처리

- try / except 블록 내부의 코드를 최소화 하자

### 코드 품질

- 코드를 구조화 해서 볼 경우 코드를 이해하고 버그와 실수를 쉽게 찾을 수 있다.
- 코드 품질 도구를 사용해 잠재적인 버그를 찾을 수 있다.
- 정적 분석 도구를 사용해 한 줄당 버그의 수를 줄일 수 있다.



# 참고

---

- https://peps.python.org/pep-0008/

터닝포인트 , 유지보수가 쉬운 파이썬 코드를 만드는 비결 - 파이썬 클린코드 2nd Edition 을 기반으로 합니다.

✔ [예제코드 다운로드 링크](https://github.com/PacktPublishing/Clean-Code-in-Python-Second-Edition)

- 본인의 python 환경에서 git 소스를 clone해 줍니다.

```bash
root@ip-172-31-46-94:/home/ubuntu# git clone https://github.com/PacktPublishing/Clean-Code-in-Python-Second-Edition.git
```

## 클린코드란

> 다른 엔지니어가 코드를 읽고 유지 관리할 수 있는 코드
>
> 품질 좋은 소프트웨어를 개발하고, 견고하고 유지보수가 쉬운 시트메을 만들고, 기술 부채를 피하는 것
