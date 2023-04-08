---
layout: post
title:  "AWS EC2에 Python 설치하기"
date:   2023-04-01 00:16:26 +0900
related_posts: /dev/docker/_posts/2023-04-01-Docker_install_on_AWS.md /dev/docker/_posts/2023-03-11-Docker_install.markdown
categories: docker basic

---

>  EC2 에서 Docker 를 설치하고, Python을 설치한다.

- AWS EC2 및 Docker 설치 방법은 아래의 Post 를 참고한다.
  
  ✔[AWS에 Docker 설치하기](https://cloudy-bay.github.io/dev/docker/basic/2023-03-31-Docker-install-on-AWS/)

- Docker 를 생성한다.

  ```bash
  sudo su
  docker run -i -t ubuntu:14.04
  ```

- container 내부에서 apt update 실행

  ```bash'
  apt-get update -y
  ```

- python3 설치

  ```bash
  apt-get install python3 pip3 -y
  ```

- version 확인

  ```bash
  python3 --version
  ```

- 실행 command 예시

  ```bash
  CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
  root@ip-172-31-46-94:/home/ubuntu# docker run -i -t ubuntu:14.04
  root@8fa9356600f6:/#
  root@8fa9356600f6:/#
  root@8fa9356600f6:/# sudo apt-get update -y
  Get:1 http://security.ubuntu.com trusty-security InRelease [56.4 kB]
  Ign http://archive.ubuntu.com trusty InRelease
  Get:2 http://archive.ubuntu.com trusty-updates InRelease [56.4 kB]
  Get:3 http://security.ubuntu.com trusty-security/main amd64 Packages [1557 kB]
  Get:4 http://archive.ubuntu.com trusty-backports InRelease [65.9 kB]
  Get:5 https://esm.ubuntu.com trusty-infra-security InRelease
  Hit http://archive.ubuntu.com trusty Release.gpg
  Get:6 https://esm.ubuntu.com trusty-infra-updates InRelease
  Get:7 http://archive.ubuntu.com trusty-updates/main amd64 Packages [2183 kB]
  Get:8 https://esm.ubuntu.com trusty-infra-security/main amd64 Packages
  Get:9 http://security.ubuntu.com trusty-security/restricted amd64 Packages [24.6 kB]
  Get:10 http://security.ubuntu.com trusty-security/universe amd64 Packages [529 kB]
  Get:11 http://security.ubuntu.com trusty-security/multiverse amd64 Packages [6133 B]
  Get:12 http://archive.ubuntu.com trusty-updates/restricted amd64 Packages [28.7 kB]
  Get:13 http://archive.ubuntu.com trusty-updates/universe amd64 Packages [931 kB]
  Get:14 http://archive.ubuntu.com trusty-updates/multiverse amd64 Packages [21.7 kB]
  Get:15 https://esm.ubuntu.com trusty-infra-updates/main amd64 Packages
  Get:16 http://archive.ubuntu.com trusty-backports/main amd64 Packages [14.7 kB]
  Get:17 http://archive.ubuntu.com trusty-backports/restricted amd64 Packages [40 B]
  Get:18 http://archive.ubuntu.com trusty-backports/universe amd64 Packages [52.5 kB]
  Get:19 http://archive.ubuntu.com trusty-backports/multiverse amd64 Packages [1392 B]
  Hit http://archive.ubuntu.com trusty Release
  Get:20 http://archive.ubuntu.com trusty/main amd64 Packages [1743 kB]
  Get:21 http://archive.ubuntu.com trusty/restricted amd64 Packages [16.0 kB]
  Get:22 http://archive.ubuntu.com trusty/universe amd64 Packages [7589 kB]
  Get:23 http://archive.ubuntu.com trusty/multiverse amd64 Packages [169 kB]
  Fetched 15.8 MB in 7s (1982 kB/s)
  Reading package lists... Done
  root@8fa9356600f6:/# apt-get install python3 pip3 -y
  Reading package lists... Done
  Building dependency tree
  Reading state information... Done
  E: Unable to locate package pip3
  root@8fa9356600f6:/# python3 --version
  Python 3.4.3
  ```

  

