# 开发环境安装器

Windows 10/11 x64 的开发环境安装器发布页。安装器支持本地离线安装、环境扫描、组件选择、安装后验证和错误报告处理。

## 下载

请进入 [Releases](https://github.com/Asuka0017/dev-environment-installer/releases) 下载：

- `DevEnvironmentInstaller.exe`：直接运行版。
- `DevEnvironmentInstaller.msi`：Windows 安装包，可创建桌面快捷方式。

完整离线环境包约 2.3 GB，不放入 Git 仓库。需要完全离线安装时，除了 EXE/MSI，还需要从网盘或对象存储获取与版本匹配的 `packages` 目录，并放在程序目录下。

## 使用方式

1. 下载 Release 中的程序文件并校验 SHA-256。
2. 直接运行 EXE，或安装 MSI 后从桌面快捷方式启动。
3. 首次启动完成平台授权和只读环境扫描。
4. 选择环境套装、安装路径和安装模式。
5. 阅读并同意用户协议和隐私政策后开始安装。

安装前请备份重要数据。MySQL 替换或更新前必须完成原数据库备份和验证；本程序不会无提示删除用户数据库。

## 当前组件范围

开发组件包括 Visual C++、MySQL Server 及相关工具、Node.js、pnpm、OpenJDK 17/25、Maven、Git、Python、Visual Studio Code、Navicat 等。实际可离线安装项以对应版本的 `config/packages.json` 和发布说明为准。

## 校验下载文件

PowerShell：

```powershell
Get-FileHash .\DevEnvironmentInstaller.exe -Algorithm SHA256
Get-FileHash .\开发环境安装器.msi -Algorithm SHA256
```

将结果与 Release 中的 `SHA256SUMS.txt` 对比。

## 离线包交付

离线安装包体积较大，不提交到 GitHub Git 历史。请从项目发布页提供的网盘或对象存储地址下载对应 `packages` 目录，并保持文件名不变。程序安装前会校验离线包哈希，缺包或哈希不一致时会停止执行。

## 免责声明

本项目仅用于学习、研究和课程实践。第三方软件的版权、许可证和使用条款归其权利人所有；使用者应自行确认所在地区和使用场景的合规性。
