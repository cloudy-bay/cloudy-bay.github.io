---
layout: post
title:  "Github 블로그 만들기(2) - jekyll 테마 적용하기"
date:   2023-03-11 00:16:26 +0900
related_posts: /dev/etc/_posts/2023-03-11-Github blog make proc1.markdown
categories: etc github
---
- window 환경

---

## 1. Ruby 설치

- jekyll 을 사용하기 위해서는 Ruby가 필요하다

  - [👀Ruby](https://namu.wiki/w/Ruby) 언어 : 간결함과 생산성을 강조한 동적인 오픈소스 프로그래밍 언어. 스크립트 언어의 일종
  - jekyll : 정적인 웹사이트 생성기로, Ruby 언어를 기반으로 제작되었으며 마크다운 방식으로 글쓰기가 가능.

- https://rubyinstaller.org/downloads/ 에서 WITH DEVKIT 중 (x86)으로 다운받아 설치

- 설치완료 후 `Start Command Prompt with Ruby` 를 실행한다

## 2. Jekyll 설치

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

        <img src="/assets/image-20230311011236532.png" alt="image-20230311011236532" style="zoom:50%;" />

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

### 2.1 jekyll 테마 선택하기

#### jekyll theme 선택 사이트

- **[jamstackthemes.dev](https://jamstackthemes.dev/ssg/jekyll/)**
- **[jekyllthemes.org](http://jekyllthemes.org/)**
- **[jekyllthemes.io](https://jekyllthemes.io/)**
- **[jekyll-themes.com](https://jekyll-themes.com/)**

들어가서 마음에 드는 테마를 선택하면 된다. 내가 선택한건 [hydejack](https://jekyll-themes.com/hydejack/) 테마(깔끔, 반응성.. 화려한 게 좋다 😉)

### 2.2 테마 적용하기

- 다운로드 받은 파일을 압축해제 한다.

- Local git repository에 복사한다

  - ex

    - 다운받은 테마 소스 복사

  - ![image-20230311020201567](/assets/image-20230311020201567.png)

    - Local git repository에 복사

    - 겹치는 파일 존재할 경우 덮어쓰기 적용

    - ![image-20230311020949633](/assets/image-20230311020949633.png)

    - jekyll command 입력

      - ```bash
        bundle install
        bundle exec jekyll serve
        ```

      - 설치가 정상적으로 완료되면, 아래의 주소에서 로컬상태로 확인 가능하다

        - http://127.0.0.1:4000/
        - 웹페이지에서 정상적으로 조회가 된다면, git에 배포한다.

- git 배포

  - 아래의 명령어로 원격 repository 로 변경된 내용을 push 한다.

    - ```bash
      git add .
      git commit -m "set Theme"
      git push
      ```

- 테마 적용 확인

  - 자신의 github blog 주소로 접속해서 정상 배포되었는지 확인한다
  
    ![image-20230318202122216](/assets/image-20230318202122216.png)
  
  - `https://{본인github username}.github.io/` 이용
  
  
