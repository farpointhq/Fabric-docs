# 設定

左サイドバーの歯車アイコンをクリックして設定パネルを開きます。このパネルはタブで整理されており、モデル、権限、連携、ターミナルプロファイル、キーボードショートカット、プライバシー、ベンチマークを構成できます。

---

## General

![General Settings](../../../assets/screenshots/settings/1_general.png)

**Project Description** — アプリケーションの簡単な概要を入力して、AI による支援をパーソナライズし、プロンプトの関連性を高めます。

**Chat Management**

* **Enable automatic chat cleanup** — 設定した日数が経過した非アクティブなチャットを自動的に削除します。
* **Maximum chat age (days)** — 非アクティブなチャットを削除するまでに保持する日数（デフォルト: 30）。
* **Auto-collapse on final output** — モデルが応答の生成を完了したときに、思考ブロックとツール呼び出しを折りたたみます。

**Notifications**

* **Enable tab notification sound** — バックグラウンドのタブがユーザーの注意を必要とするときにサウンドを再生します。

---

## Models

![Models Settings](../../../assets/screenshots/settings/2_models.png)

**Helper Model** — リクエストを分析し、編集すべき関連ファイルを提案し、メインモデルが実行される前に簡潔なタブ名を提案する軽量な LLM です。Medium、Small、その他のティアから選択します。

**Subagent Model** — アシスタントがサブエージェントを生成するときに使用されるモデルです。オプションは次のとおりです。

* ヘルパーモデルと同じ
* メインモデルに判断させる
* Medium / Small（特定のティアに固定）

**LLM Providers** — 複数のプロバイダーの API キーを追加・管理します。任意のプロバイダーを展開すると、利用可能なモデルを表示し、API エンドポイント、temperature、最大トークン数を設定できます。

* **Fabric** — 組み込みのモデルプロバイダー
* **Anthropic** — Claude モデル（API キーが必要）
* **OpenAI** — GPT モデル（API キーが必要）
* 追加のプロバイダーは「Add Provider」ボタンで追加できます

---

## 権限

![Permissions Settings](../../../assets/screenshots/settings/3_permissions.png)

**Commands** — 明示的な承認なしに AI が実行できる安全なターミナルコマンドをホワイトリストに登録します。デフォルトで許可されているコマンドには、`ls`、`pwd`、`stat`、`file`、`du`、`df`、`cat`、`head`、`tail`、`grep` などが含まれます。「Add」ボタンを使用してカスタムコマンドを追加できます。

**Directories** — AI がファイル操作のためにアクセスできるディレクトリを構成します。これにより、ファイルの読み取り、書き込み、検索の範囲が承認された場所に制限されます。

---

## スキル

![Skills Settings](../../../assets/screenshots/settings/4_skills.png)

**Agent Skills** — タスクが一致したときにエージェントがオンデマンドで読み込む、再利用可能な指示パックです。スキルは次のいずれかになります。

* **Project-scoped** — プロジェクトに `SKILL.md` ファイルとして配置されます
* **User-scoped** — ユーザーアカウント全体にグローバルにインストールされます
* **From the Marketplace** — コミュニティが作成したスキルを閲覧してインストールします

各スキルは個別にオン/オフを切り替えられます。**Browse Marketplace** を使用して新しいスキルを見つけたり、**Install from source** を使用してカスタムスキルを追加したりできます。

---

## MCP

![MCP Settings](../../../assets/screenshots/settings/5_mcp.png)

**MCP Servers** — Model Context Protocol サーバーを追加・管理します。接続されたサーバーは、LLM が利用できるツール、リソース、プロンプトを公開します。各サーバーには、バージョン、ツールの数、接続状態が表示されます。既存のサーバーを管理するには **Disconnect**、**Edit**、**Remove** を使用し、新しいサーバーを接続するには **Add Server** を使用します。

**MCP Features**

* **Resource @ Mentions** — チャット入力欄で `@` を入力すると、MCP サーバーのリソースを閲覧してコンテキストとして添付できます。
* **Prompts as Slash Commands** — MCP サーバーのプロンプトは、コンポーザー内でスラッシュコマンド（例: `/server/prompt`）として表示されます。
* **Enable MCP Tools** — LLM が MCP サーバーのツールを呼び出せるようにします。個々のツールの権限はツールごとに管理できます。

**Tool Permissions** — どの MCP ツールを許可または拒否するかを制御します。チャットでツール権限のプロンプトに対して「Always Allow」をクリックすると、ルールが自動的に作成されます。

---

## Terminal

![Terminal Settings](../../../assets/screenshots/settings/6_terminal.png)

**Default Profile** — 「+」ボタンで新しいターミナルを作成するときに使用されるシェルプロファイルです。以下の任意のプロファイルで「Set Default」をクリックすると変更できます。

**Detected Profiles** — システム上で自動的に検出されたシェル:

* Windows PowerShell
* Command Prompt
* Git Bash
* Ubuntu (WSL)

**Custom Profiles** — ユーザー定義のシェルプロファイル。カスタムプロファイルの管理は近日公開予定です。

---

## Shortcuts

![Shortcuts Settings](../../../assets/screenshots/settings/7_shortcuts.png)

**Diff Viewer**

| アクション | ショートカット |
|--------|----------|
| 前の変更へスクロール | `W` |
| ハイライトされた変更を承認 | `A` |
| 次の変更へスクロール | `S` |
| ハイライトされた変更を破棄 | `D` |

**Chat View**

| アクション | ショートカット |
|--------|----------|
| プロンプトを入力 | `↵` |
| 音声を録音（プッシュ・トゥ・トーク） | `Right Alt` |
| 最新のエージェントをバックグラウンドへ送る | `Ctrl + B` |

**File Search**

| アクション | ショートカット |
|--------|----------|
| ファイルを検索 | `Ctrl + F` |
| 大文字小文字の区別を切り替え | `Ctrl + I` |
| 正規表現を切り替え | `Ctrl + R` |

**Window**

| アクション | ショートカット |
|--------|----------|
| ターミナルを折りたたむ | `Ctrl + \`` |

---

## Privacy

![Privacy Settings](../../../assets/screenshots/settings/8_privacy.png)

**Usage Analytics**

* **Allow usage analytics** — アプリの改善に役立てるために、操作データを共有します。プロンプトの内容やファイルが収集されることは一切ありません。

**Error Reporting Settings**

Fabric には、アプリケーションの改善に役立てるための自動エラー報告機能が含まれています。エラーが発生した場合、次のことができます。

* エラーの詳細を表示する
* エラーが発生したときに何をしていたかを説明する
* 開発チームにレポートを送信する
* アプリケーションを再起動する

エラーレポートは Fabric の GitHub リポジトリに issue として送信され、エラーメッセージ、スタックトレース、アプリのバージョン、プラットフォーム情報、および（提供された場合は）あなたの説明が含まれます。エラーレポートには、個人情報やファイルの内容は一切含まれません。

---

## Benchmark

![Benchmark Settings](../../../assets/screenshots/settings/9_benchmark.png)

**Run Benchmark** — 標準化されたコーディングタスクでモデルのパフォーマンスを評価します。ドロップダウンからベンチマークを選択し、**Run Benchmark** をクリックして評価を開始します。

**Benchmark Results** — 過去のベンチマーク実行を表示し、さまざまなモデルや構成間でスコアを比較します。
