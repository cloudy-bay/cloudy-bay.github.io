---
layout: post
title:  "자동 포매팅 - 파이썬 클린코드"
date:   2023-04-18 00:16:26 +0900
related_posts: /dev/python/_posts/
categories: python basic cleancode
---

> 터닝포인트 , 유지보수가 쉬운 파이썬 코드를 만드는 비결 - 파이썬 클린코드 2nd Edition 을 기반으로 합니다.
>
> ✔ [예제코드 다운로드 링크](https://github.com/PacktPublishing/Clean-Code-in-Python-Second-Edition)
>
> - 본인의 python 환경에서 git 소스를 clone해 줍니다.
>
> ```bash
> root@ip-172-31-46-94:/home/ubuntu# git clone https://github.com/PacktPublishing/Clean-Code-in-Python-Second-Edition.git
> ```
>
> ## 클린코드란
>
> > 다른 엔지니어가 코드를 읽고 유지 관리할 수 있는 코드
> >
> > 품질 좋은 소프트웨어를 개발하고, 견고하고 유지보수가 쉬운 시트메을 만들고, 기술 부채를 피하는 것

# 도구설정

> 반복적인 확인 작업을 줄이기 위해 코드 검사를 자동으로 실행하는 기본 도구

## 데이터 타입 일관성 검사

- 타입 검사 도구가 유용하게 쓰이기 위해선 어노테이션을 정확하게 작성해야 한다(오탐방지)

### mypy

- [mypy Link](https://github.com/python/mypy)
- 정적 타입 검증 도구
- 프로젝트에서 사용되는 모든 파일에 대해서 데이터 타입의 유효성을 검사한다.

- mypy 설치

  ```bash
  pip install mypy
  ```

- mypy 실행

  ```bash
  mypy {파일명}
  ```

  - mypy를 설치하고 실행하면 의심이 되는 오류들을 보고한다. 

- 오탐일 경우 ignore 옵션으로 무시하게 할 수 있다.

  ```bash
  type_to_ignore = "something" #type: ignore
  ```

### ✔ pytype 과 mytype 차이점

- pytype에서는 최종 결과가 선언된 유형을 준수하면 문제로 간주하지 않으나, mypy는 감지한다

  example

  ```python
  from typing import List
  def get_list()-> List[str]:
      lst =["PyCon"]
      lst.append(2022) # 숫자형을 입력하고 있기 때문에 mypy에서는 오류이지만, pytype 에서는 오류가 아니다
      return [str(x) for x in lst]
  ```

  

### pylint

- 데이터 타입을 검사하는 것 외에도 다른 도구를 사용하여 보다 일반적인 유형의 품질 검사를 하는 것이 가능하나, PEP8 도 일반적인 코드 스타일이나 구조에 관한 것을 검사할 뿐 모든 메서드, 클래스, 모듈에 docstring 을 강제하지는 않는 등 제한적인 검증만 진행한다.
- 반면, 추가적인 검증이 가능한 도구 중 하나가 바로 `pylint` 다
- 가장 엄격한 수준의 검증을 하는 도구이며 기타 다른 여러 기능들도 포함하고 있다.

#### 설치

```bash
pip install pylint
```



