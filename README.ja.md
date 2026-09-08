# GH2TG GitHub Actions テンプレート

[English](README.md) | [中文](README.zh-CN.md)

以下の手順でデプロイします。テンプレートはデフォルトで `sorubedo/gh2tg` のコミット、Release、`publish-images.yml` ワークフローを監視します。

1. GitHub リポジトリを新規作成し、このディレクトリのファイルをデフォルトブランチにアップロードします。
2. リポジトリの **Settings → Actions → General** を開き、**Workflow permissions** で **Read and write permissions** を選択して保存します。
3. **Settings → Secrets and variables → Actions** で、次の Repository secrets を追加します。

   - `GH2TG_BOT_TOKEN`：Telegram Bot Token。
   - `GH2TG_GROUP_ID`：トピックを有効にした Telegram スーパーグループの ID。例：`-1001234567890`。
   - `GH2TG_GITHUB_TOKEN`：監視対象リポジトリを読み取れる GitHub Token。

4. 必要に応じて [`config.json`](config.json) を編集します。形式は [GH2TG 設定ドキュメント](https://github.com/sorubedo/gh2tg#configuration) を参照してください。
5. **Actions → Run GH2TG → Run workflow** を開き、手動で一度実行します。

ワークフローは 2 時間ごとに実行されます。`state.json` を手動でダウンロード、作成、アップロードする必要はありません。初回実行時に自動生成され、その後はワークフローが自動的に管理してコミットします。`.gitignore` に追加しないでください。
