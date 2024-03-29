## 컨테이너
> container 명령어를 붙혀야 하거나, 붙히지 않았을 때 바뀌는 명령어

`docker container COMMAND`
- `docker container prune [OPTIONS]` 중지된(stopped) 모든 컨테이너 삭제
- `docker container ls [OPTIONS], docker ps [OPTIONS]` 컨테이너 리스트 조회
  - `-a` 모든 컨테이너 리스트 조회

> container 명령어를 붙히지 않고 실행 가능한 명령어

`docker COMMAND`
- `run [OPTIONS] IMAGE [COMMAND] [ARG...]` 컨테이너 생성 및 실행 (create and start)
  - `-d, --detach` 백그라운드에서 컨테이너 실행
  - `--name string` 컨테이너 이름 지정
  - `-p, --publish list` 컨테이너 포트를 호스트에 연결 ***hostPort:containerPort***
  - `--env list` 환경 변수 설정
- `create [OPTIONS] IMAGE [COMMAND] [ARG...]` 컨테이너 생성
  - `run`과 비슷
- `start [OPTIONS] CONTAINER [CONTAINER...]` 컨테이너 실행
  - `-a` 기존 로그 및 지속적 로그 조회 (터미널 진입) 
  - `-i` 기존 로그 조회
- `restart [OPTIONS] CONTAINER [CONTAINER...]` 컨테이너 재실행
- `pause CONTAINER [CONTAINER...]` 컨테이너 일시정지
- `unpause CONTAINER [CONTAINER...]` 컨테이너 일시정지 해제
- `stop [OPTIONS] CONTAINER [CONTAINER...]` 컨테이너 중지
- `rm [OPTIONS] CONTAINER [CONTAINER...]` 컨테이너 삭제
  - `-f, --force` 실행 중인 컨테이너 중지 및 삭제
- `inspect [OPTIONS] CONTAINER [CONTAINER...]` 컨테이너 상세 정보 조회
- `logs [OPTIONS] CONTAINER` 컨테이너 로그 조회
  - `-f` 지속적 로그 조회 (터미널 진입)

## 이미지
`docker image COMMAND`
- `ls [OPTIONS] [REPOSITORY[:TAG]]` 이미지 리스트 조회
  - `-a` 모든 이미지 리스트 조회
- `inspect [OPTIONS] IMAGE [IMAGE...]` 이미지 상세 정보 조회
- `rm [OPTIONS] IMAGE [IMAGE...]` 이미지 삭제
