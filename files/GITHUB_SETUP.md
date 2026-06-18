# noto - GitHub セットアップガイド

このガイドでは、ダウンロードしたファイルを GitHub にプッシュする手順を説明します。

## ステップ 1: GitHub リポジトリを作成

1. GitHub.com にログイン
2. 右上の「+」アイコン → 「New repository」をクリック
3. リポジトリ名を入力（例：`noto`）
4. 説明を追加（例：「日記・知識DB・カレンダーが統合された個人向け Webアプリ」）
5. 「Public」を選択
6. 「Create repository」をクリック

## ステップ 2: ローカルに展開してセットアップ

```bash
# ダウンロードした圧縮ファイルを展開
tar -xzf noto-complete.tar.gz
cd noto

# Git を初期化（まだしていない場合）
git init

# 作成者情報を設定
git config user.name "Your Name"
git config user.email "your@email.com"

# すべてのファイルをステージング
git add .

# 初期コミット
git commit -m "Initial commit: noto diary app"

# main ブランチにリネーム（デフォルトが master の場合）
git branch -M main

# リモートリポジトリを追加
git remote add origin https://github.com/yourusername/noto.git

# GitHub にプッシュ
git push -u origin main
```

## ステップ 3: GitHub Pages でホスト（オプション）

リポジトリの本番版を無料でホストできます。

### 方法A: Vercel（推奨）

最も簡単なデプロイ方法です。

1. [Vercel.com](https://vercel.com) にアクセス
2. GitHub アカウントでサインアップ
3. 「Import Git Repository」をクリック
4. GitHub のリポジトリを選択
5. 環境変数設定（デフォルトで OK）
6. 「Deploy」をクリック

数秒でデプロイ完了。自動的に URL が割り当てられます。

### 方法B: Netlify

```bash
# 本番ビルド
npm run build

# Netlify CLI をインストール
npm install -g netlify-cli

# デプロイ
netlify deploy --prod --dir=build
```

### 方法C: GitHub Pages

`package.json` を編集：

```json
"homepage": "https://yourusername.github.io/noto",
```

デプロイスクリプト追加：

```bash
npm install --save-dev gh-pages
```

`package.json` の scripts に追加：

```json
"predeploy": "npm run build",
"deploy": "gh-pages -d build"
```

実行：

```bash
npm run deploy
```

https://yourusername.github.io/noto でアクセス可能になります。

## ステップ 4: CI/CD を有効化

このリポジトリには GitHub Actions ワークフロー（`.github/workflows/ci.yml`）が含まれています。

プッシュ時に自動的に以下が実行されます：
- Node.js 16.x, 18.x でテスト
- ビルド成功確認

## ファイル構成確認

ダウンロードされたファイル：

```
noto/
├── public/              # HTML、マニフェスト等
├── src/                 # React ソースコード
│   ├── components/      # コンポーネント
│   ├── data/           # 定数、ストア
│   ├── hooks/          # React フック
│   ├── pages/          # ページコンポーネント
│   ├── App.js
│   ├── index.js
│   └── index.css
├── package.json         # 依存パッケージ
├── README.md            # プロジェクト説明
├── SETUP_GUIDE.md       # セットアップガイド
├── CONTRIBUTING.md      # コントリビューション方法
├── LICENSE              # MIT ライセンス
├── vercel.json          # Vercel 設定
├── netlify.toml         # Netlify 設定
├── .github/workflows/   # GitHub Actions
├── .gitignore
├── .eslintrc.json
└── .prettierrc
```

## デプロイ後の確認事項

- ✅ 日記の作成・編集が動作するか
- ✅ 検索・フィルターが動作するか
- ✅ カレンダーが表示されるか
- ✅ ダッシュボードのグラフが表示されるか
- ✅ localStorage でデータが保存されているか（ブラウザの DevTools で確認）

## トラブルシューティング

### デプロイ後、ページが 404 エラー

GitHub Pages の場合、`homepage` フィールドが正しく設定されているか確認してください：

```json
"homepage": "https://yourusername.github.io/noto"
```

### npm install でエラー

```bash
npm cache clean --force
npm install
```

### ポート 3000 がすでに使用中

```bash
PORT=3001 npm start
```

## リポジトリの管理

### ブランチ戦略

```bash
# 開発用ブランチを作成
git checkout -b develop

# 機能ブランチを作成
git checkout -b feature/awesome-feature

# 開発後、develop にマージ
git checkout develop
git merge feature/awesome-feature

# 本番リリース時に main にマージ
git checkout main
git merge develop
git push origin main
```

### コミットメッセージ規約

```
[type]: description

# types:
# - feat: 新機能
# - fix: バグ修正
# - docs: ドキュメント
# - style: コード整形
# - refactor: リファクタリング
# - perf: パフォーマンス改善
# - test: テスト追加
# - chore: その他

# 例：
# feat: 日記のエクスポート機能を追加
# fix: 検索画面のバグを修正
# docs: セットアップガイドを更新
```

## 次のステップ

1. GitHub リポジトリで README を確認
2. Issues/Discussions で機能リクエストを管理
3. ローカルで機能開発 → GitHub へプッシュ
4. Vercel/Netlify で自動デプロイ

## さらに詳しく

- `README.md` — プロジェクト概要
- `SETUP_GUIDE.md` — ローカルセットアップ詳細
- `CONTRIBUTING.md` — コントリビューション方法

---

**質問やトラブルがあれば、GitHub Issues で報告してください！**
