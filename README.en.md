<div align="center">

# 🧩 dsh-plugins

[![license](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![DSH](https://img.shields.io/badge/DSH-plugin-0f766e.svg)](https://github.com/deepseek-ai/deepseek-harness)
[![platform](https://img.shields.io/badge/platform-web-blue.svg)](#)
[![last commit](https://img.shields.io/github/last-commit/isayrhythm/dsh-plugins)](https://github.com/isayrhythm/dsh-plugins/commits/main)
[![stars](https://img.shields.io/github/stars/isayrhythm/dsh-plugins)](https://github.com/isayrhythm/dsh-plugins/stargazers)

</div>

## 📦 Plugins

| Plugin | Description | Path |
| --- | --- | --- |
| 📊 **model-quota**<br><sub>`dsh-model-quota` ![v](https://img.shields.io/github/package-json/v/isayrhythm/dsh-plugins?filename=plugins%2Fmodel-quota%2Fpackage.json)</sub> | A sidebar entry ("模型额度") that opens per-account, per-provider subscription quotas — 5-hour, weekly and monthly windows — plus a quota ring next to the composer model name | [`plugins/model-quota`](plugins/model-quota) |
| 💾 **repo-snapshot**<br><sub>`dsh-plugin-repo-snapshot` ![v](https://img.shields.io/github/package-json/v/isayrhythm/dsh-plugins?filename=plugins%2Frepo-snapshot%2Fpackage.json)</sub> | Encrypted workspace repo snapshots (including `.git`) to a local folder or Aliyun OSS, with a settings page | [`plugins/repo-snapshot`](plugins/repo-snapshot) |

## 🗂 Layout

```
dsh-plugins/
├─ plugins/
│  ├─ model-quota/     # dsh-model-quota
│  └─ repo-snapshot/   # dsh-plugin-repo-snapshot
├─ package.json        # workspace root (private)
└─ pnpm-workspace.yaml
```

## 🚀 Install

```powershell
git clone https://github.com/isayrhythm/dsh-plugins.git
cd "$env:USERPROFILE\.dsh\profiles\desktop"
pnpm add "<clone path>\plugins\model-quota"
```

Add the package name to that profile's `package.json` under `dsh.profile.bundles`, then restart DSH.

## 📄 License

MIT — see [LICENSE](LICENSE).

`plugins/model-quota` started as a derivative of `dsh-client-ui-cpa-quota` (MIT) and has since evolved independently; the original MIT notice is kept in [plugins/model-quota/LICENSE](plugins/model-quota/LICENSE).
