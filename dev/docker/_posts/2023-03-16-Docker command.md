---

layout: post
title:  "Docker command"
date:   2023-03-16 00:16:26 +0900
categories: docker basic

---

## Dockerfiile 작성

> 도커파일(Dockerfile)이란?
>
> : 패키시, 소스코드, 명령어, 환경변수 등 도커빌드를 위해 필요한 것들을 기록해 놓은 파일

- FROM : 생성할 이미지의 베이스 이미지를 지정해준다.
- WORKDIR : 명령어를 실행할 디렉토리. Bash shelld의 cd 명령어와 같은 기능
- COPY : Docker 외부의 파일을 복사해서 내부에 추가한다. `COPY ..` 은 현재 디렉토리에 있는 것을 전부 복사하여 workdir 로 추가하는 것을 의미한다.
- RUN : 이미지 빌드시 실행되는 명령어
- EXPOSE : 이미지에서 노출할 포트
- CMD : 컨테이너 생성 시 실행되는 명령어로, Dockerfile에서 한 번만 사용할 수 있다.
  - ✅ RUN / CMD / ENTRYPOINY 차이
    - RUN : 도커 파일로부터 도커 이미지를 빌드하는 순간 실행되는 명령어로 라이브러리 설치 부분에서 주로 활용된다.
    - CMD : 이미지로부터 컨테이너를 생성하여 최초로 실행할 때 실행되는 명령어
    - ENTRYPOINT : CMD와 동일하나 최초 실행시 꼭 실행되어야 하는 명령어가 있을 때 사용

## docker images 

> 기본적으로 `docker images` 명령어는 docker image 전체 리스트와 repository , tag  그리고 size 를 조회해준다.

- 명령어

  - ```bash
    docker images [OPTIONS] [REPOSITORY[:TAG]]
    ```

- [OPTIONS]

  - | Name, shorthand                                              | Default | Description                                                  |
    | ------------------------------------------------------------ | ------- | ------------------------------------------------------------ |
    | `--all` , `-a`                                               |         | Show all images (default hides intermediate images)          |
    | [`--digests`](https://docs.docker.com/engine/reference/commandline/images/#digests) |         | Show digests                                                 |
    | [`--filter`](https://docs.docker.com/engine/reference/commandline/images/#filter) , [`-f`](https://docs.docker.com/engine/reference/commandline/images/#filter) |         | Filter output based on conditions provided                   |
    | [`--format`](https://docs.docker.com/engine/reference/commandline/images/#format) |         | Format output using a custom template: ‘table’: Print output in table format with column headers (default) ‘table TEMPLATE’: Print output in table format using the given Go template ‘json’: Print in JSON format ‘TEMPLATE’: Print output using the given Go template. Refer to https://docs.docker.com/go/formatting/ for more information about formatting output with templates |
    | [`--no-trunc`](https://docs.docker.com/engine/reference/commandline/images/#no-trunc) |         | Don’t truncate output                                        |
    | `--quiet` , `-q`                                             |         | Only show image IDs                                          |

## docker compose

### docker compose pull

> 

- 명령어

  - ```bash
    docker compose pull [OPTIONS] [SERVICE...]
    ```

### docker-compose --compatibility

- Using `--compatibility` mode is what lets us do this. It will attempt to convert that API v3 way of setting resource limits back into v2 compatible properties.



# 참고

- https://liveloper-jay.tistory.com/92
- https://docs.docker.com/engine/reference/commandline/images/

- https://nickjanetakis.com/blog/docker-tip-78-using-compatibility-mode-to-set-memory-and-cpu-limits