# LobeChat 接入配置

## 网页界面配置

1. 打开 LobeChat → 左下角 **设置** → **语言模型**
2. 选择 **OpenAI** 供应商
3. 填入：
   - **API Proxy Address**：`https://api.rqu.cn/v1`
   - **API Key**：`sk-你的密钥`
4. 在模型列表添加你要用的模型 ID（如 `gpt-4o`、`claude-sonnet-4-5`）
5. 回到对话页，右上角切换模型即可

## Docker 部署（环境变量方式）

```bash
docker run -d -p 3210:3210 \
  -e OPENAI_PROXY_URL=https://api.rqu.cn/v1 \
  -e OPENAI_API_KEY=sk-你的密钥 \
  -e ACCESS_CODE=你自己设的访问码 \
  lobehub/lobe-chat
```

## 常见问题

- **报 401**：API Key 填错或多了空格
- **模型切换后报错**：自定义模型列表里没有该模型 ID，先去添加
