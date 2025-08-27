# --- 1단계: 빌드 ---
FROM eclipse-temurin:21-jdk-alpine AS build

# 작업 디렉토리 설정
WORKDIR /app

# Maven 설치
RUN apk add --no-cache maven

# 소스 코드 복사
COPY pom.xml .
COPY src ./src

# 애플리케이션 빌드
RUN mvn clean package -DskipTests

# --- 2단계: 실행 ---
FROM eclipse-temurin:21-jre-alpine AS runtime

# 작업 디렉토리 설정
WORKDIR /app

# 빌드된 JAR 파일 복사
COPY --from=build /app/target/*.jar app.jar

# 포트 노출
EXPOSE 8080

# 컨테이너 실행 명령어
CMD ["java", "-jar", "app.jar"]