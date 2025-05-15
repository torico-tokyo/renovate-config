# renovate-config

TORICO Renovate Shareable Config Presets

## ドキュメント

[Renovate Shareable Config Presets](https://docs.renovatebot.com/config-presets/)

## 設定方法

renovate.json のextends に設定して使う  

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>torico-tokyo/renovate-config"]
}
```


Node.js + pnpm のプロジェクトでは以下の設定で使う。

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": [
    "github>torico-tokyo/renovate-config",
    "github>torico-tokyo/renovate-config:nodejs-pnpm"
  ]
}
```
