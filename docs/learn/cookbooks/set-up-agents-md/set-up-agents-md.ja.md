# プロジェクト用に AGENTS.md を設定する

**所要時間:** 15分  
**難易度:** 初級  
**作成するもの:** Fabric にプロジェクトの慣習、スタック、ルールを自動的に、毎セッション認識させる永続メモリファイル。

---

## AGENTS.md とは？

`AGENTS.md` は、プロジェクトのルートに配置するプレーンな Markdown ファイルです。Fabric はすべてのチャットセッションの開始時にこれを読み込み、その内容を永続的なコンテキストとして使用します。そこに書いた内容はすべて自動的に AI に提供されます — コピー＆ペーストも、説明のし直しも不要です。

`AGENTS.md` がないと、Fabric は各セッションをゼロから始め、プロジェクトを一から学び直さなければなりません。あれば、AI はあなたのスタック、慣習、テストルール、その他書き留めたあらゆることをすでに知っています。

---

## ステップ1: ファイルを作成する

プロジェクトのルートディレクトリに、`AGENTS.md` というファイルを作成します。

```bash
touch AGENTS.md
```

または、ルートフォルダを右クリックして Fabric のファイルブラウザから直接作成することもできます。

---

## ステップ2: プロジェクト概要を追加する

まず、プロジェクトが何であるかの短い説明から始めます。2〜3文で十分です。

```markdown
# AGENTS.md

## Project Overview
This is a Next.js 14 web app for managing freelance invoices.
It uses Supabase for the database and Auth.js for authentication.
The main user flow is: create client → create project → generate invoice → send to client.
```

これにより、AI はコードを読む前に状況を把握できます。

---

## ステップ3: スタックを記述する

主要な技術を、関連する場合はバージョンとともにリストアップします。

```markdown
## Tech Stack
- **Framework**: Next.js 14 (App Router)
- **Language**: TypeScript (strict mode)
- **Database**: Supabase (Postgres)
- **Auth**: Auth.js v5
- **Styling**: Tailwind CSS
- **Testing**: Vitest + React Testing Library
- **Deployment**: Vercel
```

---

## ステップ4: 慣習を記録する

ここが `AGENTS.md` の真価が発揮される部分です。頭の中にはあるがコードには現れない慣習を書き留めましょう。

```markdown
## Code Conventions
- Components go in `src/components/`, one file per component
- Server actions go in `src/actions/`, named `verbNoun.ts` (e.g. `createInvoice.ts`)
- Use named exports, never default exports
- All database queries go through `src/lib/db.ts` — never query Supabase directly in components
- Error handling: use the `Result<T>` type from `src/lib/result.ts`, never throw in server actions
- CSS: Tailwind utility classes only, no custom CSS files
```

---

## ステップ5: テストルールを追加する

AI に実行してほしくないコマンドを実行させないようにするか、テストの実行方法を正確に伝えます。

```markdown
## Testing
- Run tests with: `npx vitest run`
- Do NOT use `npm test` — it runs a different script
- Test files live next to the source file: `component.tsx` → `component.test.tsx`
- Mock Supabase with the helpers in `src/test/mocks/supabase.ts`
- Do not write snapshot tests
```

---

## ステップ6: 安全ルールを追加する

AI が確認なしに決して触れてはならないファイルや操作がある場合は、それを明示的に記述します。

```markdown
## Safety Rules
- Never modify `supabase/migrations/` directly — always create a new migration file
- Never commit `.env.local` or any file containing secrets
- Ask before changing `src/lib/db.ts` — it's used everywhere
- The `main` branch is protected — always work on a feature branch
```

---

## ステップ7: よくあるワークフローを追加する

複数のステップを必要とし、繰り返し行うことはすべて、記録する価値があります。

```markdown
## Common Workflows

### Adding a new page
1. Create the route in `src/app/`
2. Add a server component for data fetching
3. Add a client component in `src/components/` for interactivity
4. Add the route to `src/config/nav.ts`

### Running the dev server
```bash
npm run dev
```
App runs at http://localhost:3000

### Creating a database migration
```bash
npx supabase migration new <migration-name>
```
Edit the file in `supabase/migrations/`, then run `npx supabase db push`.
```

---

## ステップ8: テストする

Fabric を開き、新しいチャットを開始して、こう尋ねます。*「このプロジェクトは何で、どんなテストフレームワークを使っている？」*

あなたが何も言わなくても Fabric が正しく答えれば、`AGENTS.md` は機能しています。

---

## ヒント

**正確に保つ。** AI は `AGENTS.md` の内容に従います — 古い情報が書かれていれば、古い挙動になります。スタックや慣習が変わったら見直しましょう。

**時間をかけて追記する。** 完璧なファイルを最初から書こうとしないでください。同じことで AI を2回訂正していることに気づいたら、その都度ルールを追加しましょう。

**コマンドは具体的に書く。** 「テストを実行して」では曖昧です。`npx vitest run` なら曖昧ではありません。

**コード以外のプロジェクトにも使う。** 執筆プロジェクト、リサーチフォルダ、財務モデル — どんなプロジェクトフォルダでも、Fabric の手助けの仕方を形作るコンテキストを記した `AGENTS.md` を持つことができます。
