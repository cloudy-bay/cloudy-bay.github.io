layout: post
title:  "Python WHL 파일이란"
date:   2023-03-16 00:16:26 +0900
categories: python basic 

---

# WHL File?

> `.whl` 파일은 Python의 휠 형식으로 저장된 배포 패키지 파일.
>
> - 설치에 필요한 모든 파일과 메타데이터가 포함되어 있는 ZIP(.zip) 아카이브
> -  `.zip` 으로 확장자를 변경하면 `unzip`을 통하여 압축을 해제할 수 있다

## WHL 파일 이름 규칙

- WHL 파일은 아래의 명명규칙에 따라 이름이 지정된다

  ```bash
  {dist}-{version}(-{build})?-{python}-{abi}-{platform}.whl
  ```

  - EX

    ```bash
    cryptography-2.9.2-cp35-abi3-macrosx_10_9_x86_64.whl
    ```

  - {dist} : package name

  - {version} : package version 

# 참고

---

- https://docs.fileformat.com/ko/compression/whl/