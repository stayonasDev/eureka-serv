# SPRING CLOUD discovery eureka

# Run - dev
- http://localhost:8765
```bash
$ ./gradlew clean bootRun
```

# Docker build
```bash
# 명령어 형식: docker build -t <도커허브아이디>/<이미지 이름>:<태그> <빌드 컨텍스트 경로>
$ docker build -t datamario24/sc-eureka:0.2.0 .
$ docker push datamario24/sc-eureka:0.2.0
```
