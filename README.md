# 목표: Java 기반 MCP 서버, MCP 호스트와 연결된 클라이언트 구축  
- **MCP 호스트**: 생성형 AI 모델  
    - GitHub에서 제공하는 무료 GPT 4o mini 모델  
- **MCP 클라이언트**: 생성형 AI 모델 <-> MCP 서버  
    - GitHub에서 제공하는 무료 GPT 4o mini 모델 API와 지식/액션 도구 API를 LangChain4j(SDK)를 사용해 호출
    - Spring Boot 기반 앱
- **MCP 서버**: 지식/액션 도구
    - 계산기 기능(액션)을 가진 SpringBoot 기반 앱

## 0. 사전 준비
- Docker or Docker Desktop
- npx(npm)

  
## 1. MCP 서버
```bash
cd calculator-server
docker build -t mcp-server .
docker run -p 8080:8080 --name calculator-container mcp-server
```
```bash
npx @modelcontextprotocol/inspector
```

## 2. MCP 호스트서버 API 정보 가져오기



## 3. MCP 클라이언트
```bash
cd client

#example: docker build --build-arg GITHUB_TOKEN=sdsdsd1234  -t client .
docker build --build-arg GITHUB_TOKEN=your-token  -t client .

#example: docker run -e GITHUB_TOKEN=sdsdsd1234 -p 8081:8080 --name client client
docker run -e GITHUB_TOKEN=your-token -p 8081:8080 --name client client
```
