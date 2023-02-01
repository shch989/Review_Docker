## Docker 기초

### Dockerfile 작성

| 내용    | 설명                                      | 예시                  |
| ------- | ----------------------------------------- | --------------------- |
| FROM    | 어떤 이미지를 실행할 것인가?              | <이미지>              |
| WORKDIR | 작업 디렉토리를 설정                      | /<경로>               |
| COPY    | 어떤 코드와 어떤 종속성이 복사될 것인가?  | <외부폴더> <내부폴더> |
| RUN     | npm install과 같은 설정단계가 요구되는가? | npm install           |
| EXPOSE  | 내부 포트 지정                            | <포트>                |
| CMD     | 컨테이너 실행 후 실행할 이미지            | <이미지> <파일명>     |

### Docker 이미지 구축

```
$ docker build .
```

### Docker 컨테이너 시작

##### Atteched 모드는 디폴트.

```
$ docker run -p <실행포트:내부포트> <id>
```

### Docker 컨테이너 재시작

##### Detached 모드는 디폴트.

```
$ docker start <name>
```

### Atteched와 Detached 차이

| 내용     | 설명                                     | 플래그 |
| -------- | ---------------------------------------- | ------ |
| Atteched | 터미널이 잠기는 대신 터미널과 연결 된다. | 보기   |
| Detached | 터미널이 잠기지 않고 터미널과 분리 된다. | -d     |

### Docker Atteched로 변경 2가지

```
$ docker attach <name> /* Atteched 모드로 변경 */
$ docker logs <name> /* 이전의 로그를 볼 수 있음(변경 아님) */
$ docker logs -f <name> /* Atteched 모드로 변경 */
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
