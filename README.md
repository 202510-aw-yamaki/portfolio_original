# Portfolio Site

静的HTML/CSS/JavaScriptで構成されたポートフォリオサイトです。  
`index.html` にアクセスすると `yh_portfolio/profile.html` へリダイレクトされ、以下の4ページで構成されています。

- Profile: ドーナツ型メニューでプロフィール情報を表示
- Portfolio: 本をめくるようなUIで制作実績を表示
- Skills: 資格・使用ツールをコルクボード風に表示
- Contact: お問い合わせフォーム風の演出ページ

## ディレクトリ構成

```text
portfolio_original/
├─ index.html
├─ yh_portfolio/
│  ├─ profile.html
│  ├─ portfolio.html
│  ├─ skills.html
│  ├─ contact.html
│  ├─ content_editor.html
│  ├─ css/
│  └─ image/
└─ page_requirements/
```

## コンテンツ差し替え方法

各ページの表示内容は `yh_portfolio/content.json` を読み込んで反映する仕組みです。  
このリポジトリには個人情報を含む `content.json` の内容は含めない想定です。

1. [yh_portfolio/content_editor.html](/c:/academia/src/portfolio_original/yh_portfolio/content_editor.html) を開く
2. プロフィール、ポートフォリオ、スキル情報を入力する
3. `JSON保存` ボタンで `content.json` を出力する
4. 出力した `content.json` を [yh_portfolio](/c:/academia/src/portfolio_original/yh_portfolio) 直下に配置する

これで `profile.html` `portfolio.html` `skills.html` に入力内容が反映されます。  
`content.json` が存在しない場合は、各ページのデフォルト文言が表示されます。

## 閲覧方法

ビルドは不要です。静的サイトとしてそのまま配置できます。  
ただし各ページは `fetch` で `content.json` を読み込むため、内容反映を確認する際はローカルサーバー経由で開く運用を推奨します。
