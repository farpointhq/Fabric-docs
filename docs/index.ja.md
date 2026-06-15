# Fabric へようこそ

<div class="hero" markdown>

# ![Fabric ロゴ](assets/logo.png){ .no-lightbox width="42" style="vertical-align: middle; margin-right: 8px;" } Fabric

**より速く出荷。主導権を維持。決して手探りにならない。**

スピードと品質のどちらかを選ぶのはもう終わりです。Fabric は、あなたが運転席に座ったまま、AI コーディングのスーパーパワーを手に入れられます。

[ベータに参加する](https://farpointalpha.com/fabric){ .md-button .md-button--primary }
[何ができるか見る](#what-can-you-build){ .md-button }

</div>

---

## 開発者が Fabric を愛する理由

**AI コーディングツールは試したことがあるでしょう。** それらは速い——幻覚を起こすまでは。役に立つ——コンテキストを見落とすまでは。強力です——コードベースの主導権を失うまでは。

Fabric は違います。私たちは、内部で何が起きているのかわからない**不安**を抱えることなく、**AI のスピード**を求める開発者のために Fabric を作りました。

<div class="grid cards" markdown>

-   :material-eye:{ .lg .middle } **出力だけでなく、AI の思考を見る**

    ---

    AI があなたの問題を推論していく様子をリアルタイムで見られます。もうブラックボックスはありません——*なぜ* その提案をするのかを理解できるので、その判断を信頼する（あるいは修正する）ことができます。

    [:octicons-arrow-right-24: 仕組み](features/agentic-mode.md)

-   :material-swap-horizontal:{ .lg .middle } **仕事に合ったモデルを選ぶ**

    ---

    手早いタスクには高速なモデルを、複雑な推論には強力なモデルを使いましょう。会話の途中で切り替えられます。コストと品質のトレードオフはあなたが握っています。

    [:octicons-arrow-right-24: モデル選択](features/models.md)

-   :material-tab:{ .lg .middle } **すべてを同時に進める**

    ---

    バグ修正、機能開発、コードの探索を並行して進められます。各会話がそれぞれのコンテキストを保持するので、考えの流れを見失うことはありません。

    [:octicons-arrow-right-24: チャットワークスペース](guide/chat.md)

-   :material-shield-check:{ .lg .middle } **あなたのコード、あなたの主導権**

    ---

    すべてのファイル変更にはあなたの承認が必要です。AI の操作の完全な監査証跡。あなたの API キー、あなたのデータ、あなたのルール。

    [:octicons-arrow-right-24: セキュリティとプライバシー](getting-started/configuration.md)

</div>

## 何を作れるのか？

### 機能を数日ではなく数時間で出荷

Fabric は単にコードを書くだけではありません——あなたのコードベースを理解します。機能の追加を依頼すれば、何がどこに入るのか、どんなパターンを使っているのか、どう適切に統合すればよいのかを把握しています。

!!! example "実際の開発者のワークフロー"
    - 「既存のミドルウェアパターンに従って、私の Express API に JWT 認証を追加して」
    - 「ユーザー権限を扱っている箇所をすべて見つけて、管理者ロールのサポートを追加して」
    - 「このクラスを依存性注入を使うようにリファクタリングして——そしてテストも更新して」

### あらゆるタスクに最適なモデルを選ぶ

単純なリネームになぜ割増料金を払うのですか？複雑なアーキテクチャの判断になぜ高速なモデルを使うのですか？Fabric なら選べます。

| こんなときに… | 使うもの | 理由 |
|------------------|-----|-----|
| 手早い回答、単純な修正 | 高速なモデル | 即座の応答、最小限のコスト |
| 複雑な推論 | 強力なモデル | より優れたアーキテクチャ、より少ないミス |
| コードレビュー | あなたの選択 | 重要度に深さを合わせる |

!!! tip "品質を犠牲にせずコストを最適化"
    会話の途中でモデルを切り替えましょう。まず高速なモデルで探索を始め、深い推論が必要になったら強力なモデルに切り替えます。

### 退屈な部分は AI に任せる

退屈だけれど重要なタスクがあります。リファクタリング後のテスト更新、50 個のファイルにまたがる修正の適用、新しい API への移行などです。Fabric のエージェントモードは、あなたが主導権を握ったまま、複数ステップのタスクを処理します。

```
"Update all API endpoints to use the new error handling pattern,
and make sure the tests still pass."
```

何をしようとしているかを正確に確認し、各ステップを承認し、それが動く様子を見られます。驚きもなく、謎のコミットもなく、「今何をしたんだ？」もありません。

[:octicons-arrow-right-24: エージェントモードの動作を見る](features/agentic-mode.md)

### あなたのコードベースを完全に理解

Fabric はあなたのプロジェクトのメンタルモデルを構築します。次のことを把握しています。

- **どこに何があるか** - 認証コードについて尋ねれば、`src/auth/` を見ればよいと分かります
- **あなたのやり方** - あなたのパターン、規約、スタイルを学習します
- **何が何につながっているか** - ファイルやモジュール間の関係を理解します

!!! success "もうコードベースを説明する必要はありません"
    プロンプトのたびにコンテキストを貼り付ける必要はありません。Fabric は覚えています。

## コードを超えて

Fabric はソフトウェアを書くためだけのものではありません。高性能な AI をブラウザ、ファイルシステム、そして永続的なコンテキストと組み合わせているため、仕事を取り巻く思考やリサーチにも同じように役立ちます。

### 流れを止めずにリサーチ

組み込みブラウザにより、Fabric はあなたが見ているどんなページも読み取り、それを直接会話に取り込めます。長い RFC を要約したり、2 つのライブラリを並べて比較したり、Stack Overflow のスレッドから該当部分を取り出したりすることを——何もコピー＆ペーストすることなく——依頼できます。

!!! example "リサーチのワークフロー"
    - 「この Stripe のドキュメントページを読んで、一回払いに必要な最小限のセットアップを見せて」
    - 「この 2 つの npm パッケージを比較して、どちらがよりよくメンテナンスされているか教えて」
    - 「この移行ガイドの主要な破壊的変更を要約して」

### 実際にコードを反映する技術ドキュメントを書く

Fabric にモジュールを指定して、README、API リファレンス、あるいは変更履歴エントリを書くよう依頼しましょう。実際のコードを読むので、ものを作り上げることはありません——実際にそこにあるものを記述します。

!!! example "ライティングのワークフロー"
    - 「コードが実際に何をしているかに基づいて、このリポジトリの README を書いて」
    - 「前回のリリース以降のコミットから変更履歴エントリを生成して」
    - 「/deploy にあるスクリプトに基づいて、このサービスをデプロイするためのランブックを書いて」

### 一行も書く前に問題をじっくり考える

アーキテクチャの判断、プロダクトのトレードオフ、インシデントの事後分析の思考パートナーとして Fabric を使いましょう。関連するファイルを添付して、方向性を決める前に問題について本物の会話をしましょう。

!!! example "プランニングのワークフロー"
    - 「このアプリにリアルタイム通知を追加する必要があります。すでにあるものを踏まえて、WebSocket と SSE のトレードオフを順を追って説明して」
    - 「昨夜障害が発生しました。これがログです。事後分析を書くのを手伝って」
    - 「来週、新しいエンジニアをこのコードベースにオンボーディングしなければなりません。ウォークスルー文書を書くのを手伝って」

---

## 5 分で始める

<div class="grid cards" markdown>

-   :material-download:{ .lg .middle } **1. ダウンロード**

    ---

    macOS、Windows、Linux で利用可能。ワンクリックインストール、依存関係なし。

    [:octicons-arrow-right-24: Fabric をダウンロード](getting-started/installation.md)

-   :material-key:{ .lg .middle } **2. AI を接続**

    ---

    Anthropic、OpenAI、Google などの API キーを追加します。Google、Mistral、OpenRouter からは無料枠も利用できます。

    [:octicons-arrow-right-24: セットアップガイド](getting-started/configuration.md)

-   :material-rocket-launch:{ .lg .middle } **3. プロジェクトを開く**

    ---

    Fabric にあなたのコードベースを指定して、質問を始めましょう。進めるうちにあなたのコードを学習します。

    [:octicons-arrow-right-24: クイックスタート](getting-started/quickstart.md)

</div>

!!! tip "無料で始められる"
    まだ API アクセスにお金を払いたくありませんか？Google、Mistral、OpenRouter などの無料枠プロバイダーを使いましょう。

## 今日は何を作りますか？

=== "そのバグを直す"

    ```
    I'm getting "Cannot read property 'id' of undefined"
    in UserProfile.tsx. Find the bug and fix it.
    ```

=== "機能を追加する"

    ```
    Add a dark mode toggle to the settings page.
    Store the preference in localStorage and apply
    it app-wide.
    ```

=== "レガシーコードを理解する"

    ```
    Explain how the payment processing flow works.
    I need to add a new payment method and don't
    know where to start.
    ```

=== "出荷前にレビューする"

    ```
    Review this PR for security issues, edge cases
    I might have missed, and potential performance
    problems.
    ```

## コミュニティに参加する

<div class="grid cards" markdown>

-   :material-book-open-variant:{ .lg .middle } **もっと学ぶ**

    ---

    ガイドで Fabric の機能をさらに深く掘り下げましょう。

    [:octicons-arrow-right-24: ドキュメントを見る](guide/overview.md)

-   :material-github:{ .lg .middle } **参加する**

    ---

    フィードバックを共有し、機能をリクエストし、Fabric の未来を形作る手助けをしましょう。

    [:octicons-arrow-right-24: GitHub Discussions](https://github.com/farpointhq/Fabric/discussions)

-   :material-keyboard:{ .lg .middle } **パワーユーザーのヒント**

    ---

    キーボードショートカットをマスターして、ワークフローを駆け抜けましょう。

    [:octicons-arrow-right-24: ショートカットリファレンス](reference/shortcuts.md)

</div>

---

<div class="footer-cta" markdown>

**混乱なしでより速くコーディングする準備はできましたか？**

[Fabric を無料で入手](https://farpointalpha.com/fabric){ .md-button .md-button--primary }

</div>
