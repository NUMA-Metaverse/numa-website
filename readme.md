# 構成

- Repo: GitHub
- Generate: Hugo+PaperMod(+Markdown contents)
- Host: GitHub Pages

# 保守・運用

- https://github.com/NUMA-Metaverse/numa-website の`main`ブランチの内容がすなわちサイトの内容である
  - 従ってここのコードを更新すればそれがサイトに反映される
    - 「HTML をビルドして...」などという必要はなく，ソースファイルだけでよい
    - 具体例：記事執筆においては`content/posts/blogs/(post-title)/index.md`を作成すればそれだけでよい
      - この場合はhttps://numa-meta.com/posts/blogs/(post-title)/ に記事が作成されるかたちになる

# 具体的な作業手順

## 1. Hugo の環境構築

[公式ドキュメント](https://gohugo.io/getting-started/installing/)に従い，Hugo をインストールする．

## 2. リポジトリのクローン

```bash
  git clone https://github.com/NUMA-Metaverse/numa-website.git
  cd numa-website
  git submodule update --init --recursive
```

## 3. 作業ブランチの作成

まず，`main`ブランチから作業用の新しいブランチを作成し，それに切り替える．これ以降の編集やコミットは，全てこのブランチ上で行う．

```bash
  git checkout -b (branch-name) main
```

## 4. 記事の作成・編集とプレビュー

注：[Windows の場合は PowerShell を用いること．](https://gohugo.io/getting-started/quick-start/#commands)

1. 以下のコマンドで記事の作成をする．

```bash
  hugo new posts/blogs/(post-title)/index.md
```

2.  以下のコマンドでローカル開発サーバーを起動する．

```bash
  hugo server
```

3.  ブラウザで `http://localhost:1313/posts/blogs/(post-title)/` にアクセスし，表示を確認する．
4.  ファイルを編集し保存すると，変更はプレビューに自動で反映される（ホットリロード）．
5.  作業がキリの良いところまで進んだら，変更内容をコミットする．

```bash
  git commit -a -m "commit-message"
```

## 5. GitHub への反映

**原則として，プルリクエストを送る形式で進めること．**
作業内容に自信がない場合や，第三者のレビューが必要な場合は特にこの手順を遵守する．

### ブランチを利用する場合（推奨）

1.  作業ブランチをリモートにプッシュする．

```bash
  git push -u origin (branch-name)
```

2.  GitHub 上で`main`ブランチへのプルリクエストを作成する．

```bash
  gh pr create --base main --head (branch-name) --title "pr-title" --body "description"
```

### `main`ブランチに直接プッシュする場合

略

# QA

- なぜソースファイルを更新するだけでよいのか？
  - ソースの更新を検知 → ビルド → レジストリに置き稼働，まですべて自動化している
  - DevOps とか CI/CD pipeline とかで調べれば幸せになれるかもしれない
- なぜ GitHub なのか？
  - 無料，Git によるコード管理ができる，開発から運用まで行える，など
  - それ以上気にするならこの QA 見るまでもないはず
- なぜ GitHub Pages なのか？
  - 無料，GitHub のなかで収まり外部サービスの利用をしなくて済む
- なぜ public repo なのか？
- GitHub Pages にて無料で host するには public である必要がある
- 既存の generator+既存の theme による構成であり，live site から直接得られる情報と実質的に変わらない
