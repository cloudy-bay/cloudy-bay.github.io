---
layout: post
title:  "문서화 (Documentation) - 파이썬 클린코드"
date:   2023-04-08 00:16:26 +0900
related_posts: /dev/python/_posts/2023-04-08-cleancode_python1.md
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

# 문서화 (Documentation)

> 파이썬은 변수의 타입이 동적이어 변수나 객체의 값이 무엇인지 잃어버리기 쉽기 때문에 문서화는 중요한 부분이다.

## 코드 주석(Code comments)

- 가능한 **적은 주석**을 갖는 것을 목표로 해야한다.

- 좋은 코드는 코드 자체가 문서화 되어있기 때문에 명확하게 이름을 지정했다면 주석이 필요하지 않다...!

  ✔ 주석을 작성하기 전에, 새로운 함수를 추가하거나 보다 나은 변수명을 사용하는 것과 같은 방법으로 개선하자

- 주석처리된 코드는 최악이다.

## Docstring

> 소스 코드에 포함된 문서(documentation) 
>
> 컴포넌트의 동작방식과 입출력 정보 등을 확인할 수 있어야 한다.

ex)

```python
dict.update??
```

- 함수의 이름 뒤에 `??` 를 붙여주면 docstring 이 출력된다 (IPython 대화형 인터프리터 기능)

```python
Help on method_descriptor:

update(...)
    D.update([E, ]**F) -> None.  Update D from dict/iterable E and F.
    If E is present and has a .keys() method, then does:  for k in E: D[k] = E[k]
    If E is present and lacks a .keys() method, then does:  for k, v in E: D[k] = v
    In either case, this is followed by: for k in F:  D[k] = F[k]
(END)
```



## 어노테이션 (annotation)

> 함수 인자로 어떤 값이 와야 하는지 **힌트**를 주자는 것

- 어노테이션을 사용하면 `__annotations__` 이라는 특수한 속성이 생긴다. 이 속성은 어노테이션의 이름과 값을 매핑한 사전 타입의 값이다.



