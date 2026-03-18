# Portfolio Site

静的HTML/CSS/JavaScriptで構成したポートフォリオサイトです。  
`index.html` へアクセスすると、トップページとして扱う `yh_portfolio/profile.html` にリダイレクトされます。

## サイト概要

- Profile: ドーナツ型メニューでプロフィール各項目を表示
- Portfolio: 本をめくるようなUIで制作実績を表示
- Skills: 資格と使用ツールをコルクボード風に表示
- Contact: お問い合わせフォーム風の演出ページ
- Content Editor: 表示内容をJSONとして出力する編集ページ

プロフィールページ中央には表示名を配置でき、`content.json` の内容に応じてトップページ上の名前表示も差し替えられます。  
各公開ページのフッターから `content_editor.html` へ移動できます。

## ディレクトリ構成

```text
portfolio_original/
├─ index.html
├─ README.md
├─ yh_portfolio/
│  ├─ profile.html
│  ├─ portfolio.html
│  ├─ skills.html
│  ├─ contact.html
│  ├─ content_editor.html
│  ├─ css/
│  ├─ image/
│  └─ content.json
└─ page_requirements/
```

## コンテンツ編集

このサイトは `yh_portfolio/content.json` を読み込んで表示内容を切り替えます。  

編集手順:

1. [content_editor.html](/c:/academia/src/portfolio_original/yh_portfolio/content_editor.html) を開く
2. 表示名、プロフィール、ポートフォリオ、スキル情報を入力する
3. `JSON保存` で `content.json` を出力する
4. 出力した `content.json` を [yh_portfolio](/c:/academia/src/portfolio_original/yh_portfolio) 直下に配置する

反映対象:

- `profile.html`: トップページ中央の表示名とプロフィール内容
- `portfolio.html`: 作品一覧、注目作品、詳細説明、リンク
- `skills.html`: 資格一覧、ツール一覧

`content.json` が存在しない場合、各ページはデフォルト文言を表示します。

## エディタについて

`content_editor.html` では次の操作ができます。

- 表示名を含む各表示内容の入力
- JSONプレビューの確認
- `content.json` の読み込み
- `content.json` の保存
- 未保存のまま離脱しようとした場合の警告表示

## 閲覧方法

ビルドは不要で、静的ファイルとしてそのまま配置できます。  
ただし、各ページは `fetch` で `content.json` を読み込むため、内容反映を確認する際は `file://` 直開きではなくローカルサーバーまたはWebサーバー経由での確認を推奨します。
