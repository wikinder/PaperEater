# PaperEater  
arXiv の **最新2000件のコンピュータサイエンス論文** を取得して、  
**AI / AGI / ASI / LLM / OpenAI / ChatGPT / Claude / Gemini / Mistral / Sora** など  
最新トレンドに関連する論文だけを自動で絞り込んで表示する Tauri アプリです。

PaperEater は  
- 論文一覧取得  
- トレンドフィルタ  
- PDF ダウンロード（進捗表示）  
- タイトル翻訳  
をすべてローカルアプリで行えます。

---

## 主な機能

### 1. 論文カテゴリ「cs」から最新2000件取得  
`https://arxiv.org/list/cs/recent?show=2000` を自動でフェッチ。

### 2. AI系ワードで自動絞り込み（プリセットB）
以下のようなトレンド語を含む論文だけを抽出：

- AI / AGI / ASI / LLM / VLM / multimodal  
- OpenAI / GPT / ChatGPT / o1  
- Claude / Anthropic  
- Gemini / DeepMind  
- Mistral  
- LLaMA / Meta  
- Sora / diffusion  
- RAG / alignment  

### 3. PDF ダウンロード（進捗付き UI）  
ダウンロードの進行状況を円滑に可視化。

### 4. タイトル翻訳 
#### DeepL API キーを使う場合（タイトルを日本語に自動翻訳）
`index.html` にあるこの部分に API キーを入れてください：

```js
const DEEPL_API_KEY = "ここにキー";
```

#### API を使いたくない場合（デフォルト）
- DeepL キーが空だと自動翻訳はスキップ

---

## 開発環境

### 必須
- Node.js 18+
- Rust (stable)
- Tauri CLI

### セットアップ

```sh
npm install
npm run tauri dev
```

---

## ビルド方法

```sh
npm run tauri build
```

生成物は  
`src-tauri/target/release/bundle/`  
に出力されます。

---

## GitHub Actions 自動ビルド（Win / macOS 両対応）

`.github/workflows/tauri-build.yml` を実行すると、

- PaperEater-windows  
- PaperEater-macos  

が自動生成されます。

---

## プロジェクト構成

```
PaperEater/
  index.html
  README.md
  package.json
  src-tauri/
    tauri.conf.json
```

---

## ライセンス
MIT Licence
