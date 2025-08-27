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
#example: docker build --build-arg GITHUB_TOKEN=sdsdsd1234  -t client .
docker build --build-arg GITHUB_TOKEN=your-token  -t client .

#example: docker run -e GITHUB_TOKEN=sdsdsd1234 -p 8081:8080 --name client client
docker run -e GITHUB_TOKEN=your-token -p 8081:8080 --name client client
```
