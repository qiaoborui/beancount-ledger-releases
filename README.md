# Ledger iOS 发布

[Beancount Ledger Web](https://github.com/qiaoborui/beancount-ledger-web) 的 iOS App（Ledger）的安装包和 SideStore 源。

这个仓库只放发布产物：

- `sidestore/source.json`：SideStore / AltStore 源。
- [Releases](https://github.com/qiaoborui/beancount-ledger-releases/releases)：每个版本的 IPA，以及对应的 `.sha256`。

源码、文档和问题反馈都在 [beancount-ledger-web](https://github.com/qiaoborui/beancount-ledger-web)。

## 用 SideStore 安装

> 第一个版本发布之前，源里还没有 App，添加后是空的。`sidestore/app.json` 是 App 的介绍信息，第一次发版时由发布脚本写进源里。

1. 打开 SideStore，进入「源」，点「+」，添加下面这个地址：

   ```
   https://raw.githubusercontent.com/qiaoborui/beancount-ledger-releases/main/sidestore/source.json
   ```

2. 在源里找到 Ledger，点「获取」。以后有新版本，SideStore 会提示升级。

也可以从 Releases 下载 IPA，再用 SideStore / AltStore / iLoader 手动安装。IPA 是 ad-hoc 签名，安装时会用你自己的证书重新签名。

最低系统版本：iOS 17.0。

## 校验

每个 IPA 旁边都有一个 `.sha256` 文件，`source.json` 里每个版本也记录了 `sha256`：

```sh
shasum -a 256 -c LedgerMobile-<版本>-<构建号>.ipa.sha256
```

## 版本号

- 版本号（如 `0.5.0`）对应源码仓库里的 `v<版本号>` 标签。
- 构建号每打一次包加一，SideStore 用它判断有没有新包，不会重复使用。

## 第三方组件

见 [NOTICE](NOTICE)。
