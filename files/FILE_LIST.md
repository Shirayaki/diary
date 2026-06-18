# noto プロジェクト ファイル一覧

以下は、ダウンロード可能なファイル群です。

## 📦 ダウンロード対象

### 1. **noto-complete.tar.gz** （推奨）
完全なプロジェクトファイル一式（22KB）

内容：
- React アプリケーション（全ソースコード）
- package.json、設定ファイル
- GitHub Actions ワークフロー
- デプロイ設定（Vercel, Netlify）
- ドキュメント（README, SETUP_GUIDE等）
- ライセンス、その他設定

**抽出方法：**
```bash
tar -xzf noto-complete.tar.gz
cd noto
npm install
npm start
```

---

## 📄 提供ドキュメント

### GITHUB_SETUP.md
GitHub にプッシュしてデプロイするまでの手順書。
- リポジトリ作成手順
- Git コマンド
- Vercel/Netlify でのデプロイ方法
- トラブルシューティング

### FILE_LIST.md （このファイル）
プロジェクト構成とファイル一覧。

---

## 📁 プロジェクト構成（圧縮ファイル内）

```
noto/
│
├── 📂 public/
│   ├── index.html              # アプリエントリーポイント
│   ├── manifest.json           # PWA設定
│   └── favicon.ico
│
├── 📂 src/
│   ├── 📂 components/
│   │   ├── Sidebar.js          # ナビゲーションサイドバー
│   │   ├── Sidebar.css
│   │   ├── TagInput.js         # タグ入力コンポーネント
│   │   ├── TagInput.css
│   │   ├── Toast.js            # 通知表示
│   │   └── Toast.css
│   │
│   ├── 📂 data/
│   │   ├── constants.js        # カテゴリ、色、気分アイコン定義
│   │   └── store.js            # グローバル状態管理（localStorage連携）
│   │
│   ├── 📂 hooks/
│   │   └── useStore.js         # ストア購読フック
│   │
│   ├── 📂 pages/
│   │   ├── WritePage.js        # 日記作成画面
│   │   ├── WritePage.css
│   │   ├── ListPage.js         # 日記一覧画面
│   │   ├── ListPage.css
│   │   ├── SearchPage.js       # 検索・フィルター画面
│   │   ├── SearchPage.css
│   │   ├── CalendarPage.js     # カレンダー表示
│   │   ├── CalendarPage.css
│   │   ├── KBPage.js           # 知識DB管理
│   │   ├── KBPage.css
│   │   ├── DashPage.js         # ダッシュボード（統計・グラフ）
│   │   └── DashPage.css
│   │
│   ├── App.js                  # メインアプリコンポーネント
│   ├── App.css
│   ├── index.js                # React マウントポイント
│   └── index.css               # グローバルスタイル
│
├── 📂 .github/
│   └── 📂 workflows/
│       └── ci.yml              # GitHub Actions ワークフロー
│
├── package.json                # 依存パッケージ・スクリプト定義
├── .gitignore                  # Git から除外するファイル
├── .eslintrc.json              # ESLint 設定
├── .prettierrc                 # Prettier 設定
├── README.md                   # プロジェクト説明
├── SETUP_GUIDE.md              # ローカルセットアップ詳細ガイド
├── CONTRIBUTING.md             # コントリビューション方法
├── LICENSE                     # MIT ライセンス
├── vercel.json                 # Vercel デプロイ設定
├── netlify.toml                # Netlify デプロイ設定
└── .env.example                # 環境変数テンプレート
```

---

## 🚀 クイックスタート

### 1. ファイルをダウンロード
`noto-complete.tar.gz` をダウンロード

### 2. 展開
```bash
tar -xzf noto-complete.tar.gz
cd noto
```

### 3. インストール
```bash
npm install
```

### 4. 開発サーバー起動
```bash
npm start
```

ブラウザが自動的に `http://localhost:3000` で開きます。

---

## 📝 主要ファイルの役割

| ファイル | 役割 |
|--------|------|
| `src/App.js` | ページ切り替えロジック |
| `src/components/Sidebar.js` | ナビゲーション・統計表示 |
| `src/data/store.js` | localStorage 連携のステート管理 |
| `src/pages/WritePage.js` | 日記・知識DB 作成 |
| `src/pages/SearchPage.js` | キーワード検索・フィルター |
| `src/pages/CalendarPage.js` | 月カレンダー表示 |
| `src/pages/DashPage.js` | 統計グラフ（Chart.js使用） |

---

## 🔧 技術スタック

- **React 18** — UI フレームワーク
- **Chart.js** — グラフ表示
- **CSS3** — スタイリング
- **localStorage** — ローカルデータ保存

---

## 🌐 デプロイオプション

### Vercel（最も簡単）
GitHub との連携で自動デプロイ可能。

### Netlify
ドラッグ＆ドロップ、または CLI でデプロイ。

### GitHub Pages
gh-pages パッケージで無料ホスト。

詳細は `GITHUB_SETUP.md` を参照。

---

## 💾 データ保存について

すべてのデータは **localStorage** に保存されます。

**保存キー：**
- `noto_entries` — 日記データ
- `noto_kb` — 知識DB データ

**注意：**
- ブラウザのキャッシュクリアでデータが失われます
- 複数デバイス間での同期は非対応（今後の拡張で対応予定）

---

## 📚 ドキュメント読む順序

1. **README.md** — プロジェクト概要
2. **SETUP_GUIDE.md** — ローカルセットアップ
3. **GITHUB_SETUP.md** — GitHub へのプッシュ・デプロイ
4. **CONTRIBUTING.md** — 機能追加時の手順

---

## ❓ よくある質問

**Q: npm install に時間がかかるのは？**
A: 初回は依存パッケージをダウンロードするため 5-10分かかる場合があります。

**Q: データをバックアップしたい**
A: ブラウザの DevTools (F12) → Application → localStorage でコピー可能。

**Q: 複数デバイスで同期したい**
A: 次のフェーズで Firebase 等のバックエンド実装予定。

**Q: モバイルで使いたい**
A: レスポンシブ対応済み。スマートフォンのブラウザで利用可能。

---

**最終更新**: 2025年6月
**バージョン**: 0.1.0
