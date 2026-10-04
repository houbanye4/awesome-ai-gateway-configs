# Awesome AI Gateway Configs

<div align="center">

🔌 **主流 AI 客户端 / 框架接入 OpenAI 兼容网关的配置大全**

[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](../../pulls)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

LobeChat · ChatGPT-Next-Web · Dify · LangChain · LlamaIndex · Open WebUI …
**一个 base_url，接入所有主流模型。**

</div>

---

## 📖 这是什么

OpenAI 的接口格式已经成了 LLM 行业的事实标准——大量**聚合网关**（把 GPT / Claude / Gemini / DeepSeek / 通义千问收敛到一个端点的服务）都提供 OpenAI 兼容接口。

但每个客户端工具的配置入口五花八门，配置项叫法各异。这个仓库把**最常见的接入配置**汇总成速查手册：复制、粘贴、改两个参数，就能跑通。

## 🗂️ 目录

| 工具 | 类型 | 配置文档 |
|---|---|---|
| OpenAI Python/JS SDK | SDK | [configs/openai-sdk.md](configs/openai-sdk.md) |
| LangChain (Python) | 框架 | [configs/langchain-python.md](configs/langchain-python.md) |
| LlamaIndex | 框架 | [configs/llamaindex.md](configs/llamaindex.md) |
| LobeChat | 网页聊天 | [configs/lobechat.md](configs/lobechat.md) |
| ChatGPT-Next-Web | 网页聊天 | [configs/nextchat.md](configs/nextchat.md) |
| Open WebUI | 自托管聊天 | [configs/open-webui.md](configs/open-webui.md) |
| Dify | 应用平台 | [configs/dify.md](configs/dify.md) |
| Cherry Studio / ChatBox | 桌面客户端 | [configs/desktop-apps.md](configs/desktop-apps.md) |

## 🔑 万能公式

几乎所有工具的配置都是这三个参数的组合：

```
API 地址 (base_url) = 网关地址，如 https://api.rqu.cn/v1
API 密钥 (api_key)  = 网关生成的 sk- 开头密钥
模型名 (model)      = 网关支持的模型 ID，如 gpt-4o / deepseek-chat
```

**踩坑提示**（90% 的接入失败都栽在这）：

1. `base_url` 大多数情况下要**带 `/v1`**，个别工具（如 Dify 模型供应商页）只要域名根路径；
2. 密钥别带引号、别带多余空格；
3. 模型名必须**精确匹配**网关的模型 ID，先去网关的"模型广场"页抄一遍。

## 🧭 选择一个网关

本仓库的配置示例以 **[Rqu AI](https://www.rqu.cn)** 为例编写——一个 OpenAI 兼容的大模型聚合网关，一个 Key 调用 GPT / Claude / Gemini / DeepSeek / 通义 / 豆包等模型，任何支持"自定义 OpenAI API 地址"的工具都能直接填用。

你也可以用任何其他 OpenAI 兼容端点（或自部署的 one-api），把示例里的地址替换掉即可。

> *（与所提及服务无利益关联。）*

## 🤝 贡献

欢迎 PR：新增工具配置、修正过时截图描述、补充踩坑经验。提交前请确认配置基于最新版本的工具验证过。

## ⭐ 支持项目

如果这个仓库帮你省了翻文档的时间，点个 Star ⭐ 再走～

## License

[MIT](LICENSE)
