# dynamodb-admin-docker-compose

AWS Dynamodb 서비스에 연결하여 GUI로 관리하는 서비스를 docker-compose로 작성한 repo 입니다.

✅ **개발용 Dynamodb**에 연결해서 사용하세요.  
❌ **운영 Dynamodb** 연동은 보안상 문제가 있으니 연결하지 마세요.

자신 Local dynamodb에 접속하여 테이블 내용을 확인하는 용도를 주로 사용하세요.

<br>

## 사전 조건

`docker-compose.override.yml` 파일을 만들어 설정값을 적어주세요.

* `docker-compose.override.yml.sample` 파일을 복사해 이용하세요.
* `docker-compose.override.yml` 파일은 gitignore 됩니다. 

**설정 예시**

```yaml
version: '3'

services:
  dynamodb-admin:
    ports:
      - 8001:8001

    environment:
      DYNAMO_ENDPOINT: "http://<MY_IP_ADDRESS>:8000"
```

<br>

## 사용법

아래 명령으로 Admin 웹을 실행하세요.

```bash
docker-compose up -d
```

실행한 Admin 웹은 아래 URL로 접속하세요. 만약 Port를 변경했다면 해당 Port로 접속하세요.

Admin 웹 URL: http://localhost:8001

<br>

## 참고자료

* https://medium.com/swlh/a-gui-for-local-dynamodb-dynamodb-admin-b16998323f8e
