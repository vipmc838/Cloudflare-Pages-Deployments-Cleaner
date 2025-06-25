# 🚀 Cloudflare Pages 部署清理工具

当 Cloudflare Pages 项目部署次数超过 100 次后，将**无法通过网页界面删除部署记录**，这是一个已知限制。  
本工具使用 Cloudflare 官方 API，通过 Node.js 脚本或 GitHub Actions 实现 **批量删除历史部署记录**，仅保留当前生产版本。

---

## 🧰 功能特性

- ✅ 自动获取所有部署列表  
- ✅ 排除当前生产版本部署（canonical deployment）  
- ✅ 支持强制删除 alias 版本  
- ✅ 支持命令行手动运行或 GitHub Actions 自动执行  

---

## 🧪 使用方式 1：本地命令行执行

> 🔗 脚本原作者：[**@cm大佬**](https://github.com/cmliu)  
> 📖 [点击查看原文教程](https://blog.cmliussss.com/p/CFPagesDeleteArchive/)  
> 🙏 致谢 cm 大佬无私分享原始脚本！

## 🤖 使用方式 2：GitHub Actions 自动执行
你也可以将删除任务交给 GitHub Actions 自动运行，无需本地环境！

### 📁 项目结构示例
.
├── index.js                # 主脚本
├── package.json
├── package-lock.json
└── .github/
    └── workflows/
        └── delete-cf-pages.yml

### ✅ 添加 GitHub Secrets

进入仓库 → Settings → Secrets and variables → Actions，添加以下 3 项：

## 环境变量配置

| 环境变量             | 说明                 |
| ---------------- | -------------------- |
| `CF_API_TOKEN`     | Cloudflare API 令牌  |
| `CF_ACCOUNT_ID`  | 	Cloudflare 帐号 ID|
| `CF_PAGES_PROJECT_NAME`   | Pages 项目名称 |

### ▶️ 执行方式
1. 打开 GitHub 仓库主页 → Actions

2. 选择工作流程：Delete Cloudflare Pages Deployments

3. 点击右上角 Run workflow ➝ 执行任务

### ⚠️ 注意事项
- 🛑 不可恢复：部署删除后不可恢复，请谨慎操作。

- 🔐 权限要求：API Token 需具备“编辑 Cloudflare Workers”权限。

- ⏳ 删除速度：部署数量大时请耐心等待，脚本已支持退避重试机制。
