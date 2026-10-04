# ChatGPT-Next-Web (NextChat) 接入配置

## 网页界面配置

1. 打开 NextChat → 左下角 **设置**
2. 找到 **自定义接口** 区域：
   - **接口地址**：`https://api.rqu.cn`（NextChat 会自动补 `/v1`，**不要**手动带 /v1）
   - **API Key**：`sk-你的密钥`
3. 在模型列表选择或输入模型 ID

> ⚠️ NextChat 的接口地址与其他工具不同：**不带** `/v1`。这是最容易踩的坑。

## Docker 部署

```bash
docker run -d -p 3000:3000 \
  -e OPENAI_API_KEY=sk-你的密钥 \
  -e BASE_URL=https://api.rqu.cn \
  -e CUSTOM_MODELS=gpt-4o,claude-sonnet-4-5,deepseek-chat \
  yidadaa/chatgpt-next-web
