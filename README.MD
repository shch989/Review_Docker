## Docker 이미지 & 컨테이너: 코어 빌딩 블록

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
| Atteched | 터미널이 잠기는 대신 터미널과 연결 된다. | -a     |
| Detached | 터미널이 잠기지 않고 터미널과 분리 된다. | -d     |

### Docker Atteched로 변경 2가지

```
$ docker attach <name> /* Atteched 모드로 변경 */
$ docker logs <name> /* 이전의 로그를 볼 수 있음(변경 아님) */
$ docker logs -f <name> /* Atteched 모드로 변경 */
```

### Docker 실행 중인 컨테이너

```
$ docker ps
```

### Docker 컨테이너 중지

```
$ docker stop <name>
```

### Docker 모든 컨테이너 불러오기

```
$ docker ps -a
```

### Docker 모든 이미지 불러오기

```
$ docker images
```

### Docker 중지 된 컨테이너 삭제

```
$ docker rm <name> <name> ...
```

### Docker 이미지 삭제

```
$ docker rmi <ID> <ID> ...
```

### Docker 사용 안하는 이미지 모두 삭제

```
$ docker image prume
```

### Docker 컨테이너에서 Node.js 실행

```
$ docker run node
```

### Docker 컨테이너 내부의 터미널 모드에서 Node.js 실행

```
$ docker run -it node
```

### Docker 이미지 검사

```
$ docker image inspect <ID>
```

### Docker 컨테이너에서 컨테이너로 복붙

```
$ docker cp <폴더명>/<범위> <name>:/<복사할 폴더명>
$ docker cp <name>:/<복사한 폴더명> <폴더명>
```

### Docker 컨테이너와 이미지에 이름 & 태그 지정

```
$ docker build -t <REPOSITORY>:<TAG> .
$ docker run -p <실행포트:내부포트> <name> <REPOSITORY>:<TAG>
```

### Docker --help 기능

| 내용        | 설명                                       | 플래그 |
| ----------- | ------------------------------------------ | ------ |
| Atteched    | 터미널이 잠기는 대신 터미널과 연결 된다.   | -a     |
| Detached    | 터미널이 잠기지 않고 터미널과 분리 된다.   | -d     |
| Interactive | 인터렉티브 모드(컨테이너에 값을 입력 가능) | -i     |
| TTY(의사)   | 터미널을 생성                              | -t     |
| Remove      | 컨테이너가 종료될 때 자동으로 제거         | --rm   |
| Name        | 컨테이너의 이름 지정                       | --name |

### Docker Hub에 push하기

```
$ docker login /* Docker Hub 로그인 */
$ docker tag <goals>:<TAG> <DockerHub_Username>/<Repository>
$ docker push <DockerHub_Username>/<Repository>
$ docker logout /* Docker Hub 로그아웃 */
```

### Docker Hub에 pull하기

```
$ docker pull <DockerHub_Username>/<Repository>
```

## Docker 데이터 관리 및 볼륨으로 작업하기
