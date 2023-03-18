---
layout: post
title:  "Github 블로그 만들기(1) - "
date:   2023-03-11 00:16:26 +0900
related_posts: /dev/etc/_posts/2023-03-11-Github blog make proc2.markdown
categories: etc github
---
- 나도 따라하면서 쓰는 완전 초보 가이드
- window 환경

---

## 0. 사설

이제 진짜 개발자로 살아야 하기 때문에.. 살아남기 위해서 공부하는 것들 적어놓을 겸 기술 블로그를 파기로 했다.

기술 블로그 채널로는 많이들 사용하시는게

- 티스토리 (Tistory)
- Velog
- github
- 네이버

등등이 있는데, 아래의 이유로 github 블로그를 선택했다. 

- git 을 알아야 하기 때문에 진입장벽이 있다는 단점 > 이지만 되려 나는 git 자체에 익숙해져야 하는 상황이라 오히려 장점
- 개발 소스 혹은 프로젝트를 공유하기에 적합
- markdown 지원
- 구글 애드센스 지원
- 다양한 커스터마이징 가능 

블로그 만들면서, 글 올리면서 git에도 친숙해지길 바라며, github 블로그 만드는 글로 첫 시작을 해보려 한다.

참고로 나는 IT회사에서 오래 근무했지만 '개발자' 는 아니어 진짜 기본 개념도 없는 왕초보이기 때문에, command 하나하나의 의미까지 검색하며 쓴다.

---

## 1. 초기 환경 설정

## 1.1 git 설치

- Git Window version 설치
  - https://goddaehee.tistory.com/216 참고하여 window version git 설치 진행

## 1.2 github 셋팅

- github 가입 : https://github.com/

- 새로운 repository 생성

  - ![image-20230309003717319](/assets/image-20230309003717319-1678468029181-3.png)

  - Repository 이름은 `{username}.github.io` 이런식으로 지어준다. (공식문서에 따르면, 다를 경우 문제가 생길 수 있다고 한다.)
  - 생성 시 `Add a README File` check

- 생성된 repository git clone

  - ![image-20230309004204000](/assets/image-20230309004204000-1678468029182-4.png)

- 설치한 git bash 실행

- repository 를 저장할 local 위치로 cd 

- repository 위치에서 아래의 명령어 실행

  - ```bash
    git clone {clone해온 url}
    ```

    - `git clone {https~~~}` : git 저장소 복제 및 다운로드

    - ex

      ```bash
      git clone https://github.com/cloudy-bay/cloudy-bay.github.io.git
      ```

- clone 한 위치로 이동 후 아래의 명령어 실행

  - ```bash
    cd {username}.github.io
    echo "Hello World" > index.html
    ```

    - ex

      ```bash
      yoojin@cloudy-bay MINGW64 ~
      $ cd cloudy-bay.github.io/
      
      yoojin@cloudy-bay MINGW64 ~/cloudy-bay.github.io (main)
      $ echo "Hello World" > index.html
      ```

      로컬PC 경로에 파일 잘 만들어졌는지 확인

      ![image-20230309004713300](/assets/image-20230309004713300.png)

- git push

  - ```bash
    git add --all # 변경분을 모두 스테이징 영역에 올린다 
    git commit -m "inital commit" #inital commit 이라는 메모로 commit
    git push -u origin main #origin 저장소의 main branch 에 push
    ```

    - [👀](https://www.daleseo.com/git-add/)`git add` 는 작업 디렉토리(working directory) 상의 변경 내용을 스테이징 영역(stagig area) 에 추가하기 위해서 사용하는 git 명령어 

    - [👀](https://www.daleseo.com/git-push/)`git push` 는 원격 저장소(remote repository)에 변경분을 업로드 하기 위해 사용하는 git 명령어 

    - ex

      ```bash
      yoojin@cloudy-bay MINGW64 ~/cloudy-bay.github.io (main)
      $ git add --all
      warning: in the working copy of 'index.html', LF will be replaced by CRLF the next time Git touches it
      g
      yoojin@cloudy-bay MINGW64 ~/cloudy-bay.github.io (main)
      $ git commit -m "inital commit"
      [main 8c1845a] inital commit
       1 file changed, 1 insertion(+)
       create mode 100644 index.html
      yoojin@cloudy-bay MINGW64 ~/cloudy-bay.github.io (main)
      $ git push -u origin main
      Enumerating objects: 4, done.
      Counting objects: 100% (4/4), done.
      Delta compression using up to 4 threads
      Compressing objects: 100% (2/2), done.
      Writing objects: 100% (3/3), 286 bytes | 95.00 KiB/s, done.
      Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
      To https://github.com/cloudy-bay/cloudy-bay.github.io.git
         35a83dc..8c1845a  main -> main
      branch 'main' set up to track 'origin/main'
      ```

      - git remote repository 에 변경분 반영된 것 확인 가능
        - 위에 clone 할 때 이미 index.html이 있는데 글 쓰기 전에 이미 push까지 해놔서 그렇다...ㅎㅎ

      ![image-20230309005904225](/assets/image-20230309005904225.png)

- 인터넷 주소창에 {username}.github.io 를 입력해서 창이 잘 뜨는지 확인

  - ex

  - ```text
    https://cloudy-bay.github.io/
    ```

  - <img src="/assets/image-20230309010149836.png" alt="image-20230309010149836" style="zoom:50%;" />

## 2. jekyll



## 99. 참고

- https://zeddios.tistory.com/1223
- https://velog.io/@kimsoyeong/github.io-jekyll

