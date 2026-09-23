# 发布说明

## GitHub 文件分工

- Git 仓库：README、发布说明、校验清单和轻量文档。
- GitHub Release：当前版本的 EXE、MSI、校验清单。
- 网盘或对象存储：约 2.3 GB 的 `packages` 离线安装包目录。

GitHub 普通仓库不适合保存大体积离线安装包；超过单文件限制的安装包不能通过普通 `git push` 上传。不要使用 Git LFS 代替网盘作为唯一交付渠道，除非已配置可持续的 LFS 配额和账单。

## 当前版本

- 架构：Windows x64
- 直接运行版：`DevEnvironmentInstaller.exe`
- 安装包：`DevEnvironmentInstaller.msi`
- 完整离线包：`packages/`，单独分发

## 发布检查

1. 在 Windows 10/11 x64 测试机验证程序启动。
2. 只读扫描通过后再验证安装流程。
3. 单独验证 MSI 安装成功提示和桌面快捷方式。
4. 发布 EXE、MSI 和 `SHA256SUMS.txt`。
5. 同步发布离线包目录的下载地址和同版本哈希清单。
