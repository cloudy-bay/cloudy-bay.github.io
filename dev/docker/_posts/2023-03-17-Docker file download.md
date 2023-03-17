---
layout: post
title:  "Docker File Download"
date:   2023-03-17 00:16:26 +0900
categories: docker basic
---

# 도커 파일 복사

## 컨테이너 👉 로컬

```bash
$docker cp {container_name}:{directory_path/file_nm} {local_directory} 
```

- `docker cp` 명령어 뒤에 컨테이너 이름과 컨테이너 내부 경로를 `":"` 로 구분해 적어주고 그 뒤에 복사해올 로컬 경로를 적어준다.
  - docker container 이름은 terminal에 `docker ps` 명령어로 조회되는 `NAMES` 항목을 확인하면 된다.

## 로컬 👉 컨테이너

```bash
$docker cp {local_directory/file_nm} {container_name}:{directory_path} 
```

- 컨테이너에서 옮겨올 때와 반대로 실행해주면 된다.



# 참고

- https://itholic.github.io/docker-copy/
- 
