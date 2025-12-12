# PRを作成

- Read @.github/PULL_REQUEST_TEMPLATE.md に従うこと
  - @.github/PULL_REQUEST_TEMPLATE.md が存在しない場合は、以下のフォーマットで作成すること

  ```markdown
  ## Why

  ## What
  ```

- Draftで作成すること
- push時は`git push -u origin <branch_name>` のように `--set-upstream` を指定すること
- コマンドの例: `gh pr create --draft --title "title" --body "body"`
