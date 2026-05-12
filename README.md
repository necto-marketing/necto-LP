# Necto 不動産向けLP

不動産会社向け AI業務効率化・集客支援サービス「Necto」のランディングページ。

## ファイル構成

```
necto-realestate-lp/
├─ index.html         … LP本体（単一HTML、Tailwind CDN）
├─ README.md          … このファイル
├─ posts/
│  ├─ threads.md      … Threads 投稿テンプレ（5本）
│  └─ instagram.md    … Instagram 投稿テンプレ（フィード3本＋ストーリーズ）
└─ assets/
   ├─ logo.png        … ★Nectoロゴ画像を配置
   ├─ line-qr.png     … ★公式LINE QRコード画像を配置
   ├─ favicon.png     … 任意
   └─ ogp.png         … 任意（OGP用 1200×630）
```

## 公開前にやること

### 1. 画像の配置
`assets/` フォルダに以下を入れてください。

| ファイル名 | 内容 | 推奨サイズ |
|---|---|---|
| `logo.png` | Nectoロゴ（提供済み） | 横長、PNG透過 |
| `line-qr.png` | LINE公式アカウントQR | 正方形（512px以上推奨） |
| `favicon.png` | ブラウザタブ用 | 64×64 / 任意 |
| `ogp.png` | SNSシェア用カード | 1200×630 / 任意 |

### 2. リンクの差し替え
`index.html` 内の以下を実値に置換してください。

| 箇所 | 現在の値 | 差し替え |
|---|---|---|
| LINE友だち追加URL | `https://line.me/R/ti/p/@your-line-id` | 実際のLINE URL |
| Threads URL | `<a href="#" aria-label="Threads">` の `#` | 実際のThreads URL |
| Instagram URL | `<a href="#" aria-label="Instagram">` の `#` | 実際のInsta URL |

### 3. AI診断ツールリンク
3か所すべて `https://necto-marketing.github.io/shindan/` で実値設定済み。

## 公開方法（オススメ順）

### A. GitHub Pages（診断ツールと同じ org に置く）
1. `necto-marketing` org に `lp` リポジトリを作成
2. このフォルダをまるごと push
3. Settings → Pages → Branch: `main` / Root を選択
4. 公開URL：`https://necto-marketing.github.io/lp/`

### B. Netlify Drop
[app.netlify.com/drop](https://app.netlify.com/drop) にフォルダごとドラッグ＆ドロップで即公開。

### C. Vercel
`vercel deploy` で即公開。カスタムドメインを当てたい場合に最適。

## デザイン設計

- メインカラー：emerald系（`brand-500: #10B981`）
- アクセント：ネイビー（`ink-900: #0B2447`）
- ロゴのブルー→グリーングラデーションを `gradient-text` / `gradient-bg` で再現
- フォント：Noto Sans JP（Google Fonts）
- 単一HTML + Tailwind CDN、JS依存なし（FAQの開閉のみ `<details>` で実装）
