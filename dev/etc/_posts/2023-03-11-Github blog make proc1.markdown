---
layout: post
title:  "Github 블로그 만들기(1)"
date:   2023-03-11 00:16:26 +0900
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

  - <img src="assets/image-20230309010149836.png" alt="image-20230309010149836" style="zoom:50%;" />

## 2. jekyll

## 2.1 Ruby 설치

- jekyll 을 사용하기 위해서는 Ruby가 필요하다

  - [👀Ruby](https://namu.wiki/w/Ruby) 언어 : 간결함과 생산성을 강조한 동적인 오픈소스 프로그래밍 언어. 스크립트 언어의 일종
  - jekyll : 정적인 웹사이트 생성기로, Ruby 언어를 기반으로 제작되었으며 마크다운 방식으로 글쓰기가 가능.

- https://rubyinstaller.org/downloads/ 에서 WITH DEVKIT 중 (x86)으로 다운받아 설치

- 설치완료 후 `Start Command Prompt with Ruby` 를 실행한다

- cmd 창에 아래의 명령어를 쳐서 `jekyll` 을 설치한다.

  - ```bash
    gem install jekyll bundler
    ```

  - ex) 정상설치 완료된 경우

    ```bash
    A new release of RubyGems is available: 3.4.6 → 3.4.8!
    Run `gem update --system 3.4.8` to update your installation.
    ```

    ```bash
    C:\Users\yoojin>ruby -v
    ruby 3.2.1 (2023-02-08 revision 31819e82c8) [i386-mingw32]
    
    C:\Users\yoojin>jekyll -v
    jekyll 4.3.2
    ```

- 아래의 명령어를 이용하면, 블로그 파일이 생성되게 된다.

  - ```bash
    jekyll new ./
    ```

    index.html 파일을 만들기도 했고, 난 그 외의 다른 파일들이 있어서 아래와 같은 conflict error 가 발생했다.

    이럴때는 `-f` 옵션을 줘서 강제로 생성하게 한다.

  - ```bash
    C:\Users\yoojin\cloudy-bay.github.io>jekyll new ./
              Conflict: C:/Users/yoojin/cloudy-bay.github.io exists and is not empty.
                        Ensure C:/Users/yoojin/cloudy-bay.github.io is empty or else try again with `--force` to proceed and overwrite any files.
    
    C:\Users\yoojin\cloudy-bay.github.io>jekyll new ./ -f
    ```

- jekyll을 로컬서버에 띄우기

  - ```bash
    bundle exec jekyll serve
    ```

  - ex

    - ```bash
      C:\Users\yoojin\cloudy-bay.github.io>bundle exec jekyll serve
      Configuration file: C:/Users/yoojin/cloudy-bay.github.io/_config.yml
                  Source: C:/Users/yoojin/cloudy-bay.github.io
             Destination: C:/Users/yoojin/cloudy-bay.github.io/_site
       Incremental build: disabled. Enable with --incremental
            Generating...
             Jekyll Feed: Generating feed for posts
      Deprecation Warning: Using / for division outside of calc() is deprecated and will be removed in Dart Sass 2.0.0.
      
      Recommendation: math.div($spacing-unit, 2) or calc($spacing-unit / 2)
      
      More info and automated migrator: https://sass-lang.com/d/slash-div
      
         ╷
      40 │   margin-bottom: $spacing-unit / 2;
         │                  ^^^^^^^^^^^^^^^^^
         ╵
          ..\..\..\..\minima-2.5.1\_sass\minima\_base.scss 40:18     @import
          minima.scss 48:3                                           @import
          C:\Users\yoojin\cloudy-bay.github.io\assets\main.scss 1:9  root stylesheet
      Deprecation Warning: Using / for division outside of calc() is deprecated and will be removed in Dart Sass 2.0.0.
      
      Recommendation: math.div($spacing-unit, 2) or calc($spacing-unit / 2)
      
      More info and automated migrator: https://sass-lang.com/d/slash-div
      
          ╷
      134 │   padding-left: $spacing-unit / 2;
          │                 ^^^^^^^^^^^^^^^^^
          ╵
          ..\..\..\..\minima-2.5.1\_sass\minima\_base.scss 134:17    @import
          minima.scss 48:3                                           @import
          C:\Users\yoojin\cloudy-bay.github.io\assets\main.scss 1:9  root stylesheet
      Deprecation Warning: Using / for division outside of calc() is deprecated and will be removed in Dart Sass 2.0.0.
      
      Recommendation: math.div($spacing-unit, 2) or calc($spacing-unit / 2)
      
      More info and automated migrator: https://sass-lang.com/d/slash-div
      
          ╷
      189 │     padding-right: $spacing-unit / 2;
          │                    ^^^^^^^^^^^^^^^^^
          ╵
          ..\..\..\..\minima-2.5.1\_sass\minima\_base.scss 189:20    @content
          minima.scss 38:5                                           media-query()
          ..\..\..\..\minima-2.5.1\_sass\minima\_base.scss 186:3     @import
          minima.scss 48:3                                           @import
          C:\Users\yoojin\cloudy-bay.github.io\assets\main.scss 1:9  root stylesheet
      Deprecation Warning: Using / for division outside of calc() is deprecated and will be removed in Dart Sass 2.0.0.
      
      Recommendation: math.div($spacing-unit, 2) or calc($spacing-unit / 2)
      
      More info and automated migrator: https://sass-lang.com/d/slash-div
      
          ╷
      190 │     padding-left: $spacing-unit / 2;
          │                   ^^^^^^^^^^^^^^^^^
          ╵
          ..\..\..\..\minima-2.5.1\_sass\minima\_base.scss 190:19    @content
          minima.scss 38:5                                           media-query()
          ..\..\..\..\minima-2.5.1\_sass\minima\_base.scss 186:3     @import
          minima.scss 48:3                                           @import
          C:\Users\yoojin\cloudy-bay.github.io\assets\main.scss 1:9  root stylesheet
      Deprecation Warning: Using / for division outside of calc() is deprecated and will be removed in Dart Sass 2.0.0.
      
      Recommendation: math.div($spacing-unit, 3) or calc($spacing-unit / 3)
      
      More info and automated migrator: https://sass-lang.com/d/slash-div
      
          ╷
      244 │     padding: ($spacing-unit / 3) ($spacing-unit / 2);
          │               ^^^^^^^^^^^^^^^^^
          ╵
          ..\..\..\..\minima-2.5.1\_sass\minima\_base.scss 244:15    @import
          minima.scss 48:3                                           @import
          C:\Users\yoojin\cloudy-bay.github.io\assets\main.scss 1:9  root stylesheet
      Warning: 6 repetitive deprecation warnings omitted.
      Run in verbose mode to see all warnings.
                          done in 2.641 seconds.
       Auto-regeneration: enabled for 'C:/Users/yoojin/cloudy-bay.github.io'
          Server address: http://127.0.0.1:4000/
        Server running... press ctrl-c to stop.
      ```

      - ✔ server 주소가 `Server address: http://127.0.0.1:4000/` 로 따짐

      - 주소창에 server 주소 입력 후 접속 확인

        <img src="assets/image-20230311011236532.png" alt="image-20230311011236532" style="zoom:50%;" />

- git push

  - ```bash
    git add .
    git commit -m "jekyll setting" #원하는 commit comment 아무거나
    git push
    ```

  - ex

    - ```bash
      C:\Users\yoojin\cloudy-bay.github.io>git add .
      
      C:\Users\yoojin\cloudy-bay.github.io>git commit -m "jekyll setting"
      [main dace40c] jekyll setting
       8 files changed, 260 insertions(+)
       create mode 100644 .gitignore
       create mode 100644 404.html
       create mode 100644 Gemfile
       create mode 100644 Gemfile.lock
       create mode 100644 _config.yml
       create mode 100644 _posts/2023-03-11-welcome-to-jekyll.markdown
       create mode 100644 about.markdown
       create mode 100644 index.markdown
      
      C:\Users\yoojin\cloudy-bay.github.io>git push
      Enumerating objects: 12, done.
      Counting objects: 100% (12/12), done.
      Delta compression using up to 4 threads
      Compressing objects: 100% (11/11), done.
      Writing objects: 100% (11/11), 4.70 KiB | 962.00 KiB/s, done.
      Total 11 (delta 0), reused 0 (delta 0), pack-reused 0
      To https://github.com/cloudy-bay/cloudy-bay.github.io.git
         0bccc36..dace40c  main -> main
      
      C:\Users\yoojin\cloudy-bay.github.io>git push\
      git: 'push\' is not a git command. See 'git --help'.
      
      The most similar command is
              push
      
      ```

    - `https://{본인github username}.github.io/` 이용해서 접속해 잘 적용됐는지 확인하기

      - ![image-20230311011843429](/assets/image-20230311011843429.png)



## 99. 참고

- https://zeddios.tistory.com/1223
- https://velog.io/@kimsoyeong/github.io-jekyll

