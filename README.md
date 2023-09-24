# 職務経歴書
## 基本情報
|key|value|
|----|----|
|名前|岡本 侑樹|
|住所|東京都|
|年齢|24歳（1999.1.8生まれ）|
|ポジション|フロントエンドエンジニア、バックエンドエンジニア|
|エンジニア歴|2年（3年目）|
|Zenn|https://zenn.dev/felipe|
|Twitter|https://twitter.com/nuxt_hogehoge|
|Speaker Deck|https://speakerdeck.com/yuki_okamoto476|
|TOEIC|860点|
|出身大学・学部|同志社大学 法学部
|その他|[University of the People](https://www.uopeople.edu/)でComputer Science専攻（2023.11〜）

## 実務で経験のある言語・フレームワーク・ツール
### フロントエンド
React | TypeScript | Nuxt.js | JavaScript | Jest | React Testing Library | Playwright | Storybook | GraphQL | Apollo Client
### バックエンド
NestJS | TypeScript | PostgreSQL | Jest | GraphQL | Apollo Server | Github Actions
### インフラ
GCP（Cloud build | Cloud SQL | Cloud Storage | Workflows）| Terraform

### フロントエンド
フロントエンドの経験が1番長い。React、Vue（2系）ともに経験あり。基本設計→開発→テストまで問題なく対応可能。コードレビューやジュニアエンジニアのサポートも行っている。

### バックエンド
NestJSで開発経験あり。API設計や詳細設計→開発→テストまで問題なく対応可能。コードレビューも行っている。

### インフラ
GCPやTerraformで軽い修正なら対応可能。

## 業務経歴
### レバレジーズ株式会社（2022.12〜現在）

#### プロジェクト概要
HR系のSassの開発（マイクロサービス下）

#### 担当業務
サービス共通の基盤や管理画面の開発

#### 使用技術
React | TypeScript | NestJS

#### 発揮したバリュー1
##### 【課題・状況】
2000件のデータを取得するAPIの実行時間が25秒ほどかかっておりUXが低下している箇所があった

##### 【行動】
フロントエンドとバックエンドの両方から改善を試みた。
フロントエンドでは、APIを実行している関数をReactのhooksを用いて最適化、使用していない値をそもそもAPIで取得しないように修正することでオーバーフェッチングを解消。
バックエンドでは、APIで取得している値の中でいくつかn+1問題が起きていたので、dataloaderを用いてSQLのチューニングを実施。

##### 【結果】
フロントエンドの改善で約5秒、バックエンドの改善で約10秒ほど、計15秒ほど実行時間を短くすることができた。

#### 発揮したバリュー2
##### 【課題・状況】
①バックエンドで長年アップデートされていないことで、脆弱性の指摘やサポートがもうすぐ切れるライブラリが複数存在していた。<br>
②アップデートしようにも他のライブラリが依存、そのライブラリにも別のライブラリが依存しているなど、依存関係が複雑に絡みあっていて（ex. peer-dependenciesのエラーが10個ほど出る）容易にアップデートできない。<br>
③アップデートすると破壊的変更が起きる（ex. TypeORM 0.2→0.3、Apollo Server v2→v4）。

##### 【行動】
①を受けてライブラリのバージョンアップに着手。<br>
②に対しては、ライブラリをアップデートしたときに吐き出されるエラーから、どのライブラリがどのライブラリに依存しているか、どのバージョンなら解決できるかを紐解いて整理。<br>
そして、そのライブラリのGitHubを確認し、適切なバージョンをインストール。<br>
アップデートする際に対応していないライブラリが出てきた場合は、そのライブラリの代わりに別のライブラリをインストール。<br>
これを繰り返して全ての依存関係のエラーを解消。<br>
また、更新が止まっていそうなライブラリが存在した場合は、将来的なリスクも鑑みライブラリを使わない独自実装に切り替えた。<br>
③については、ライブラリのGitHubや公式ドキュメントのマイグレーションガイドから変更箇所を読み解き、既存のコードに合う形にコードを修正。
また、アップデートにより変更があった箇所や修正していく中で詰まった箇所は、解決法とともにドキュメントにまとめ他チームに展開することでナレッジの共有をおこなった。

##### 【結果】
1ヶ月ほどかけてライブラリをバージョンアップし、脆弱性を大きく減らすことができた。

#### 発揮したバリュー3
##### 【課題・状況】
ジュニアレベルのフロントエンドエンジニアが新規で入社して教育が必要だった

##### 【行動】
そのメンバーのサポートやアウトプットを管理した。<br>
具体的には、<br>
- API連携やコンポーネントの設計など少し難しそうなタスクの場合は、1日の終わりに声をかけて進捗の確認。詰まっていそうなところがあれば実装方針・実装方法の相談に乗る。
- 期限を考慮して時間がかかりそうであればタスクの巻き取り。
- そのメンバーのコードレビューは主に自分が担当。コードの品質の担保やそのメンバーの技術力向上のためにより良い実装方法や知見の提供を行なった。

##### 【結果】
フロントエンドに関してはある程度自走できるくらいにまで育てることができた。

#### 発揮したバリュー4
##### 【課題・状況】
フロントエンドのリポジトリにおいて以下の状況が発生していた。<br>
①脆弱性の指摘が108個あり長年放置されていた。<br>
②create-react-appを用いておりアプリケーションを起動するのに45秒ほどかかっていた。

##### 【行動】
以下の打ち手を講じた<br>
①クリティカルな脆弱性は指摘されていなかったがいつかは解消しなければならないということで、脆弱性が指摘されているライブラリをアップデート。更新が止まっていそうなライブラリについては別のライブラリに移行したり、ライブラリを使わない独自実装に切り替えた。<br>
②不便というほどではないがもっと高速に起動できれば開発効率が間違いなく上がると考え、ビルドツールをcreate-react-appからviteに移行。

##### 【結果】
①108個指摘されていた脆弱性を0にできた。<br>
②アプリケーションの起動が45秒から10秒ほどに短縮でき自分だけでなくチームメンバーの開発効率も上がった。

### 株式会社メンバーズ（2021.4〜2022.11）
#### プロジェクト概要
シニア向けサービスの開発

#### 担当業務
シニア向けのWebサイト、Webviewページ制作

#### 使用技術
Nuxt.js

#### 発揮したバリュー1
##### 【課題・状況】
APIから取得した情報を表示する機能を実装する際に、以下の課題があった。
- リリースに間に合わせるために、実装方針をある程度固めて実装していたが、途中でAPIが改修され、仕様が大きく変更された。
- 例外パターンの仕様が存在しない。そもそも考慮されていない。

##### 【行動】
このような課題がある中で、まずはリリースに間に合わせることを優先するために、最低限必要な例外パターン時の仕様についてディレクターとデザイナーに提案。旧仕様のロジックを流用しながら、最低限必要な機能を実装してなんとかリリースに間に合わせることができた。<br>
そして、リリース後に以下の改善をおこなった。
- エラーパターンを含め全ての例外パターンを実装することで、エラー時のユーザーのとるべき【行動】をわかりやすくした。
- 一度APIの通信に成功しデータを取得できた場合は、そのデータをキャッシュとして保持し、2回目以降そのAPIにアクセスしないように実装を変更することで、APIの負荷を軽減。これにより、ユーザーの通信に伴うストレスも軽減。
- 子コンポーネント側にAPI取得のロジックを書いていたが、親コンポーネント側にロジックをロジックを移行することで、より可読性の高いコードにした。

#### 発揮したバリュー2
##### 【課題・状況】
チームで毎日行うMTGのために会議室を予約する必要があったが、それをバックオフィスの人に依頼して毎日手動でOutlookから予約してもらっていた。

#### 【行動】
この作業を自動化するために、Power Automateというローコードツールを用いて、毎日特定の時間になったら自動でOutlookの予約のメールをくるようにした。

#### 【結果】
毎日手動でおこなっていた1分ほどの時間を削減することができた。