# dsh-plugins

My ([isayrhythm](https://github.com/isayrhythm)) collection of [DeepSeek Harness](https://github.com/deepseek-ai/deepseek-harness) plugins.

## Plugins

| Plugin | Description | Path |
| --- | --- | --- |
| **model-quota** | A sidebar entry ("模型额度") that opens per-account, per-provider subscription quotas — 5-hour, weekly and monthly windows — plus a quota ring next to the composer model name | [`plugins/model-quota`](plugins/model-quota) |
| **repo-snapshot** | Encrypted workspace repo snapshots (including `.git`) to a local folder or Aliyun OSS, with a settings page | [`plugins/repo-snapshot`](plugins/repo-snapshot) |

## Install

```powershell
git clone https://github.com/isayrhythm/dsh-plugins.git
cd "$env:USERPROFILE\.dsh\profiles\desktop"
pnpm add "<clone path>\plugins\model-quota"
```

Then add the package name to that profile's `package.json` under `dsh.profile.bundles`, and restart DSH.

## License

MIT — see [LICENSE](LICENSE).

`plugins/model-quota` started as a derivative of `dsh-client-ui-cpa-quota` (MIT) and has since evolved independently; the original MIT notice is kept in [plugins/model-quota/LICENSE](plugins/model-quota/LICENSE).
