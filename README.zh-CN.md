# GH2TG GitHub Actions 模板

[English](README.md) | [日本語](README.ja.md)

按下面步骤部署。模板默认监控 `sorubedo/gh2tg` 的提交、Release 和 `publish-images.yml` 工作流。

1. 新建一个 GitHub 仓库，把本目录中的文件上传到默认分支。
2. 打开仓库的 **Settings → Actions → General**，在 **Workflow permissions** 中选择 **Read and write permissions**，保存。
3. 打开 **Settings → Secrets and variables → Actions**，添加以下 Repository secrets：

   - `GH2TG_BOT_TOKEN`：Telegram Bot Token。
   - `GH2TG_GROUP_ID`：开启话题的 Telegram 超级群组 ID，例如 `-1001234567890`。
   - `GH2TG_GITHUB_TOKEN`：能读取待监控仓库的 GitHub Token。

4. 按需编辑 [`config.json`](config.json)。格式说明见 [GH2TG 配置文档](https://github.com/sorubedo/gh2tg#configuration)。
5. 打开 **Actions → Run GH2TG → Run workflow** 手动执行一次。

之后工作流每两小时执行一次。第一次执行只建立 `state.json` 基线，不发送已有历史；后续执行只发送新更新。工作流会自动提交 `state.json`，不要把它加入 `.gitignore`。
