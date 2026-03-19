# GitHub Flow 学習ガイド

GitHub CLI (`gh`) を活用したモダンな開発フローの手順です。

## 1. Issue の作成
まず、何を修正・追加するかを Issue として登録します。

```powershell
gh issue create --title "Issueのタイトル" --body "Issueの内容"
```

## 2. ブランチの作成と切り替え
作業用の新しいブランチを作成します。

```powershell
git checkout -b branch-name
```

## 3. ファイルの修正とコミット
通常通りファイルを修正し、コミットします。

```powershell
git add .
git commit -m "コミットメッセージ"
```

## 4. GitHub へプッシュ
作成したブランチを GitHub へ送信します。初回は `-u origin branch-name` を付けます。

```powershell
git push -u origin branch-name
```

## 5. プルリクエスト (PR) の作成
GitHub CLI を使って PR を作成します。

```powershell
gh pr create --title "PRのタイトル" --body "PRの詳細内容" --base main
```

## 6. PR のマージ
レビューが完了したら、PR をメインブランチにマージします。作業ブランチの削除も同時に行えます。

```powershell
gh pr merge --merge --delete-branch
```

## 7. ローカルの同期
メインブランチに戻り、最新の状態を反映させます。

```powershell
git checkout main
git pull origin main
```
