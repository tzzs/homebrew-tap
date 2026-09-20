# homebrew-tap

@tzzs 的 Homebrew tap，目前收录：

- [CableScope](https://github.com/tzzs/cablescope) — macOS USB-C / Thunderbolt 线缆检测工具（菜单栏 App + CLI）

## 安装

**菜单栏 App**（源码构建，需要 Xcode 15+ 工具链）

```bash
brew install tzzs/tap/cablescope-app
```

装完按 `brew info` 打印的 `ln -s` 命令软链到 `/Applications`，即可在访达与启动台中看到它。

**命令行工具**

```bash
brew install tzzs/tap/cablescope-cli
cablescope pretty
```

## 关于 cask

`Casks/cablescope.rb` 暂未提供。Homebrew 的 cask 安装必定给 app 打上
`com.apple.quarantine` 且不提供关闭开关，未经 Apple 公证的 app 装完会被
Gatekeeper 拒绝打开——与其发一个装了打不开的版本，不如暂不提供。

上游配置好 Apple 开发者证书后，[cablescope 的发布工作流](https://github.com/tzzs/cablescope/blob/main/.github/workflows/release.yml)
会在发版时自动重新创建并维护它。

两个 formula 的 `url` 与 `sha256` 同样由该工作流在每次发版时自动更新，无需手动维护。
