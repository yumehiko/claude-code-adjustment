# カスタムコマンド詳細

このドキュメントでは、Claude Code 用のカスタムコマンドの詳細な使い方と活用例を説明します。

## コマンド一覧

### `/ask` - 質問コマンド

**目的**: エージェントに、作業などを求めず、単に質問する

```
/ask 質問内容
```

---

### `/spec` - 仕様作成コマンド

**目的**: 自然言語による要求から明確な仕様書（specs/your-feature-name/requirements.md）を作成します。

```
/spec ユーザー認証機能を追加したい
```

---

### `/design` - 技術設計書作成コマンド

**目的**: requirements.mdを基に技術設計書（design.md）を作成します。

```
/design your-feature-name
```

---

### `/task` - 実装タスクリスト作成コマンド

**目的**: design.mdを基に実装タスクリスト（tasks.md）を作成します。

```
/task your-feature-name
```

---

### `/do` - タスク実行コマンド

**目的**: task.mdにあるタスクのうち、未着手のものを1つ選び実行します。

```
/do your-feature-name
```

---

## ドキュメント駆動開発のワークフロー

これらのコマンドは、以下のワークフローで使用されることを想定しています：

1. **要件定義**: `/spec` コマンドで要件を明確化（→ requirements.md）
2. **技術設計**: `/design` コマンドで設計書を作成（requirements.md → design.md）
3. **タスク計画**: `/task` コマンドでタスクリストを作成（design.md → tasks.md）
4. **実装**:  `/do` コマンドでタスクを1つずつ実行