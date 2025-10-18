# GitHub セットアップガイド

このガイドでは、GA4-AI-Workflowリポジトリを GitHubにアップロードする手順を説明します。

---

## 📋 前提条件

- GitHubアカウントを持っていること
- Gitがローカル環境にインストールされていること
- コマンドライン（ターミナル）の基本操作ができること

---

## 🚀 手順1: GitHubでリポジトリを作成

### 1-1. GitHubにログイン

[GitHub](https://github.com/) にアクセスしてログイン

### 1-2. 新しいリポジトリを作成

1. 右上の「+」アイコンをクリック → 「New repository」を選択
2. 以下の情報を入力：

```
Repository name: ga4-ai-workflow
Description: GA4データ分析とAI活用による実践的マーケティング改善ワークフロー集
```

3. 公開設定を選択：
   - **Public**: 誰でも閲覧可能（オープンソースとして公開）
   - **Private**: 自分だけ、または招待した人のみ閲覧可能

4. 以下のオプションは**チェックしない**（ローカルに既にファイルがあるため）：
   - ❌ Add a README file
   - ❌ Add .gitignore
   - ❌ Choose a license

5. 「Create repository」ボタンをクリック

---

## 🚀 手順2: ローカルリポジトリの初期化とアップロード

### 2-1. ターミナルで作業ディレクトリに移動

```bash
cd /path/to/ga4-ai-workflow
```

### 2-2. Gitリポジトリを初期化

```bash
git init
```

### 2-3. すべてのファイルをステージング

```bash
git add .
```

### 2-4. 初回コミット

```bash
git commit -m "Initial commit: GA4 AI Workflow complete guide"
```

### 2-5. メインブランチの名前を設定

```bash
git branch -M main
```

### 2-6. リモートリポジトリを追加

```bash
# あなたのGitHubユーザー名に置き換えてください
git remote add origin https://github.com/YOUR_USERNAME/ga4-ai-workflow.git
```

### 2-7. GitHubにプッシュ

```bash
git push -u origin main
```

**認証情報を求められた場合:**
- Username: あなたのGitHubユーザー名
- Password: GitHubのパーソナルアクセストークン（PAT）
  - [Personal Access Token作成方法](#personal-access-tokenの作成方法) を参照

---

## 🔑 Personal Access Token の作成方法

GitHub は2021年8月以降、パスワード認証を廃止しました。代わりにPersonal Access Token (PAT) を使用します。

### 手順

1. GitHub にログイン
2. 右上のプロフィールアイコン → **Settings**
3. 左側メニュー最下部の **Developer settings**
4. **Personal access tokens** → **Tokens (classic)**
5. **Generate new token** → **Generate new token (classic)**
6. 以下を設定：
   - Note: `GA4 Workflow Upload`
   - Expiration: `90 days`（または好みの期間）
   - Select scopes:
     - ✅ **repo**（すべてのサブ項目）
7. **Generate token** をクリック
8. **トークンをコピー**（このページを離れると二度と表示されません）

### トークンの使用

```bash
git push -u origin main
```

- Username: あなたのGitHubユーザー名
- Password: **コピーしたトークン**を貼り付け

---

## 📝 手順3: リポジトリの設定（オプション）

### 3-1. About（リポジトリ説明）の設定

1. GitHubのリポジトリページにアクセス
2. 右側の⚙️（歯車アイコン）をクリック
3. 以下を入力：

```
Description: GA4データ分析とAI活用による実践的マーケティング改善ワークフロー集

Website: （あなたのWebサイトがあれば）

Topics: 
- google-analytics
- ga4
- ai
- marketing
- data-analysis
- workflow
- e-commerce
- seo
```

### 3-2. README.mdのプレビュー確認

- リポジトリトップページで README.md が正しく表示されているか確認
- 画像リンクやMarkdownの構文が正しいか確認

### 3-3. GitHub Pages の有効化（オプション）

静的サイトとして公開したい場合：

1. リポジトリの **Settings** タブ
2. 左側メニューの **Pages**
3. Source: `Deploy from a branch`
4. Branch: `main` / `/ (root)`
5. **Save**

数分後、 `https://YOUR_USERNAME.github.io/ga4-ai-workflow/` でアクセス可能になります。

---

## 🎨 手順4: リポジトリのカスタマイズ

### 4-1. Badges（バッジ）の追加

README.md の上部に以下のようなバッジを追加すると見栄えが良くなります：

```markdown
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![GA4](https://img.shields.io/badge/Google%20Analytics-4-blue)](https://analytics.google.com/)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)
[![GitHub stars](https://img.shields.io/github/stars/YOUR_USERNAME/ga4-ai-workflow)](https://github.com/YOUR_USERNAME/ga4-ai-workflow/stargazers)
```

### 4-2. Topics（トピック）の追加

リポジトリページの右側「About」セクション → ⚙️ → Topics に以下を追加：

```
google-analytics, ga4, ai, chatgpt, claude, marketing, data-analysis,
e-commerce, seo, workflow, digital-marketing, conversion-optimization
```

---

## 🔄 手順5: 更新時のワークフロー

### ファイルを変更した後

```bash
# 変更を確認
git status

# 変更をステージング
git add .

# コミット（変更内容を説明するメッセージを記載）
git commit -m "Update: プロンプトテンプレートを改善"

# GitHubにプッシュ
git push origin main
```

### 便利なGitコマンド

```bash
# 現在のブランチ確認
git branch

# 変更履歴を表示
git log --oneline

# リモートリポジトリのURL確認
git remote -v

# 最後のコミットを取り消す（まだpushしていない場合）
git reset --soft HEAD~1
```

---

## 🌟 手順6: コミュニティ機能の活用

### 6-1. Issues の有効化

リポジトリの **Settings** → **Features** → ✅ Issues

ユーザーからの質問やバグレポートを受け付けられます。

### 6-2. Discussions の有効化

リポジトリの **Settings** → **Features** → ✅ Discussions

コミュニティとの交流、Q&A、アイデア共有に活用できます。

### 6-3. CONTRIBUTING.md の作成

貢献ガイドラインを作成すると、オープンソースプロジェクトとして成長しやすくなります。

```markdown
# 貢献ガイド

このプロジェクトへの貢献を歓迎します！

## 貢献方法

1. このリポジトリをフォーク
2. 新しいブランチを作成 (`git checkout -b feature/amazing-feature`)
3. 変更をコミット (`git commit -m 'Add: 新しいワークフロー追加'`)
4. ブランチにプッシュ (`git push origin feature/amazing-feature`)
5. Pull Request を作成

## コーディング規約

- Markdownファイルは日本語で記述
- コード例は実行可能な状態で提供
- 新しいワークフローは `prompts/` フォルダに追加
```

---

## 📊 手順7: アナリティクスとモニタリング

### 7-1. GitHub Insights の活用

リポジトリの **Insights** タブで以下を確認できます：

- 📈 Traffic: 訪問者数、閲覧ページ
- ⭐ Stars: スター数の推移
- 🔄 Network: フォークの状況
- 👥 Community: 貢献者の情報

### 7-2. Star History の追加

README.md に以下を追加すると、スター数の推移グラフを表示できます：

```markdown
## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=YOUR_USERNAME/ga4-ai-workflow&type=Date)](https://star-history.com/#YOUR_USERNAME/ga4-ai-workflow&Date)
```

---

## 🐛 トラブルシューティング

### エラー: "Authentication failed"

**原因**: パスワードの代わりにPersonal Access Tokenが必要

**解決策**: [Personal Access Tokenの作成方法](#personal-access-tokenの作成方法) を参照

---

### エラー: "remote: Repository not found"

**原因**: リモートURLが間違っている

**解決策**:
```bash
# 現在のリモートURLを確認
git remote -v

# 正しいURLに変更
git remote set-url origin https://github.com/YOUR_USERNAME/ga4-ai-workflow.git
```

---

### エラー: "fatal: refusing to merge unrelated histories"

**原因**: リモートとローカルの履歴が異なる

**解決策**:
```bash
git pull origin main --allow-unrelated-histories
```

---

### プッシュが遅い / タイムアウトする

**原因**: ファイルサイズが大きい、またはネットワーク問題

**解決策**:
```bash
# 大きなファイルを .gitignore に追加
echo "*.csv" >> .gitignore
echo "*.xlsx" >> .gitignore

# キャッシュをクリア
git rm -r --cached .
git add .
git commit -m "Update .gitignore"
```

---

## 📚 参考リソース

- [GitHub公式ドキュメント](https://docs.github.com/ja)
- [Git公式ドキュメント](https://git-scm.com/doc)
- [GitHub Skills（学習コース）](https://skills.github.com/)
- [Markdown記法ガイド](https://guides.github.com/features/mastering-markdown/)

---

## 📞 サポート

問題が発生した場合は、以下の方法でサポートを求めてください：

1. **GitHub Issues**: リポジトリの Issues タブで質問
2. **GitHub Discussions**: コミュニティに質問
3. **Stack Overflow**: `git` または `github` タグで質問

---

## ✅ チェックリスト

アップロード完了後、以下を確認してください：

- [ ] README.md が正しく表示されている
- [ ] LICENSE ファイルが認識されている
- [ ] .gitignore が機能している（不要なファイルが含まれていない）
- [ ] すべての Markdown ファイルがリンク切れなく表示される
- [ ] About セクションに説明とトピックが設定されている
- [ ] Issues / Discussions が有効化されている（オプション）

---

**🎉 おめでとうございます！**

GitHubへのアップロードが完了しました。

リポジトリURL: `https://github.com/YOUR_USERNAME/ga4-ai-workflow`

ぜひSNSでシェアして、コミュニティに貢献してください！

---

最終更新: 2025年10月18日
