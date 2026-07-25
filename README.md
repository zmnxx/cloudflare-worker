# Cloudflare Workers

多个独立 Worker 位于 `workers/` 目录。每个 Worker 都有独立的入口文件和 `wrangler.toml`，需要分别部署。

## 目录

- `workers/pinyin/`：当前拼音 Worker，入口 `pinyin-worker.js`
- `workers/translate/`：预留翻译 Worker
- `workers/base64/`：预留 Base64 Worker

## 部署拼音 Worker

Cloudflare Git 部署时，将 Root directory 设置为 `workers/pinyin`，Deploy command 设置为：

```sh
npx wrangler deploy
```

然后在 Cloudflare Worker 的 Variables and Secrets 中设置 `API_KEY`。

使用 Wrangler：

```sh
cd workers/pinyin
npx wrangler secret put API_KEY
npx wrangler deploy
```
