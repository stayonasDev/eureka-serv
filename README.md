# SPRING CLOUD discovery eureka

# Run - dev
- http://localhost:8765
```bash
$ ./gradlew clean bootRun
```

# Docker build
```bash
# 명령어 형식: docker build -t <도커허브아이디>/<이미지 이름>:<태그> <빌드 컨텍스트 경로>
$ docker build -t stayonasdev/sc-eureka:0.2.0 .
$ docker push stayonasdev/sc-eureka:0.2.0
```
# Use Compose
```bash
services:
  eureka-server:
    # 유레카 서버의 도커 이미지 이름
    image: stayonasdev/sc-eureka:0.2.0 
    container_name: eureka-server
    ports:
      # 외부 포트:컨테이너 내부 포트 (외부에서 접근 시 필요)
      - "8765:8765" 
    environment:
      # application.yml의 설정을 오버라이드
      # defaultZone의 localhost:8765를 컨테이너 이름(eureka-server)으로 변경 덮어 쓰기
      - EUREKA_CLIENT_SERVICEURL_DEFAULTZONE=http://eureka-server:8765/eureka/
      # spring.application.name 변경 필요 하다면
      - SPRING_APPLICATION_NAME=d-service
```
