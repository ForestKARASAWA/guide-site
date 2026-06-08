# 家づくりガイド コーディネート編 サイト

## 公開方法（GitHub Pages）

### 1. GitHubリポジトリを作成
1. https://github.com にサインイン
2. 右上の「＋」→「New repository」
3. Repository name: `guide-site`（任意）
4. Public にチェック → 「Create repository」

### 2. ファイルをアップロード
1. 「uploading an existing file」をクリック
2. `guide-site` フォルダの中身を全て選択してドラッグ＆ドロップ
3. 「Commit changes」

### 3. GitHub Pages を有効化
1. リポジトリの「Settings」タブ
2. 左メニュー「Pages」
3. Source: 「Deploy from a branch」→ Branch: `main` / `/ (root)` → Save
4. 数分後に `https://YOUR_USERNAME.github.io/guide-site/` で公開される

---

## スタッフが写真を編集するには（Decap CMS セットアップ）

### 4. admin/config.yml を編集
`admin/config.yml` の2行目を変更:
```
repo: ForestKARASAWA/guide-site
```

### 5. Netlify で OAuth アプリを設定（1回だけ）
1. https://app.netlify.com にサインイン（無料）
2. 「Add new site」→「Import an existing project」→ GitHubと連携
3. 同じリポジトリを選択 → 「Deploy site」
4. Site settings → Identity → 「Enable Identity」
5. Identity → Registration → 「Invite only」
6. Identity → Services → Git Gateway → 「Enable Git Gateway」
7. スタッフのメールアドレスを Invite で招待

### 6. 管理画面へのアクセス
`https://YOUR_USERNAME.github.io/guide-site/admin/` を開く
→ Netlify Identity でログイン → 写真のアップロード・更新が可能

---

## フォルダ構成
```
guide-site/
├── index.html          # メインサイト
├── admin/
│   ├── index.html      # CMS管理画面
│   └── config.yml      # CMS設定
├── content/
│   └── photos.json     # 写真データ（CMSが自動更新）
├── images/
│   └── uploads/        # アップロードされた写真
└── README.md
```
