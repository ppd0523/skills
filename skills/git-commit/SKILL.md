---
name: git-commit
description: Split staged changes into coherent commits and write Conventional Commit messages. Use when the user asks to commit staged work or create commits.
---

# Git Commit

Create one commit per coherent change group. Do not combine unrelated staged changes into one commit. A single commit is appropriate only when all staged changes serve the same intent.

## Workflow

1. Inspect `git status --short`, `git diff --cached`, and `git diff`. Treat staged changes as the commit scope; do not include unstaged or untracked changes unless the user asks.
2. Group the staged changes by intent, such as a fix, feature, documentation update, or refactor. Keep dependent changes together and order commits so each one makes sense on its own.
3. If unstaged edits overlap a staged file, do not unstage or add that whole file: that could change what the user chose to stage. Explain the overlap and ask the user to stage the intended hunks or clarify how to proceed.
4. When the staged paths can be safely regrouped, unstage only those paths with `git restore --staged -- <paths>`; this keeps their worktree edits. Stage one group at a time, using `git add -p` when a file contains separate concerns.
5. Before each commit, inspect `git diff --cached` and confirm it contains only the current group. Commit it, then repeat for the next group.
6. After the last commit, inspect `git status --short` and confirm no unstaged or untracked work was committed accidentally. Do not push unless the user asks.

If the staged changes do not have a clear grouping, show the proposed groups and ask before committing.

## Commit message

Use the Conventional Commits form:

```text
<type>[optional scope][!]: <short description>
```

Choose a type that matches the group, commonly `feat`, `fix`, `docs`, `refactor`, `perf`, `test`, `build`, `ci`, `chore`, or `revert`. Keep the subject specific to that commit. Use a `BREAKING CHANGE:` footer for a breaking change.

Write the body as a list, one `* ` item per change, never as narrative paragraphs. Keep each item short: one line, what changed (and why only when it is not obvious). Skip the body when the subject already says everything.

```text
feat(viewer): 타임라인을 새 창으로 띄우기

* 타임라인 막대에 새 창 버튼 추가
* 팝업과 메인 창이 같은 app 상태 공유
* 팝업을 닫으면 메인 창으로 복귀
```

Write the subject and any body in Korean. Keep Conventional Commit type names and optional scopes in English.
