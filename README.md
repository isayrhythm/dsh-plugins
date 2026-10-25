# dsh-plugins

我（[isayrhythm](https://github.com/isayrhythm)）的 [DeepSeek Harness](https://github.com/deepseek-ai/deepseek-harness) 插件集合。

## 插件

| 插件 | 说明 | 目录 |
| --- | --- | --- |
| **model-quota** | 侧栏常驻入口「模型额度」：点开即看各账号、各厂商的订阅套餐与额度窗口（5 小时 / 每周 / 每月），输入框旁还有额度圆环 | [`plugins/model-quota`](plugins/model-quota) |
| **repo-snapshot** | 工作区仓库快照（含 `.git`）加密备份到本地目录或阿里云 OSS，带设置页 | [`plugins/repo-snapshot`](plugins/repo-snapshot) |

## 结构

```
dsh-plugins/
├─ plugins/
│  ├─ model-quota/     # dsh-model-quota
│  └─ repo-snapshot/   # dsh-plugin-repo-snapshot
├─ package.json        # workspace 根（private）
└─ pnpm-workspace.yaml
```

## 安装

每个插件都是独立包。以 `model-quota` 为例：

```powershell
git clone https://github.com/isayrhythm/dsh-plugins.git

# 在 DSH 的 profile 目录里把插件装进去
cd "$env:USERPROFILE\.dsh\profiles\desktop"
pnpm add "<clone 路径>\plugins\model-quota"
```

然后把包名加进该 profile 的 `package.json`：

```json
{
  "dsh": {
    "profile": {
      "bundles": ["@deepseek-ai/dsh-base", "@deepseek-ai/dsh-web-app", "dsh-model-quota"]
    }
  }
}
```

重启 DSH 生效。

## 许可

MIT，见 [LICENSE](LICENSE)。

`plugins/model-quota` 的初始版本参考并衍生自 `dsh-client-ui-cpa-quota`（MIT），此后已独立演进；原项目的 MIT 版权声明保留在 [plugins/model-quota/LICENSE](plugins/model-quota/LICENSE)。
