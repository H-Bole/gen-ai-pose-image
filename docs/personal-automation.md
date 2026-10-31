# 个人 fork 自动化（当前关闭）

仅用于 H-Bole/gen-ai-pose-image，不向上游功能 PR 提交此配置。

上游同步流程已准备每日定时及手动入口。它只调用 GitHub 的 merge-upstream 接口合并 main，不强推、不重置；冲突会使流程失败并保留现有改动。

当前开关：仓库 Actions 关闭、同步工作流关闭、仓库变量 AUTO_UPSTREAM_SYNC_ENABLED=false。工作流同时校验仓库名与变量，避免在上游仓库运行。没有 push 触发器。

个人 Vercel 项目 lanpose-comfyui 保留 GitHub 关联以备将来使用，现阶段关闭 Preview 自动部署，并以项目 Ignored Build Step 的 exit 0 阻止 Git 自动构建；本分支 vercel.json 额外设置 git.deploymentEnabled=false。现有网站仍可访问，验收 Preview 仅通过明确的手动部署创建。

PR 合并不代表授权开启。只有用户之后主动明确要求开启时，才按顺序检查 main 与上游差异、解决冲突、自测，再恢复仓库 Actions、启用该工作流、设置变量为 true，并移除个人 Vercel 的禁用配置。不开启时，定时同步和推送自动部署均不得运行。
