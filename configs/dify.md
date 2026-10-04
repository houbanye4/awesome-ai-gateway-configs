# Dify 接入配置

## 模型供应商配置

1. 登录 Dify → 右上角 **设置** → **模型供应商**
2. 找到 **OpenAI-API-compatible**（注意不是 OpenAI），点添加模型：
   - **Model Name**：`gpt-4o`
   - **Model Type**：LLM
   - **API Key**：`sk-你的密钥`
   - **API endpoint URL**：`https://api.rqu.cn`（⚠️ Dify 这里只填根路径，**不要带** /v1）
3. 每个模型都要单独添加一条（想用 5 个模型就加 5 次）

> ⚠️ Dify 的坑：用 **OpenAI-API-compatible** 供应商而不是 **OpenAI** 供应商，
> 后者会强制走官方域名。URL 是否带 /v1 取决于 Dify 版本，报 404 时试着去掉/加上。

## Embedding 模型

同页面添加模型时把 **Model Type** 选为 `Text Embedding`，填入网关支持的 embedding 模型 ID。
