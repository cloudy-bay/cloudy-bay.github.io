---
layout: post
title:  "Python Basic"
date:   2023-03-11 00:16:26 +0900
categories: python basic
---

# python

## __init__.py
> __init__.py 는 해당 디렉터리가 패키지의 일부임을 알려주는 역할을 한다.
> python version 3.3 이후부터는 작성하지 않아도 패키지임을 인식하지만, 그 이전 버전에서는 꼭 있어야 인식한다. 따라서, 호환성을 위해 작성해주도록 하자.

## os.path

- os.path.basename(filename)
  - 전달받은 `filename`의 이름만을 출력한다.

## if

- If not

  - 조건문이 아닌 경우 실행문을 실행시킨다

  - ```python
    if not a_condition:
        block_of_code_to_execute_if_condition_is_false
    ```

  - python 에서의`False`값

    - `0`,`0L`,`0.0`과 같은 숫자 0 값
    - 다음과 같은 빈 시퀀스 :
      - 빈 목록 []
      - 빈 사전 {}
      - 빈 문자열 ''
      - 빈 튜플
      - 빈 세트

  - ex

    - ```python
      if not job_description:
      	job description = os.path.basename(sub_task['text'])
      ```

      job_description 이 비어있으면, 아래를 수행해라

## File

### File 생성하기

- open

  - ```python
    f = open("새파일.txt",'w')
    f.close()
    ```

  - open 함수는 다음과 같이 "파일 이름"과 "파일 열기 모드"를 입력값으로 받고 결괏값으로 파일 객체를 리턴한다.

    > 파일 객체 = open(파일 이름, 파일 열기 모드)

    파일 열기 모드에는 다음과 같은 것들이 있다.

    | 파일열기모드 | 설명                                                       |
    | :----------- | :--------------------------------------------------------- |
    | r            | 읽기모드 - 파일을 읽기만 할 때 사용                        |
    | w            | 쓰기모드 - 파일에 내용을 쓸 때 사용                        |
    | a            | 추가모드 - 파일의 마지막에 새로운 내용을 추가 시킬 때 사용 |

### File read

- readline 함수

- readlines 함수

  > 파일의 모든 줄을 읽어서 각각의 줄을 요소로 갖는 리스트를 리턴한다.

## sqlparse

## List

### .join()

> List를 문자열로 일정하게 합쳐주는 함수
>
> ```python
> ''.join(리스트)
> '구분자'.join(리스트)
> ```

- `''.join(리스트)` 
  - 매개변수로 들어온 리스트를 하나의 문자열로 합쳐준다.
  - ex)  ''.join(['a','b','c']) > 'abc'
- `'구분자'.join(리스트)
  - 매개변수로 들어온 리스트의 값과 값 사이에 '구분자' 에 들어온 구분자를 넣어서 하나의 문자열로 합쳐준다.
  - ex) '_'.join(['a','b','c']) > 'a_b_c'

## zfill()

- 파이썬 문자열 앞에서부터 0으로 채우기

  ```python
  str.zfill({num})
  ex)
  "3".zfill(3)
  >>> "003"
  ```

  

## 참고

- https://wikidocs.net/26
- https://blockdmask.tistory.com/468
- https://buildmedia.readthedocs.org/media/pdf/sqlparse/latest/sqlparse.pdf





결혼 3천

축의 800

빌려드린 돈 1000

주식 1000
