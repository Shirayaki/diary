# noto — 日記・知識データベースアプリ

## セットアップ

```bash
npm install
npm start
```

ブラウザで http://localhost:3000 が開きます。

## 構成

- `src/data/store.js` — グローバルステート（localStorageに自動保存）
- `src/data/constants.js` — カテゴリ・気分などの共通定義
- `src/pages/` — 画面ごとのコンポーネント（write / list / search / calendar / kb / dashboard）
- `src/components/` — Sidebar・Toast・TagInputなどの共通パーツ

## データの永続化について

現在はブラウザの localStorage にデータを保存しています。
複数デバイスでの同期や本番運用が必要な場合は、`src/data/store.js` を
Supabase や Firebase などのバックエンドに置き換えてください。
