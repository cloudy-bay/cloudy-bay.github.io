---
layout: post
title:  "Github 블로그 만들기(2)"
date:   2023-03-11 00:16:26 +0900
categories: etc github
---
- window 환경
- Github 블로그 만들기(1) 글 후행

---

## 1. jekyll 테마 선택하기

### 1.1 jekyll theme 선택 사이트

- **[jamstackthemes.dev](https://jamstackthemes.dev/ssg/jekyll/)**
- **[jekyllthemes.org](http://jekyllthemes.org/)**
- **[jekyllthemes.io](https://jekyllthemes.io/)**
- **[jekyll-themes.com](https://jekyll-themes.com/)**

들어가서 마음에 드는 테마를 선택하면 된다. 내가 선택한건 [hydejack](https://jekyll-themes.com/hydejack/) 테마(깔끔, 반응성.. 화려한 게 좋다 😉)

### 1.2 테마 적용하기

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

      - ❗ 설치하다보면 아래와 같은 Liquid Exception: Liquid syntax error 가 날 수 있다

        - ex

          ```bash
          C:\Users\yoojin\cloudy-bay.github.io>bundle exec jekyll serve
          Configuration file: C:/Users/yoojin/cloudy-bay.github.io/_config.yml
                      Source: C:/Users/yoojin/cloudy-bay.github.io
                 Destination: C:/Users/yoojin/cloudy-bay.github.io/_site
           Incremental build: disabled. Enable with --incremental
                Generating...
                 Jekyll Feed: Generating feed for posts
            Liquid Exception: Liquid syntax error (C:/Users/yoojin/cloudy-bay.github.io/_includes/styles/style.scss line 17): Unknown tag 'include_cached' included in assets/css/hydejack-9.1.6.css
                              ------------------------------------------------
                Jekyll 4.3.2   Please append `--trace` to the `serve` command
                               for any additional information or backtrace.
                              ------------------------------------------------
          ```

        - 아래의 문서에 따르면, `Gemfile` 에 아래의 gem  설치 plugin을 넣어주어야 한다.

          - ![image-20230311135828764](/assets/image-20230311135828764.png)
          - plugin 명령어 입력
            - 
        
        
        
        
