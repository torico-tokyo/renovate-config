# renovate-config

TORICO Renovate Shareable Config Presets

## ドキュメント

[Renovate Shareable Config Presets](https://docs.renovatebot.com/config-presets/)

## 設定方法

.github リポジトリにrenovate.json を追加して、リポジトリに内容にあった設定をextends に指定して使用する。

### 共通の設定

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>torico-tokyo/renovate-config"]
}
```

### Node.js + pnpm

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": [
    "github>torico-tokyo/renovate-config",
    "github>torico-tokyo/renovate-config:nodejs-pnpm"
  ]
}
```
