# Hugo 環境構築・開発・デプロイ手順

## 1. Hugo の環境構築

- [公式ドキュメントの手順](https://gohugo.io/getting-started/installing/)に従い，Hugo をインストール．

## 2. 開発

以下のコマンドを実行後，`content/posts`の内容を変更・保存

```bash
hugo server
```

- 上記コマンドでローカル開発サーバーが起動．
- ホットリロード対応のため，変更は自動で反映される．
- 注：[Windows の場合は PowerShell を用いること．](https://gohugo.io/getting-started/quick-start/#commands)

## 3. CI/CD パイプライン（GitHub Pages へのデプロイ）

- GitHub Actions を利用し，このリポジトリの`main`ブランチへのプッシュが行われた場合にサイトを自動ビルド・デプロイしている．

## 4. 参考リンク

- [Hugo 公式ドキュメント](https://gohugo.io/)
  - [GitHub Pages へのデプロイ方法](https://gohugo.io/host-and-deploy/host-on-github-pages/)
- [PaperMod Wiki](https://github.com/adityatelange/hugo-PaperMod/wiki)
