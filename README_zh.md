# EFI 吾空 X15 8745hs 780m核显 opencore 黑苹果

[English](README.md) | [简体中文](README_zh.md)

## OpenCore版本

[OpenCore 1.0.8](https://github.com/acidanthera/OpenCorePkg)

## 测试过的系统

- macOS Tahoe 26.0
- macOS Tahoe 26.7.3

## 硬件

- 笔记本: 吾空 X15 8745hs (杂牌笔记本)
- CPU: AMD Ryzen 7 8745hs
- 核显: AMD Radeon 780m
- 内存: 2 * 8G 5600mhz ddr5
- 硬盘: 笔记本自带的吾空定制杂牌硬盘512G

## 使用项目

- [nullarc](https://github.com/luuumi-dev/nullarc):提供了780m的核显卡支持

## 测试结果

- 支持Metal 3，但vda不支持
- 笔记本键盘和触控板均正常
- 无线网卡和蓝牙不能使用(我用的是mt7922网卡，折腾了几个mt7922驱动后依然不行，可能是我的网卡有问题)
- hdmi输出有问题
- 音频与麦克风未测试

## 步骤

1. 使用该EFI文件正常引导安装黑苹果
2. 进入黑苹果系统，安装`nullarc`显卡驱动支持,[参考官方文档](https://github.com/luuumi-dev/nullarc#installing)
   先从[release界面](https://github.com/luuumi-dev/nullarc/releases)下载最新`nullarc-v0.4.0-alpha.zip`，解压进入文件夹里运行

```zsh
sudo ./install.sh --windowserver
```

然后根据提示，把用户自动登录打开，并重启2次，之后整个界面就可以通过780m核显进行渲染

## 说明

仅做780m核显的实验性验证目的，细节未充分优化，仅做参考

## 感谢

- [nullarc](https://github.com/luuumi-dev/nullarc)
- [mechrevo-wujie14pro-7840hs-780m-hackintosh-efi](https://github.com/bbbbrt/mechrevo-wujie14pro-7840hs-780m-hackintosh-efi)
