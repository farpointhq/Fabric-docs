# クイックスタート

## インストール

**ダウンロード → インストール → コーディング開始。これだけです。**

## Fabric を入手する

<div class="grid cards" markdown>

-   :material-apple:{ .lg .middle } **macOS**

    ---

    Apple Silicon（M1/M2/M3/M4）と Intel Mac に対応。macOS 12 以降。

    [Mac 用をダウンロード](https://farpointalpha.com/fabric){ .md-button .md-button--primary }

-   :material-microsoft-windows:{ .lg .middle } **Windows**

    ---

    Windows 10 以降（64 ビット）。

    [Windows 用をダウンロード](https://farpointalpha.com/fabric){ .md-button .md-button--primary }

-   :material-linux:{ .lg .middle } **Linux**

    ---

    AppImage または .deb パッケージ。Ubuntu 20.04 以降または同等の環境。

    [Linux 用をダウンロード](https://farpointalpha.com/fabric){ .md-button .md-button--primary }

</div>

!!! success "無料で始められる"
    Google、Mistral、OpenRouter などの無料プランのプロバイダーを利用すれば、API アクセスに料金を支払うことなく始められます。

## 必要なもの

- **インターネット接続**（AI モデルはクラウドで実行されます）
- **4GB の RAM**（最小）、大規模プロジェクトには 8GB 以上
- 任意のプロバイダーの **API キー**（Google、Mistral、OpenRouter で無料プランを利用可能）

---

## インストール手順

=== "macOS"

    1. ダウンロードした `.dmg` ファイルを開く
    2. **Fabric** を **アプリケーション** フォルダにドラッグする
    3. アプリケーションから Fabric を開く

    !!! tip "初回起動"
        macOS にセキュリティ警告が表示される場合があります。アプリを右クリック → **開く** → もう一度 **開く** を選択してください。

=== "Windows"

    1. `Fabric-Setup.exe` を実行する
    2. インストーラーの指示に従う
    3. スタートメニューから起動する

    !!! tip "Windows セキュリティ"
        SmartScreen が表示された場合は、**詳細情報** → **実行** をクリックしてください。

=== "Linux"

    **AppImage（最も簡単）:**
    ```bash
    chmod +x Fabric.AppImage
    ./Fabric.AppImage
    ```

    **Debian/Ubuntu:**
    ```bash
    sudo dpkg -i Fabric.deb
    ```

---

## 初回起動

Fabric を開くと、すぐにチャットインターフェースが表示されます。セットアップウィザードも設定フォームもありません。

### 今すぐ試す（API キー不要）

Fabric には始めるための無料トークンが含まれています。プロジェクトフォルダを開いて質問してみましょう:

```
What does this codebase do?
```

### 自分の API キーを追加する（任意）

使用するモデルをもっと細かく制御したいですか? 設定で自分のキーを追加できます:

| プロバイダー | キーの入手先 |
|----------|------------------|
| **Anthropic** | [console.anthropic.com](https://console.anthropic.com/) |
| **OpenAI** | [platform.openai.com](https://platform.openai.com/api-keys) |
| **Google** | [aistudio.google.com](https://aistudio.google.com/app/apikey) |

!!! tip "無料プランの選択肢"
    - **Google** — Gemini モデル向けの充実した無料プラン
    - **Mistral** — 始めるための無料 API アクセス
    - **OpenRouter** — DeepSeek R1 などの無料モデル

---

## アップデート

Fabric は自動的に更新されます。新しいバージョンが利用可能になると通知が表示されます。


## 起動して始める

### ステップ 1: Fabric を開く

他のアプリと同じように起動するだけです。ターミナルコマンドも設定ファイルも不要です。

### ステップ 2: コードを指定する

**ファイル** → **プロジェクトを開く** をクリックし、プロジェクトフォルダを選択します。Fabric はすぐにあなたのコードベースの学習を開始します。

!!! success "ここで魔法が起こります"
    Fabric があなたのプロジェクトを理解すると、汎用的な AI ではなく *あなた専用の* AI になります:

    - 認証コードがどこにあるかを把握します
    - あなたの命名規則に従います
    - 必要になりそうなファイルを提案します
    - コンポーネント同士がどう連携しているかを理解します

### ステップ 3: モデルを選ぶ

モデルのドロップダウンをクリックし、行う作業に応じて選択します:

| こんな作業? | これを使う |
|-------------|----------|
| 簡単な質問、単純な修正 | 高速モデル（Haiku、GPT Mini） |
| 複雑な問題、コードレビュー | 高性能モデル（Sonnet、GPT-4） |
| よくわからない? | まず高速モデルで始め、必要に応じて切り替える |

!!! tip "いつでも切り替え可能"
    まず高速モデルで始めましょう。回答が十分に深くない場合は、より高性能なモデルに切り替えてください。Fabric はすべてのコンテキストを保持します。

### ステップ 4: 何でも質問する

質問を入力して Enter キーを押すだけです。特別な構文も魔法のコマンドもありません。

---

## 今すぐ試してみよう

### 「なぜこれが動かないの?」

壊れたコードを貼り付けて、Fabric が解決するのを見てみましょう:

```
This keeps crashing and I don't know why:

TypeError: Cannot read properties of undefined (reading 'map')
  at UserList (UserList.tsx:15:23)
```

**Fabric は:** バグを見つけ、なぜ起こるのかを説明し、複数の修正方法を提示します。

### 「これを作って」

必要なものを平易な言葉で説明します:

```
localStorage に状態を保存する React フックを作成してください。
JSON を自動的に処理し、TypeScript で動作するようにしてください。
```

**Fabric は:** あなたのプロジェクトのパターンに合った、本番環境で使えるコードを書きます。

### 「このコードは大丈夫?」

リリースする前にセカンドオピニオンを得ましょう:

```
セキュリティ上の問題や見落としがないかレビューしてください:

app.post('/api/users', async (req, res) => {
  const { email, password } = req.body;
  const user = await db.users.create({ email, password });
  res.json(user);
});
```

**Fabric は:** 入力検証の欠如、暗号化されていないパスワード、エラー処理の不足を検出します。
