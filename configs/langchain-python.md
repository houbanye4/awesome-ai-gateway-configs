# LangChain (Python) 接入配置

## ChatOpenAI（推荐）

```python
from langchain_openai import ChatOpenAI

llm = ChatOpenAI(
    model="gpt-4o",
    api_key="sk-你的密钥",
    base_url="https://api.rqu.cn/v1",   # ← 关键参数
    temperature=0.7,
)

print(llm.invoke("你好，介绍一下你自己").content)
```

## 多模型混用

聚合网关下可以给不同链配不同模型：

```python
fast_llm = ChatOpenAI(model="deepseek-chat", api_key=key, base_url=base)
smart_llm = ChatOpenAI(model="claude-sonnet-4-5", api_key=key, base_url=base)
```

## Embeddings

```python
from langchain_openai import OpenAIEmbeddings

emb = OpenAIEmbeddings(
    model="text-embedding-3-small",
    api_key="sk-你的密钥",
    base_url="https://api.rqu.cn/v1",
)
```

> 注意：确认网关支持对应 embedding 模型；不支持时在网关的模型广场查可用列表。
