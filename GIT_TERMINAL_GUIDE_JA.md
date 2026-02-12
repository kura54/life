# Git Terminal Guide (Japanese)

## 0. 今回の状態

- `origin` は設定済み: `git@github.com:kura54/life.git`
- 作業ブランチは作成済み: `codex/life-secretary-demo`
- `push` 失敗理由: GitHub に SSH 公開鍵が未登録

## 1. まず1回だけやる初期設定

```bash
git config --global user.name "Ryota Kuratomo"
git config --global user.email "125339052+RyotaKuratomo54@users.noreply.github.com"
git config --global init.defaultBranch main
```

## 2. SSH鍵を GitHub に登録

1. 次の公開鍵をコピー:

```text
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIA9LQIHonzU9GDggnQdk66xQd7Nq3QGuB1aQF/ZzJoYD macbook-to-lab
```

2. GitHub の `Settings > SSH and GPG keys > New SSH key` で貼り付けて保存
3. 接続確認:

```bash
ssh -T git@github.com
```

`Hi <username>!` が出ればOK。

## 3. 今回の push を完了する

```bash
cd /Users/kuratomoryota/Desktop/Codex
git push -u origin codex/life-secretary-demo
```

## 4. 毎日の基本コマンド

```bash
git status
git switch -c codex/<branch-name>
git add <file>
git commit -m "message"
git push -u origin codex/<branch-name>
```

## 5. よく使う復旧コマンド

```bash
git log --oneline --decorate -n 10
git diff
git restore --staged <file>
git switch <branch>
```

注意: `git reset --hard` は内容を消すので、慣れるまで使わない。
