# Github 블로그 만들기(2)

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
    
    - ![image-20230311020201567](assets/image-20230311020201567.png)
    
    - Local git repository에 복사
    
    - 겹치는 파일 존재할 경우 덮어쓰기 적용
    
    - ![image-20230311020949633](assets/image-20230311020949633.png)
    
    - jekyll command 입력
    
      - ```bash
        bundle install
        jekyll 
        ```
    
      - 