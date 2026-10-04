# OpenAI SDK 接入配置

## Python

```python
from openai import OpenAI

client = OpenAI(
    api_key="sk-你的密钥",
    base_url="https://api.rqu.cn/v1",   # ← 唯一要改的地方
)

resp = client.chat.completions.create(
    model="gpt-4o",
    messages=[{"role": "user", "content": "你好"}],
)
print(resp.choices[0].message.content)
```

## Node.js / TypeScript

```javascript
import OpenAI from "openai";

const client = new OpenAI({
  apiKey: "sk-你的密钥",
  baseURL: "https://api.rqu.cn/v1",    // ← 唯一要改的地方
});

const resp = await client.chat.completions.create({
  model: "deepseek-chat",
  messages: [{ role: "user", content: "你好" }],
});
console.log(resp.choices[0].message.content);
```

## curl

```bash
curl https://api.rqu.cn/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer sk-你的密钥" \
  -d '{"model": "gpt-4o", "messages": [{"role": "user", "content": "hi"}]}'
```

## 流式输出

SDK 的 `stream=True` 用法完全不变，网关原样转发 SSE。
