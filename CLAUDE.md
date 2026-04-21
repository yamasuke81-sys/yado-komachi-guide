# yado-komachi-guide — YADO KOMACHI Hiroshima 宿泊者向け案内ページ

## 概要
広島・エクセリア小町 704号室の宿泊者向けチェックイン/アウト案内ページ。
旅館業事前説明資料（Excel）から web 化したもの。日本語/英語切替対応。

## 技術スタック
- Firebase Hosting（静的配信）
- バニラ HTML/CSS/JS（フレームワーク不使用）
- Bootstrap Icons（CDN）、Google Fonts（Noto Sans JP / Playfair Display）

## ファイル構成
```
yado-komachi-guide/
├── public/
│   ├── index.html     # 本体（1ファイル完結、CSS/JS 内包）
│   └── img/           # 写真・マップ画像（Excel から抽出）
├── firebase.json      # Hosting 設定
├── .firebaserc        # Firebase プロジェクト: yado-komachi-guide
└── .claude/skills/deploy/SKILL.md  # デプロイ用スキル
```

## デプロイ
```bash
firebase deploy --only hosting
```
または `/deploy` スキルを実行。

公開URL: https://yado-komachi-guide.web.app

## コンテンツ更新時の注意
- 写真は `public/img/` に配置、ファイル名は `image{N}.{ext}` 形式（Excel 抽出時の元名称）
- Wi-Fi 値・電話番号など運用値は HTML 内に直書き。変更時は `index.html` を直接編集
- チェックイン/アウト時間の変更は「ご注意事項」カード＋セクション見出しの time-badge の両方を同期
