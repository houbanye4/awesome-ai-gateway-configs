# LlamaIndex 接入配置

## 全局默认配置

```python
from llama_index.core import Settings
from llama_index.llms.openai_like import OpenAILike
from llama_index.embeddings.openai import OpenAIEmbedding

Settings.llm = OpenAILike(
    model="gpt-4o",
    api_key="sk-你的密钥",
    api_base="https://api.rqu.cn/v1",   # ← 关键参数
    is_chat_model=True,                  # 必须显式声明，否则可能走 completion 接口
)

Settings.embed_model = OpenAIEmbedding(
    model="text-embedding-3-small",
    api_key="sk-你的密钥",
    api_base="https://api.rqu.cn/v1",
)
```

## 单次调用指定

```python
from llama_index.llms.openai_like import OpenAILike

llm = OpenAILike(
    model="deepseek-chat",
    api_key="sk-你的密钥",
    api_base="https://api.rqu.cn/v1",
    is_chat_model=True,
)
print(llm.complete("你好").text)
```

## 常见问题

- **报错 `is_chat_model` 相关**：OpenAILike 必须设置 `is_chat_model=True`，这是 LlamaIndex 区分 chat/completion 接口的开关；
- **用 OpenAI 类代替 OpenAILike**：也可以直接用 `llama_index.llms.openai.OpenAI`，多传一个 `api_base` 参数，但部分严格校验域名的版本会不兼容。
