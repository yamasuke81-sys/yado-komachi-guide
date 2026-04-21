---
name: deploy
description: yado-komachi-guide を Firebase Hosting にデプロイする。commit & push も同時実行。
---

# /deploy

以下を順番に実行：

1. `git status` で変更状況を確認（未コミット変更があれば次ステップで commit）
2. 変更をステージして commit
   ```bash
   git add -A
   git commit -m "update: <変更内容の要約>"
   ```
3. Firebase Hosting にデプロイ
   ```bash
   firebase deploy --only hosting --project yado-komachi-guide
   ```
4. デプロイ成功後に GitHub に push
   ```bash
   git push origin main
   ```
5. ユーザーに公開URL `https://yado-komachi-guide.web.app` を伝える

## 注意
- コミットメッセージは変更内容を端的に（日本語OK）
- デプロイは毎回 commit & push もセット（やますけのルール）
- `.env` など秘密情報が差分に含まれていないか確認してから commit
