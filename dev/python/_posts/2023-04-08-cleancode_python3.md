---
layout: post
title:  "자동 포매팅 - 파이썬 클린코드"
date:   2023-04-18 00:16:26 +0900
related_posts: /dev/python/_posts/2023-04-08-cleancode_python1.md /dev/python/_posts/2023-04-08-cleancode_python2.md /dev/python/_posts/2023-04-08-cleancode_python4.md
categories: python basic cleancode
---

- 코딩 컨벤션 등을 만들어두어도 강제하지 않는다면 추후 의미가 퇴색된다. 도구를 사용하여 표준 준수 여부를 확인하는 것 외에 자동으로 코드 형식을 지정하게 하는 것이 자동 포매팅이다.

## **flake8**

- PEP-8 준수여부 검사
- PEP-8 준수 코드로 자동 변환
- 옵션을 통한 프로젝트 레벨 수정 가능

## **black**

- [링크](https://github.com/psf/black)

- **all or nothing** 방식

- 라인 길이 제외와 같은 옵션은 허용하지 않으면서 고유하고 결정적인 방식으로 코드를 지정

- 부분적인 포매팅은 지원하지 않고 파일을 완벽하게 포매팅 한다.

  - example 

    - 따옴표는 항상 큰따옴표만 사용
    - 파라미터의 순서는 항상 동일할 것

    😲 **black 왜 좋은데?**

    - 엄격하지만 코드의 차이를 최소화 할 수 있는 유일한 방법
    - 실제 변경사항이 있는 경우에만 PR(Pull Request)이 생성
    - PEP-8 보다 제약은 많이 생기지만 문제의 핵심에 보다 집중 가능

    🙄 **PEP-8이랑 뭐가 다른데?**

    - PEP-8 은 허용하나, black 은 아래의 코드를 허용 안 함

      ```python
      def my_function(name):
          """
          >>> my_function('black')
          'received Black'
          """
          return 'received {0}'.format(name.title())
      ```

      - black 검사 실행

        ```python
        black -l 79.py
        ```

      - black 실행 결과

        ```python
        def my_function(name):
            """
            >>> my_function('black')
            'received Black'
            """
            return "received {0}".format(name.title())
        ```

  - black 검사만 하길 원할 경우 `--check` 옵션을 주고 실행




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

