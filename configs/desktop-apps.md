# Cherry Studio / ChatBox 桌面客户端接入配置

## Cherry Studio

1. **设置** → **模型服务** → **OpenAI**
2. **API 地址**：`https://api.rqu.cn/v1`（Cherry Studio 需要完整带 /v1）
3. **API 密钥**：`sk-你的密钥`
4. 点击"添加模型"或在对话页直接选择

## ChatBox

1. **设置** → 模型提供方选 **OpenAI API** 或 **自定义提供方**
2. **API Domain**：`https://api.rqu.cn`（ChatBox 自动补路径）
3. **API Key**：`sk-你的密钥`
4. **模型**：手动输入模型 ID

> 💡 两款客户端对"是否带 /v1"的要求不同：报 404 时优先检查这里。
