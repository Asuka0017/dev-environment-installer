# 环境类型目录

安装器使用 `config/environment-catalog.json` 管理四个环境套装。套装只负责分类和批量勾选，所有组件仍在同一个安装列表中展示。

- `计算机软件开发必备`：VS Code、Python、Node.js、pnpm、JDK 17/25、Maven、Git、MySQL 生态和 Navicat。
- `办公与文档处理`：7-Zip、LibreOffice、Pandoc，以及用户自备的 Microsoft Office LTSC/专业增强版。
- `系统运行库与硬件支持`：Visual C++、PowerShell 7 和 Windows 硬件驱动检测。
- `其他专业开发环境`：Arduino IDE、R 和 kubectl。

## 本地包策略

- `bundled`：安装包随发布目录提供，安装前校验 SHA-256，可完全离线安装。
- `user-provided`：用户提供合法本地安装包或许可证。当前为 Office 和 Navicat，不会随公开程序分发。
- `system-managed`：由 Windows 根据当前硬件和系统功能处理。当前为 Windows 硬件驱动检测，不会用通用驱动覆盖用户设备。

当前所有 `bundled` 组件必须同时存在于 `源码/packages` 和正式发布目录的 `packages` 中。缺失的用户自备包会保持可见，但不能进入安装计划；系统管理项只提供检测和官方入口引导。

组件的 `installLocationPolicy` 明确安装位置：`managed-root` 使用用户选择的环境目录，`system-default` 遵循 Windows 系统目录，`vendor-default` 遵循厂商默认目录。

## 校验

```powershell
pwsh -NoProfile -File tests/EnvironmentCatalog.Tests.ps1
```
