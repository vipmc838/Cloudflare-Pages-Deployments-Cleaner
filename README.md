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

> 🔗 脚本原作者：[@cm大佬](https://blog.cmliussss.com/p/CFPagesDeleteArchive/)  
> 感谢 cm 大佬无私分享原始脚本！

