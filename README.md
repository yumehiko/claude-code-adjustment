# Claude Code Adjustment

自分のClaude Code用の設定をまとめています。

## 使い方

### copy rules

このプロジェクト内でClaude Codeを呼び出し、「copy rules」と入力すると、このプロジェクトの設定をユーザーのClaudeグローバル設定（~/.claude/以下）にClaudeがコピーします。

1. グローバルルール（`/rules/global/CLAUDE.md`）を `~/.claude/CLAUDE.md` にコピー
2. カスタムコマンド（`/rules/commands/`）を `~/.claude/commands/` にコピー
3. 既存の設定がある場合は、追加・マージ・置換を選択可能

### カスタムコマンド

以下のカスタムコマンドが利用可能です：

- `/ask` - 質問や疑問点を整理して、効果的な質問を生成
- `/spec` - 仕様や要件を明確化
- `/design` - 実装前に設計やアプローチを検討
- `/task` - タスクを整理して実行計画を立てる
- `/do` - 実行計画を指定し、未着手のタスクを実行する

詳細な使い方や活用例については [COMMANDS.md](./COMMANDS.md) を参照してください。

### ルールの開発

1. **グローバルルール**: `rules/global/CLAUDE.md` を編集して全プロジェクトに適用されるルールを定義
2. **プロジェクト固有ルール**: 特定のプロジェクト・フレームワーク向けのルールを、個別のディレクトリ内の `CLAUDE.md` に記載
3. **カスタムコマンド**: `rules/commands/` に新しい Markdown ファイルを追加