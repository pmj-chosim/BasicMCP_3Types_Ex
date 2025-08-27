# --- 1단계: 빌드 ---
FROM eclipse-temurin:21-jdk-alpine AS build

# 작업 디렉토리 설정
WORKDIR /app

# 빌드 시에 외부에서 GITHUB_TOKEN을 인자로 받습니다.
ARG GITHUB_TOKEN

# GITHUB_TOKEN을 환경 변수로 설정합니다.
ENV GITHUB_TOKEN=$GITHUB_TOKEN

# Maven 빌드 의존성 관리를 위해 pom.xml 복사
COPY pom.xml .

# 소스 코드 복사
COPY src ./src

# Maven 패키지 설치
RUN apk add --no-cache maven

# 애플리케이션 빌드 (테스트 건너뛰기)
RUN mvn clean package -DskipTests

# --- 실행 스테이지 ---
FROM eclipse-temurin:21-jre-alpine

# 작업 디렉토리 설정
WORKDIR /app

# 빌드 스테이지에서 생성된 JAR 파일 복사
COPY --from=build /app/target/*.jar app.jar

# 애플리케이션 실행 명령어
ENTRYPOINT ["java", "-jar", "app.jar"]