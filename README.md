# GH2TG GitHub Actions Template

[中文文档](README.zh-CN.md) | [日本語](README.ja.md)

[![Telegram](https://img.shields.io/badge/Telegram-@gh2tg-26A5E4?logo=telegram&logoColor=white)](https://t.me/gh2tg)

Follow these steps to deploy. The template monitors commits, releases, and the `publish-images.yml` workflow in `sorubedo/gh2tg` by default.

1. Download and extract [`gh2tg-template.tar.gz`](https://github.com/sorubedo/gh2tg-template/releases/latest/download/gh2tg-template.tar.gz). It contains only `.github/workflows/gh2tg.yml` and `config.json`.
2. Create a GitHub repository and upload `.github` and `config.json` to its default branch.
3. Open **Settings → Actions → General**, select **Read and write permissions** under **Workflow permissions**, and save.
4. Under **Settings → Secrets and variables → Actions**, add these repository secrets:

   - `GH2TG_BOT_TOKEN`: Telegram Bot token.
   - `GH2TG_GROUP_ID`: Telegram supergroup ID with Topics enabled, for example `-1001234567890`.
   - `GH2TG_GITHUB_TOKEN`: GitHub token that can read the repositories to monitor.

5. Edit [`config.json`](config.json) as needed. See the [GH2TG configuration documentation](https://github.com/sorubedo/gh2tg#configuration) for the format.
6. Open **Actions → Run GH2TG → Run workflow** to run it once manually.

The workflow runs every two hours. You do not need to download, create, or upload `state.json` manually: the first run creates it, and the workflow maintains and commits it automatically. Do not add it to `.gitignore`.
