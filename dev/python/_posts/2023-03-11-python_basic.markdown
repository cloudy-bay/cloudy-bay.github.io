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

