# 🎯 noto - はじめにお読みください

日記・知識DB・カレンダー・ダッシュボード統合 Webアプリ **noto** へようこそ！

このドキュメントでは、ダウンロードしたファイルを使ってプロジェクトを始める方法を説明します。

---

## 📦 ダウンロードしたファイル

### アーカイブ（3種類から選択）

| ファイル名 | サイズ | 説明 |
|-----------|--------|------|
| **noto-complete.tar.gz** | 22KB | **推奨** 完全なプロジェクト一式（tar形式） |
| noto-complete.zip | 44KB | 完全なプロジェクト一式（zip形式） |
| noto-app.tar.gz | 18KB | ソースコードのみ（tar形式） |

**どれを選ぶ？**
- **Windows**: `.zip` をダウンロード（解凍ツール標準搭載）
- **Mac/Linux**: `.tar.gz` をダウンロード（ターミナルで解凍可能）

### ドキュメント（すべてお読みください）

| ファイル | 内容 |
|---------|------|
| **FILE_LIST.md** | ファイル構成・プロジェクト概要 |
| **GITHUB_SETUP.md** | GitHub へのプッシュ・デプロイ手順 |

圧縮ファイル内にも含まれています：
- `README.md` — プロジェクト説明
- `SETUP_GUIDE.md` — セットアップ詳細
- `CONTRIBUTING.md` — コントリビューション方法

---

## 🚀 最速スタート（5分で開始）

### Step 1: ファイルを展開

**Windows (PowerShell):**
```powershell
# Explorerで右クリック → 「すべて展開」
# または PowerShellで：
Expand-Archive -Path noto-complete.zip -DestinationPath .
cd noto
```

**Mac/Linux:**
```bash
tar -xzf noto-complete.tar.gz
cd noto
```

### Step 2: 依存パッケージをインストール

```bash
npm install
```

初回は 5-10分かかります。☕ 待ってください。

### Step 3: 開発サーバーを起動

```bash
npm start
```

ブラウザが自動的に開き、`http://localhost:3000` に接続されます。

**おめでとうございます！🎉 アプリが起動しました。**

---

## 📖 次に読むべきドキュメント

### 1️⃣ 当プロジェクトについて学ぶ
ダウンロードしたファイルを展開して開く：
```
noto/README.md
```

### 2️⃣ ローカル環境でのセットアップ詳細
```
noto/SETUP_GUIDE.md
```

### 3️⃣ GitHub にプッシュしてデプロイする
```
GITHUB_SETUP.md  （このフォルダにあります）
```

### 4️⃣ コードを編集・拡張する方法
```
noto/CONTRIBUTING.md
```

---

## 🎮 アプリの使い方

展開したアプリで、以下の機能を試せます。

### 日記を書く
1. 左のナビゲーションから「日記を書く」をクリック
2. タイトルと内容を入力
3. カテゴリ・気分を選択
4. タグを追加（Enterキーで確定）
5. 右パネルで「知識を追加する」で気づきを同時記録
6. 「保存する」をクリック

### 日記を検索
「検索・フィルター」から：
- キーワード入力
- カテゴリ・タグ・気分で絞り込み
- 並び替え（新しい順 / 古い順 / タイトル順）

### カレンダーで確認
「カレンダー」から：
- 月表示で記録日を視覚化
- 日付をクリックして詳細表示

### ダッシュボード
「ダッシュボード」から：
- 月別投稿グラフ
- カテゴリ分布
- タグクラウド
- 気分の統計

---

## 💻 VSCode での開発

### プロジェクトをVSCodeで開く

```bash
code noto
```

または VSCode → ファイル → フォルダを開く → `noto` を選択

### 推奨拡張機能

- **ES7+ React/Redux/React-Native snippets**
- **Prettier - Code formatter**
- **ESLint**
- **Thunder Client**（API テスト用）

### デバッグ

```bash
# 開発サーバーを起動（デバッグ対応）
npm start
```

ブラウザの DevTools (F12) を開いてコンソール、Elements タブを活用します。

---

## 🌐 GitHub へプッシュ＆デプロイ

### GitHub リポジトリを作成して公開

```bash
git init
git add .
git commit -m "Initial commit: noto diary app"
git branch -M main
git remote add origin https://github.com/yourusername/noto.git
git push -u origin main
```

詳しくは `GITHUB_SETUP.md` を参照。

### Vercel で自動デプロイ（最も簡単）

1. [vercel.com](https://vercel.com) にアクセス
2. GitHub で認証
3. リポジトリを選択
4. 「Deploy」をクリック

完了！自動的に URL が割り当てられます。

---

## 🆘 トラブルシューティング

### npm install でエラー

```bash
npm cache clean --force
npm install
```

### ポート 3000 がすでに使用中

```bash
PORT=3001 npm start
```

### ブラウザに古いデータが表示される

DevTools を開いて localStorage をクリア：
```javascript
localStorage.clear();
```

その他のトラブルは `SETUP_GUIDE.md` の「トラブルシューティング」セクションを参照。

---

## 📋 チェックリスト

セットアップが完了したことを確認：

- [ ] ファイルを展開した
- [ ] `npm install` を実行した
- [ ] `npm start` で開発サーバーが起動した
- [ ] ブラウザで `http://localhost:3000` にアクセスできた
- [ ] 日記を1件作成した
- [ ] 検索・フィルターが動作した
- [ ] カレンダーが表示された
- [ ] ダッシュボードのグラフが表示された

---

## 📚 リソース

| 項目 | ファイル/URL |
|------|------------|
| プロジェクト概要 | `noto/README.md` |
| セットアップ詳細 | `noto/SETUP_GUIDE.md` |
| GitHub 連携 | `GITHUB_SETUP.md` |
| ファイル一覧 | `FILE_LIST.md` |
| コントリビューション | `noto/CONTRIBUTING.md` |
| React 公式ドキュメント | https://react.dev |
| Chart.js | https://www.chartjs.org |

---

## 🤝 次のステップ

### 開発を続ける場合

1. VSCode でプロジェクトを開く
2. `npm start` で開発サーバーを起動
3. ファイルを編集すると自動的にホットリロード
4. 新機能を追加
5. GitHub にプッシュ

### 本番環境にデプロイする場合

1. 本番ビルド：`npm run build`
2. `GITHUB_SETUP.md` に従い Vercel/Netlify/GitHub Pages を選択
3. 自動デプロイ設定

### チームで開発する場合

1. GitHub Organization を作成
2. リポジトリをメンバーと共有
3. ブランチ戦略を決定（`main` / `develop`）
4. Pull Request で コードレビュー

---

## ✨ 今後の拡張案

このプロジェクトは以下の機能追加が計画されています：

- ☁️ クラウド同期（Firebase / Supabase）
- 🤖 Claude API を使った AI 自動サマリー
- 📊 より詳細な統計分析
- 🌙 ダークモード
- 📱 モバイルアプリ化
- 📤 データエクスポート（PDF, CSV）

---

## 💬 質問・バグ報告

- GitHub Issues で質問やバグを報告してください
- Discussions で機能リクエストを共有してください
- Pull Requests でコード貢献ができます

---

## 📄 ライセンス

このプロジェクトは **MIT ライセンス** で公開されています。
自由に使用・改変・配布できます。詳細は `noto/LICENSE` を参照。

---

## 🎯 まとめ

1. **このファイルを読む** ✅ 完了
2. **ファイルを展開する**
3. **`npm install` を実行する**
4. **`npm start` で起動する**
5. **各ドキュメントを読む**
6. **開発を進める**

それでは、楽しい開発を！🚀

---

**質問があれば、気軽に GitHub Issues で報告してください。**

**最終更新**: 2025年6月
**バージョン**: 0.1.0
