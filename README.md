# shogo's Claude Code Plugin

Claude Code用のGitワークフロー支援プラグインです。Conventional CommitsとConventional Branchの規約に従った開発フローを自動化します。

## 機能

このプラグインは、以下のGitワークフローコマンドを提供します：

### コマンド一覧

- `/git-create-branch` - Conventional Branchに従ってブランチを作成
- `/git-create-commit` - Conventional Commitsに従ってコミットメッセージを作成
- `/git-create-pr` - GitHub PRをDraftで作成
- `/git-create-branch-commit-pr` - 上記3つのコマンドを順次実行

## セットアップ

### 必要要件

- Node.js v22.20.0
- Claude Code CLI
- GitHub CLI (`gh`)

### インストール

1. このリポジトリをクローン：

```bash
git clone https://github.com/shogo452/claude-code-plugin.git
```

2. Claude Codeのプラグインディレクトリにシンボリックリンクを作成：

```bash
ln -s /path/to/claude-code-plugin ~/.claude/plugins/shogo-claude-code-plugin
```

3. Claude Codeを再起動して、プラグインを読み込みます。

## 使い方

### ブランチ作成

```
/git-create-branch
```

[Conventional Branch](https://conventional-branch.github.io/)に従ったブランチ名を作成します。

形式: `feature/[FeatureName]-[実装した機能名]`

例: `feature/admin-user-role-edit-invite-form`

### コミット作成

```
/git-create-commit
```

[Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)に従ってコミットを実行します。

#### コミットメッセージの形式

- `type(scope): subject` の形式
- タイトルは50文字以内、本文は72文字程度で改行
- 動詞は原形を使用（add, fix, updateなど）
- scopeは原則記述するが、適切なものがない場合は省略可
- コミットメッセージは小文字で始める
- 実装とテストコードが含まれている場合、typeはtestよりもfeat/fixを優先

### PR作成

```
/git-create-pr
```

GitHub PRをDraftとして作成します。

- `.github/PULL_REQUEST_TEMPLATE.md`が存在する場合はそれに従います
- テンプレートがない場合は、基本的なWhy/What形式で作成
- `git push -u origin <branch_name>`で自動的にupstreamを設定

### 完全なワークフロー

```
/git-create-branch-commit-pr
```

ブランチ作成、コミット、PR作成を一度に実行します。

## ライセンス

MIT

## 作者

shogo452

## リポジトリ

https://github.com/shogo452/claude-code-plugin
