---
layout: post
title:  "Docker 설치하기"
date:   2023-03-11 00:16:26 +0900
related_posts: /dev/docker/_posts/2023-03-18-Docker_start.md
categories: docker basic
---

- window 환경

## 도커(Docker)란?

> **도커(Docker)**는 리눅스 컨테이너에 여러 기능을 추가함으로써 Application을 컨테이너로서 좀 더 쉽게 사용할 수 있게 만들어진 오픈소스 프로젝트.
>
> 일반적으로 도커라고 하면 도커 엔진(Docker Engine) 혹은 도커에 관련된 모든 프로젝트를 의미한다.

### 1. 도커 컨테이너

- 도커 컨테이너는 가상화된 공간을 생성하기 위해 리눅스의 자체 기능인 chroot, namespace, cgroup을 사용함으로써 프로세스 단위의 격리 환경을 만들기 때문에 성능 소실이 거의 없다.
- 컨테이너에 필요한 커널은 호스트의 커널을 공유해 사용하고, 컨테이너 안에는 애플리케이션을 구동하는 데 필요한 라이브러리 및 실행파일만 존재해, 컨테이너를 이미지로 만들었을 때 이미지의 용량이 가상머신에 비해 대폭 줄어든다는 장점이 있다.
- 따라서, 도커 컨테이너를 이용할 경우 배포시간 및 성능 손실 단축이 거의 없다는 장점.

### 2. 도커의 장점

- 애플리케이션의 개발과 배포가 편해진다.
  - 도커 컨테이너는 호스트(서버를 부팅할 때 실행되는 운영체제) 위에서 실행되는 격리된 공간으로 독립된 개발 환경을 보장받는다.
  - 커널이 포함되어 있지 않아 이미지 크기가 작다.
  - 이미지 내용을 레이어 단위로 구성하고 중복 레이어를 재사용 할 수 있어 배포 속도가 빠르다.
- 여러 애플리케이션의 독립성과 확장성이 높아진다.
  - 컨테이너는 수 초 내로 생성 / 시작 / 독립된 환경 동시 제공이 가능하기 때문에 마이크로 서비스 아키텍처에 가장 많이 사용된다.



## 도커 엔진 설치

> 도커는 다양한 운영체제에서 사용할 수 있으나, 리눅스 컨테이너를 제어하는 api를 go언어로 구현한 libcontainer를 사용하기 때문에 대부분의 리눅스 운영체제에서 사용할 수 있다.

### Docker Descktop for Windows 설치

- Hyper-V 가상화를 지원하는 64비트 환경의 윈도우 10 Pro, Enterprise, Home 운영체제 필요

- 다운로드 :  https://docs.docker.com/desktop/install/windows-install/

  ![image-20230315224256094](/assets/image-20230315224256094.png)

- 다운로드 받은 파일을 설치후 컴퓨터를 재부팅 하면 도커 설치 완료

- 도커 설치 확인

  - ```BASH
    docker -v
    ```

  - ```bash
    C:\Users\yoojin>docker -v
    Docker version 20.10.23, build 7155243
    ```

### 리눅스 환경에 도커 마련하기

- 도커는 리눅스에 최적화 되어있으므로, 리눅스 개봘환경을 구축하기 위해 가상환경을 마련한다.
- 버추얼박스 , VMWare 같은 가상화 환경과 AWS EC2 를 사용하는 방법이 있다.

### 1. 버추얼박스 설치

- 아래의 경로에서 버추얼박스(Virtual Box) 를 설치한다

- 다운로드 경로

  - https://www.virtualbox.org/wiki/Downloads
  - ![image-20230318194154965](/assets/image-20230318194154965.png)

  - 자신의 운영체제에 맞는 패키지를 설치한다.

### 2. 이미지 파일 설치(.iso)

- 도커와 가장 잘 호환되며 관련 자료가 많은 건 우분투 이기 때문에 가상머신에 사용될 이미지 파일(.iso) 를 Ubuntu 로 선택하여 설치한다.
- https://releases.ubuntu.com/20.04/
- 데스크톱과 서버 버전이 있으나, 난 서버에 익숙해지기 위해 서버 버전을 선택하여 설치를 진행한다.
- ![image-20230318194820524](/assets/image-20230318194820524.png)

### 3. 버추얼 박스에 우분투 이미지 설치

- 설치한 Virtual Box 를 실행한다

- 새로만들기(N) 을 선택한다

- ![image-20230318212231915](/assets/image-20230318212231915.png)

- 이름을 적당히 넣어주고, 위에서 다운받은 ubuntu image(.iso) 파일을 선택해준다

  ![image-20230318212526118](/assets/image-20230318212526118.png)

- 이후 과정 다 적당히 setting 

- ![image-20230318213344925](/assets/image-20230318213344925.png)

- ![image-20230318213428354](/assets/image-20230318213428354.png)

- 기존 사용하던 Disk 를 넣을 수 있지만, 신규 생성으로 진행

- ![image-20230318213501538](/assets/image-20230318213501538.png)

- ![image-20230318213521380](/assets/image-20230318213521380.png)

- ubuntu server 환경 설정 완료

  ![image-20230318213633723](/assets/image-20230318213633723.png)

### 4. 리눅스 도커 엔진 설치

- 설치한 VM-ubuntu 서버에 접속한다

- 최신 버전 커널을 사용하고 있는지 확인한다

  - ```bash
    uname -r
    ```

    - 호스트 운영체제가 최소한 3.10 version 이상을 사용해야 docker 컨테이너를 정상적으로 사용할 수 있다.

    <img src="./../../../assets/image-20230318222606565.png" alt="image-20230318222606565" style="zoom:50%;" />

- 도커 설치 진행

  - ubuntu 20.04

    ```bash
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key-add -
    # add-apt-repository \
    "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
    
    # apt-get update
    
    #apt-get install docker-ce
    ```
    
    

# 참고

---

- https://blog.naver.com/alice_k106/220882666548
