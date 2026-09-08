# GH2TG GitHub Actions Template

[中文文档](README.zh-CN.md) | [日本語](README.ja.md)

Follow these steps to deploy. The template monitors commits, releases, and the `publish-images.yml` workflow in `sorubedo/gh2tg` by default.

1. Create a GitHub repository and upload these files to its default branch.
2. Open **Settings → Actions → General**, select **Read and write permissions** under **Workflow permissions**, and save.
3. Under **Settings → Secrets and variables → Actions**, add these repository secrets:

   - `GH2TG_BOT_TOKEN`: Telegram Bot token.
   - `GH2TG_GROUP_ID`: Telegram supergroup ID with Topics enabled, for example `-1001234567890`.
   - `GH2TG_GITHUB_TOKEN`: GitHub token that can read the repositories to monitor.

4. Edit [`config.json`](config.json) as needed. See the [GH2TG configuration documentation](https://github.com/sorubedo/gh2tg#configuration) for the format.
5. Open **Actions → Run GH2TG → Run workflow** to run it once manually.

The workflow runs every two hours. The first run only establishes the `state.json` baseline; later runs send new updates. The workflow commits `state.json` automatically, so do not add it to `.gitignore`.
