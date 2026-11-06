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

### GitHub Packages の社内 npm パッケージを使うリポジトリ

`@torico-tokyo/*` を GitHub Packages（`npm.pkg.github.com`）から取得するリポジトリでは、
lockfile の更新時にパッケージを取得できるように `githubPackages` を追加する。
リポジトリの `.npmrc` にある `${TORICO_GITHUB_TOKEN}` のような環境変数の行は Renovate が読み飛ばすため、
認証はこのプリセットの `hostRules` で渡す。

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": [
    "github>torico-tokyo/renovate-config",
    "github>torico-tokyo/renovate-config:nodejs-pnpm",
    "github>torico-tokyo/renovate-config:githubPackages"
  ]
}
```

事前に [Mend Developer Portal](https://developer.mend.io/) の torico-tokyo 組織の設定で、
`TORICO_GITHUB_TOKEN` という名前の secret を登録しておく。値は `read:packages` 権限を持つ classic PAT にする。
secret がないままこのプリセットを読み込むと、そのリポジトリの Renovate が設定エラーで止まる。
