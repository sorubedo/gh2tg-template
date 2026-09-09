# GH2TG GitHub Actions 模板

[English](README.md) | [日本語](README.ja.md)

[![Telegram](https://img.shields.io/badge/Telegram-@gh2tg-26A5E4?logo=telegram&logoColor=white)](https://t.me/gh2tg)

按下面步骤部署。模板默认监控 `sorubedo/gh2tg` 的提交、Release 和 `publish-images.yml` 工作流。

1. 下载并解压 [`gh2tg-template.tar.gz`](https://github.com/sorubedo/gh2tg-template/releases/latest/download/gh2tg-template.tar.gz)。压缩包只包含 `.github/workflows/gh2tg.yml` 和 `config.json`。
2. 新建一个 GitHub 仓库，把 `.github` 和 `config.json` 上传到默认分支。
3. 打开仓库的 **Settings → Actions → General**，在 **Workflow permissions** 中选择 **Read and write permissions**，保存。
4. 打开 **Settings → Secrets and variables → Actions**，添加以下 Repository secrets：

   - `GH2TG_BOT_TOKEN`：Telegram Bot Token。
   - `GH2TG_GROUP_ID`：开启话题的 Telegram 超级群组 ID，例如 `-1001234567890`。
   - `GH2TG_GITHUB_TOKEN`：能读取待监控仓库的 GitHub Token。

5. 按需编辑 [`config.json`](config.json)。格式说明见 [GH2TG 配置文档](https://github.com/sorubedo/gh2tg#configuration)。
6. 打开 **Actions → Run GH2TG → Run workflow** 手动执行一次。

之后工作流每小时执行一次。无需手动下载、创建或上传 `state.json`：首次运行会自动生成，之后由工作流自动维护并提交。不要把它加入 `.gitignore`。
