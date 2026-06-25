# 永続メモリ

<div class="video-wrapper" markdown>
<video controls width="100%" style="border-radius: 8px; margin: 1rem 0;">
  <source src="../../../../assets/videos/persistent-memory.mp4" type="video/mp4">
  お使いのブラウザは動画タグをサポートしていません。
</video>
</div>

## 永続メモリとは？

永続メモリは、Fabric の AI にプロジェクトに関する恒久的な一連の指示を与える方法です。AI が常に把握しておくべき事柄を、会話のたびに説明しなくても伝えられます。

これを実現するには、プロジェクトのルートに **`AGENTS.md`** ファイルを配置します。Fabric でチャットを開始するたびに、AI は他の何よりも先に、このファイルを自動的に読み込みます。これは常設のブリーフィングだと考えてください。プロジェクトの背景、コーディング標準、重要な決定事項、そして AI が従わなければならないあらゆるルールを記載します。

## AGENTS.md が重要な理由

永続メモリがないと、新しいチャットセッションは毎回まっさらな状態から始まります。「Jest ではなく Vitest を使う」「squash-merge は絶対にしない」「このサービスは `src/main/services/` にある」といった同じコンテキストを、何度も繰り返すことになります。

プロジェクトに `AGENTS.md` があれば、そのコンテキストは常に読み込まれます。あなたが一言も発する前に、AI はあなたの慣習を把握しています。

ここはまた、AI がすべてのタスクで尊重しなければならない **安全ルールやワークフロー要件** を記載するのに適した場所でもあります。たとえば「`npm test` を直接実行しない」や「常に PR を作成し、main には決してプッシュしない」といったものです。これらの指示は、AI が毎回のセッション開始時に目にするため、1 回限りのメッセージよりも大きな重みを持ちます。

## 使い方

**1. ファイルを作成する**

プロジェクトのルート（`package.json`、`README.md` などの隣）に `AGENTS.md` を追加します。

```
my-project/
├── AGENTS.md        ← create this
├── package.json
└── src/
```

**2. 指示を平易な言葉で書く**

特別な構文は不要です。マークダウンだけです。AI がコードを読んでも把握できない事柄に焦点を当てましょう。

```markdown
# My Project Agent Instructions

## Project Overview
This is a Next.js app with a Postgres database. The backend API lives in
`src/api/` and the frontend components in `src/components/`.

## Coding Standards
- Use TypeScript everywhere. No `any` types.
- All database queries go through the service layer in `src/services/`.
- Write tests with Vitest. Test files live next to the code they test.

## Critical Rules
- Never push directly to `main`. Always open a PR.
- Never run the full test suite locally — it takes 10+ minutes. Run
  `npm run test:changed` instead.

## How We Work
When fixing a bug, always add a regression test before changing the code.
When adding a feature, update the relevant section in `docs/` when done.
```

**3. Fabric が自動的に読み込む**

他には何もする必要はありません。次にこのプロジェクトを対象とした Fabric のチャットセッションを開くと、AI はすでにあなたの `AGENTS.md` を読み込んでおり、会話を通じてその指示に従います。

## AGENTS.md に書くべき内容

含めるとよいもの:

- **プロジェクト概要** — プロジェクトが何をするのか、主要なディレクトリ、どのように構成されているか
- **コーディング標準** — フォーマットルール、命名規則、使用するライブラリ
- **ワークフロールール** — PR の仕組み、ブランチの命名、レビュープロセス
- **安全ルール** — 決して実行してはならないコマンド、変更してはならないファイル、ユーザーの承認を必要とする事柄
- **テストの慣習** — どのテストランナーを使うか、テストはどこにあるか、何をテストするか
- **よくある落とし穴** — 以前にバグを引き起こしたことがある事柄、AI が注意すべき罠

コードを読めばすでに明らかな事柄を `AGENTS.md` に入れるのは避けましょう。AI が自力では本当に推測できないコンテキストのためにとっておきましょう。

## スコープ: プロジェクト vs ユーザー

`AGENTS.md` は複数持つことができます。

- **プロジェクトレベル**（`<project-root>/AGENTS.md`）— このプロジェクトにのみ適用されます。リポジトリにコミットすれば、チーム全体がその恩恵を受けられます。
- **ユーザーレベル**（`~/.agents/AGENTS.md` または `~/.claude/AGENTS.md`）— Fabric で開くすべてのプロジェクトに適用されます。「常に理由を説明する」や「簡潔な回答を好む」といった個人的な好みに適しています。

両方が存在する場合、Fabric はそれらを組み合わせ、プロジェクトレベルの指示がユーザーレベルの指示よりも優先されます。

## ヒント

- **率直に書く。** AI は指示を文字どおりに受け取ります。「関数コンポーネントを優先する」は「私たちは関数コンポーネントが好きな傾向がある」よりも明確です。
- **焦点を絞る。** 本当のリスクをカバーする 50 行の `AGENTS.md` は、AI が読み進めなければならない 500 行のものよりも効果的です。
- **状況が変わったら更新する。** 新しいサービスを追加したり、ディレクトリの名前を変更したり、慣習を変えたりした場合は、同時に `AGENTS.md` も更新しましょう。
- **安全ルールから始める。** 最も価値が高いのは、AI が取り返しのつかない操作をするのを防ぐエントリです。まずそれらを追加しましょう。
