## Docker 기초

### Dockerfile 작성

| 내용    | 설명                              | 예시                  |
| ------- | --------------------------------- | --------------------- |
| FROM    | 어떤 환경을 실행할 것인가?        | <환경>                |
| WORKDIR | 작업 디렉토리를 설정              | /<경로>               |
| COPY    | 어떤 경로에다가 저장을 할 것인가? | <외부폴더> <내부폴더> |
| RUN     | 실행                              | npm install           |
| EXPOSE  | 특정 포트 지정                    | <포트>                |
| CMD     | 컨테이너 실행 후 실행할 서버      | <환경> <파일명>       |

### Docker 빌드

```
$ docker build .
```

### Docker 컨테이너 시작

```
$ docker run -p <실행포트:현재포트> <id>
```

### Docker 컨테이너 중지

```
$ docker ps
$ docker stop <name>
```

### Docker 모든 컨테이너 불러오기

```
$ docker ps -a
```

### Docker 컨테이너에서 Node.js 실행

```
$ docker run node
```

### Docker 컨테이너 내부의 터미널 모드에서 Node.js 실행

```
$ docker run -it node
```
