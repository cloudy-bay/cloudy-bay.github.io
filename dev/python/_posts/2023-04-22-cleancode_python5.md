---
layout: post
title:  "Pythonic code"
date:   2023-05-07 00:16:26 +0900
related_posts: /dev/python/_posts/2023-04-08-cleancode_python1.md /dev/python/_posts/2023-04-08-cleancode_python2.md /dev/python/_posts/2023-04-08-cleancode_python3.md /dev/python/_posts/2023-04-08-cleancode_python4.md
categories: python basic cleancode
---

> 모든 언어는 해당 언어로 작업을 처리하는 고유한 `관용구`를 가지고 있다. 이 관용구를 따르는 코드를 `관용적`이라고 부르며, **파이썬스럽다고** 한다.
>
> - 인덱스와 슬라이스를 이해하고 인덱싱 가능한 객체를 올바른 방식으로 구현하기
> - 시퀀스와 이터러블 구현하기
> - 컨텍스트 관리자를 만드는 모범 사례 연구
> - 매직 메서드 사용
> - 퍼이썬에서 발생할 수 있는 부작용 피하기

# 인덱스와 슬라이스

> 자신이 가지고 있는 요소에 접근하는 방법

- 인덱스 (index)

  - 배열의 뒤에서부터 접근하고 싶을 때에는 음수를 사용하면 된다.

  ```python
  my_numbers = (4,5,3,9)
  my_numbers[-1]
  >>>> 9
  
  my_numbers[-3]
  >>>> 5
  ```

- 슬라이스 (slice)

  - 특정 구간의 요소를 구하고 싶을 때 사용
  - 첫 번째 파라미터의 인덱스에서 두 번째 파라미터의 인덱스 까지 가져오라는 것을 뜻함
  - 첫 인덱스는 포함, 끝 인덱스는 제외

  ```python
  my_numbers(1,1,2,3,5,8,13,21)
  my_numbers[2:5]
  >>>> (2,3,5)
  ```

  - 시작 혹은 끝 파라미터를 제외할 수 있다.

  ```PYTHON
  my_numbers[:3]
  >>>> (1,1,2)
  my_numbers[3:]
  >>>> (3,5,8,13,21)
  ```

  - 파라미터 없을 경우

  ```python
  my_numbers[::]
  >>>> (1,1,2,3,5,8,13,21)
  ```

  - 파라미터 N 개

  ```py
  my_numbers[1:7:2]
  >>>> (1,3,8)
  ```

  

# 참고

---

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
