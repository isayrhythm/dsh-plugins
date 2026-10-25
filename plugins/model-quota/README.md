<div align="center">

# 📊 dsh-model-quota

[![version](https://img.shields.io/github/package-json/v/isayrhythm/dsh-plugins?filename=plugins%2Fmodel-quota%2Fpackage.json&label=version)](plugins/model-quota)
[![license](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![DSH](https://img.shields.io/badge/DSH-%E2%89%A50.2-0f766e.svg)](https://github.com/deepseek-ai/deepseek-harness)
[![platform](https://img.shields.io/badge/platform-web-blue.svg)](#)

给 [DeepSeek Harness](https://github.com/deepseek-ai/deepseek-harness) 用的**模型额度面板**：左侧栏常驻一个入口，点开就是一张表 —— **每个账号 × 每个厂商**的订阅套餐、额度窗口和重置倒计时，不用再进「设置 → 插件」翻卡片。

</div>

## ✨ 功能

| | 功能 | 说明 |
| --- | --- | --- |
| 📌 | **侧栏入口** | 与「插件」「自动化任务」同级，点一下切到额度页（原生 `layout.selectPanel`，当前面板会高亮） |
| 📋 | **额度页** | 按账号分组，显示厂商徽章、订阅套餐（Pro 等）、全部额度窗口（5 小时 / 每周 / 每月）与「多久后刷新」 |
| ⭕ | **输入框圆环** | 模型名左侧一个小圆点，悬停即可看当前模型对应账号的额度 |
| 🔍 | **自动发现实例** | 读取 DSH 各 provider 的 `baseURL` 判断是否为 CliProxyAPI，不需要手工维护模型列表 |
| 🧩 | **多实例 / 多账号** | 支持同时看多个网关和多个登录账号 |
| 🎨 | **颜色语义** | 🟢 ≥20% 剩余 · 🟡 <20% · 🔴 已耗尽 · ⚪ 加载中 / 未配置 |
| 🪶 | **零依赖** | 纯 JavaScript，无构建步骤；管理密钥只存在当前浏览器的 `localStorage` |

## 🖼 截图

**额度页内容** —— 各账号 × 各厂商的额度窗口：

![额度页](assets/screenshots/settings-card-accounts.png)

**输入框模型名旁的圆环与悬浮卡**：

![圆环悬浮卡](assets/screenshots/quota-tooltip.png)

## 🚀 安装

```powershell
git clone https://github.com/isayrhythm/dsh-plugins.git
cd "$env:USERPROFILE\.dsh\profiles\desktop"
pnpm add "<clone 路径>\plugins\model-quota"
```

把 `"dsh-model-quota"` 加进该 profile `package.json` 的 `dsh.profile.bundles`，然后重启 DSH。

## ⚙️ 配置

1. 打开 DSH 设置 → 插件 → **CliProxyAPI 额度**
2. 填入 CLIProxyAPI 的**管理密钥**（`config.yaml` 里的 `management.secret-key`），保存
3. 实例会按 provider 的 `baseURL` 自动发现；也可以手动添加

> 管理接口需要在网关侧开启（`management.allow-remote: true`）；如果前面有反向代理，记得把 `/v0/management/` 也转发过去。

## ❓ 常见问题

<details>
<summary>圆环一直是灰色？</summary>

说明还没拿到数据：检查设置卡片里是否显示「可用 · N 个账号」。显示「未配置密钥」就先把管理密钥填上。

</details>

<details>
<summary>显示「无法连接」或 404？</summary>

说明浏览器请求不到管理接口 —— 确认网关的 `management.allow-remote` 已开启，且反代放行了 `/v0/management/` 与 `/v8/management/`。

</details>

## 📄 许可

MIT。初始版本参考并衍生自 `dsh-client-ui-cpa-quota`（MIT），MIT 版权声明见 [LICENSE](LICENSE)；此后本插件已独立演进。
