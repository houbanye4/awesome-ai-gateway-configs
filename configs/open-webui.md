# Open WebUI 接入配置

## 管理面板配置

1. 登录 Open WebUI → 右上角头像 → **管理员面板**
2. **设置** → **外部连接**
3. 添加 OpenAI 连接：
   - **URL**：`https://api.rqu.cn/v1`
   - **密钥**：`sk-你的密钥`
4. 保存后会自动拉取模型列表
5. 新建对话时在顶部选择模型

## Docker 部署

```bash
docker run -d -p 3000:8080 \
  -e OPENAI_API_BASE_URL=https://api.rqu.cn/v1 \
  -e OPENAI_API_KEY=sk-你的密钥 \
  -v open-webui:/app/backend/data \
  ghcr.io/open-webui/open-webui:main
```
