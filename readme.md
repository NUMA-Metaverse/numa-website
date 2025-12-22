# NUMA Website

NUMA (Nippon Universities Metaverse Alliance) 公式ウェブサイト(numa-meta.com)のソースコードリポジトリ．

## システム構成

- **Repository**: GitHub
- **Generator**: Hugo + PaperMod (Theme)
- **Content**: Markdown
- **Hosting**: GitHub Pages

`main` ブランチの内容を本番環境([numa-meta.com](https://numa-meta.com/))と同期しているため，**ソースコード(Markdown ファイル等)を更新すれば，ビルド・デプロイは自動で行われる**．

## 命名規則

この README 全体を通して，`<angle-bracketed>`のように`<`と`>`で囲まれたものはプレースホルダーを示し，ここに実際の値や変数名などを規定された形式に従って入れることを意味する．`<説明>`のように日本語で書かれたものについては，形式を特段指定しないものとする．

### 識別子の定義

この README 全体を通して，以下の識別子を定義する：

| 識別子名                         | 意味・説明                                                                                                                                                                                                                                  | 備考・例                                                                                                               |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `<prefix>`                       | 作業の種類．<br>`blog`: 記事執筆・修正．<br>`feat`: サイト機能追加・レイアウト変更<br>`fix`: バグ修正(表示崩れ・リンク切れなど)．**※記事に関しては，たとえ修正であっても`blog`を用いること．**<br>`chore`: 依存関係更新・ドキュメント整備等 | 例: `blog`                                                                                                             |
| `<circle-id>`                    | 作業者の所属．サークル所属なら **[`name-id.md`](./name-id.md)に記載された** ID，個人勢または不明時は `numa`．                                                                                                                               | 例: `numa`                                                                                                             |
| `<user-name>`                    | 作業者の GitHub ユーザー名．<br>なお，一般に GitHub リポジトリ URL は次の形式をしている: `https://github.com/<user-name>/<repo-name>`                                                                                                       | 例: `username123`                                                                                                      |
| `<additional-path>` _(optional)_ | 記事が配置されるサブディレクトリやカテゴリ．<br>特定シリーズ・年度・テーマごとに必要な場合のみ指定．                                                                                                                                        | 例: `review-kikaku`, `events/winter-fes`                                                                               |
| `<post-ref>`                     | **記事に表示されるタイトルとは別途定める，** 投稿の内容の簡潔な説明(英数字・ハイフン区切り・1 行)．                                                                                                                                         | 例: `ux-design-trends`                                                                                                 |
| `<branch-ref>`                   | ブランチの内容の簡潔な説明(英数字・ハイフン区切り・1 行)．                                                                                                                                                                                  | 例: `add-ux-design-trends`                                                                                             |
| `<branch-name>`                  | **ブランチ名の命名規則**:<br>`<prefix>/<circle-id>/<user-name>[/<additional-path>]/<branch-ref>`<br><br>※ `[/<additional-path>]` は任意．特別な指示・構成時のみ追加．                                                                       | 例 1: `blog/numa/username123/add-ux-design-trends`<br>例 2: `blog/numa/username123/review-kikaku/add-ux-design-trends` |

## 具体的な作業手順(一般メンバー向け)

### 0. コーディング全般の環境構築

- PC
  - Windows, Linux, Mac その他 Unix，のいずれでも可能．
    - ただし，[Windows の場合は PowerShell を用いること．](https://gohugo.io/getting-started/quick-start/#commands)
- エディタ
  - とりあえず[VSCode](https://code.visualstudio.com/) を使っていれば充分．
- [Git](https://git-scm.com/)
  - GitHub で使うツール，くらいの認識で OK．
  - インストールは AI に訊けばなんとかなる．

### 1. Hugo の環境構築

[公式ドキュメント](https://gohugo.io/getting-started/installing/)に従い，Hugo をインストールする．

### 2. リポジトリのクローン

```sh
  git clone https://github.com/NUMA-Metaverse/numa-website.git
  cd numa-website
  git submodule update --init --recursive
```

### 3. 作業ブランチの作成

まず，`main`ブランチから作業用の新しいブランチを作成し，それに切り替える．これ以降の編集やコミットは，全てこのブランチ上で行う．

```sh
  git checkout -b <branch-name> main
```

なお，ブランチ名(`<branch-name>`)は「[識別子の定義](#識別子の定義)」に従って命名すること．

#### 3.1. 具体的な作成例

- **サークル「Hoge XR」所属の「Hira Buin」が「Hoge XR の紹介記事」を新規作成する**
  - `<prefix>`: `blog`
  - `<circle-id>`: `hoge-xr`
  - `<user-name>`: `hira-buin`
  - `<branch-ref>`: `add-hoge-xr-intro`

```sh
  git checkout -b blog/hoge-xr/hira-buin/add-hoge-xr-intro
```

- **個人勢の「Ko Jin」が「レビュー企画」の一環として「Foo Bar のレビュー記事」を新規作成する**
  - `<prefix>`: `blog`
  - `<circle-id>`: `numa`
  - `<user-name>`: `ko-jin`
  - `<additional-path>`: `review-kikaku`
  - `<branch-ref>`: `add-foo-bar-review`

```sh
  git checkout -b blog/numa/ko-jin/review-kikaku/add-foo-bar-review
```

### 4. 記事の作成・編集とプレビュー

#### 4.1. 記事の作成

以下のコマンドで記事の作成をする．

```sh
  hugo new posts/blogs[/<additional-path>]/<post-ref>/index.md
```

この場合，記事のファイルは`content/posts/blogs[/<additional-path>]/<post-ref>/index.md`に作成される．

##### 4.1.1. 具体的な作成例

- **Hoge XR の紹介記事」を新規作成する**
  - `<post-ref>`: `hoge-xr-intro`

```sh
  hugo new posts/blogs/hoge-xr-intro/index.md
```

- **「レビュー企画」の一環として「Foo Bar のレビュー記事」を新規作成する**
  - `<additional-path>`: `review-kikaku`
  - `<post-ref>`: `foo-bar-review`

```sh
  hugo new posts/blogs/review-kikaku/foo-bar-review/index.md
```

#### 4.2. ローカル開発サーバーを起動する．

以下のコマンドでローカル開発サーバーを起動する．

```sh
  hugo server
```

#### 4.3. プレビュー

ブラウザで `http://localhost:1313/posts/blogs[/<additional-path>]/<post-ref>/` にアクセスし，表示を確認する．

#### 4.4. 執筆

ファイルを編集し保存すると，変更はプレビューに自動で反映される(ホットリロード)．編集時は以下のを遵守すること．

- **Front Matter の設定:**
  - **tags**: `<circle-id>`のほか，`活動記録`, `イベント開催`, `お知らせ` 等から適切に選択する．
  - **categories**: ブログ記事の場合は `["Blog"]` を指定する．
- **アセット管理(画像)のルール:**
  - **配置**: 原則として，記事の `index.md` と同階層(Page Bundle)に配置する．
  - **最適化**: 掲載画像は必ずリサイズおよび圧縮を行う．[Squoosh](https://squoosh.app/) 等を用い，1 枚あたり数百 kB 程度を目安とする．
- **代替テキスト**: Markdown の画像記法における代替テキスト(alt 属性)を適切に記述する．

#### 4.5. コミット

作業がキリの良いところまで進んだら，変更内容をコミットする．

```sh
  git commit -a -m "<prefix>: <説明>"
```

### 5. GitHub への反映

**原則として，PR(プルリクエスト)を送る形式で進めること．**

#### 5.1. PR を送る場合

##### 5.1.1. 作業ブランチをプッシュ

以下のコマンドで，作業ブランチをリモートにプッシュする．

```sh
  git push -u origin <branch-name>
```

##### 5.1.2. PR を作成

GitHub 上で`main`ブランチへの PR を作成する．作成前に以下の**チェック項目**を確認すること．

- [ ] `hugo server` でローカルビルドし，表示崩れがないか確認した
- [ ] 画像の圧縮・適正配置を行った
- [ ] メタデータ(tags/categories)は適切か
- [ ] ファイルパス・コミット・PR の命名規則は適切か
- [ ] 記事投稿日時は適切か(PR に数日かかったときなど)

**タイトル命名規則**: `<prefix>: <説明>`
(例: `blog: add hoge-xr-intro`)

コマンドで行う場合は以下：

```sh
  gh pr create --base main --head <branch-name> --title "<prefix>: <説明>" --body "<PRの詳細な説明>"
```

#### 5.2. `main`ブランチに直接プッシュする場合

略

## QA

- なぜソースファイルを更新するだけでよいのか？
  - ソースの更新を検知 → ビルド → デプロイ，まですべて自動化している．
  - DevOps とか CI/CD pipeline とかで調べれば幸せになれるかもしれない．
- なぜ GitHub なのか？
  - 無料，Git によるコード管理ができる，開発から運用まで行える，など．
  - ~~GitLab とか言われても...~~
- なぜ GitHub Pages なのか？
  - 無料，GitHub のなかで収まり外部サービスの利用をしなくて済む．
- なぜ public repo なのか？
  - GitHub Pages にて無料で host するには public である必要がある．
  - 既存の generator+既存の theme による構成であり，live site から直接得られる情報と実質的に変わらない．

## 具体的な作業手順(管理者向け)

以下，このサイト全体の設定などを弄ることに関して記す．紛らわしいので collapse しておく．

<details>
<summary>Click to view 👀</summary>

### サークルのリストの管理

各サークルについて，[`data/circles/list.yaml`](./data/circles/list.yaml) がメタデータの，[`assets/images/circles`](./assets/images/circles)配下がアイコン画像のマスタである．~~(解説完了)~~

従い，加入/脱退サークルが生じた場合などには，これらを更新すればよい．

以下，`<circle-id>`は上記で扱ったものと一致する．

#### [`data/circles/list.yaml`](./data/circles/list.yaml): メタデータ

加入に際しては，以下のような内容を追加すればよい．`id`, `name`以外に欠けているフィールドがあっても差し支えない．脱退に際してはまるごと削除．

```yaml
- id: "<circle-id>"
  name: "Hoge XR"
  university: "ふが大学"
  links:
    - label: "公式Xアカウント"
      url: "https://twitter.com/hoge-xr-dayo"
```

※ID は他の団体と重複しないようにすること．~~*IDentity*がなあああ～あい，になっちゃうからね．~~

なお，この変更に伴い，[`name-id.md`](./name-id.md)は自動で更新されるようになっている．([`.github/workflows/generate-name-id-table.yaml`](./.github/workflows/generate-name-id-table.yaml) による．)

また，[加盟団体一覧のページ](https://numa-meta.com/members/) のソースは [`content/posts/members/index.md`](./content/posts/members/index.md)であるが，そのコンテンツは自動で生成されるため，編集の必要はない．([`layouts/shortcodes/circleList.html`](./layouts/shortcodes/circleList.html)による．)

#### [`assets/images/circles`](./assets/images/circles): アイコン画像

`assets/images/circles/<circle-id>.<extention>`を追加すること．`<extention>`としては`png`, `jpg`, `jpeg`, `svg`をサポートしている．

</details>
