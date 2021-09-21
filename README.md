# Dell-Optilex-9020m-Hackintosh

## 详细配置信息

|   规格   |                 详细信息                  |
| :------: | :---------------------------------------: |
| 电脑信息 |            Dell OptiPlex 9020m            |
|    OS    |           macOS Big Sur 11.5.2            |
|  处理器  |           Intel Core™ i5-4690t            |
|   内存   | SKHynix 4GB * 2 DDR3 Dual Channel 1600MHz |
|   存储   |  SKHynix HFS256G39TNH-73A0A mSATA 256GB   |
|   显卡   |          Intel HD Graphics 4600           |
|  显示器  |                 某东杂牌                  |
|   声卡   |              Realtek ALC235               |
|   网卡   |         Broadcom BCM943224PCIEBT2         |

## 特性

- 仿冒机型：`Macmini7,1` （S/N已去除防止冲突，请自行生成）
- 显卡注入，参考黑果小兵[(@daliansky)](https://github.com/daliansky/Dell-OptiPlex-9020M-Hackintosh)项目的EFI，替换生成，本机在开机时会黑屏一下，推测是DP转HDMI所致
- 使用[USBToolBox](https://github.com/USBToolBox/tool)进行USB定制，确保端口可用，原EFI在macOS11.3以上版本USB可能会出现问题，定制后可能有一个端口只能识别USB2.0，懒得修了
- 蓝牙正常；隔空投送、接力正常；Wi-Fi正常，针对 `BCM943224PCIEBT2` 进行修改，确保可用
- EC正常、开机音效支持、电源按钮功能正常 

## BIOS设置（版本：A19）

- 恢复出产设置：`Load Defaults`
- 关闭`VT-d` 
- 关闭`CFG LOCK` ：在`GRUB SHELL` 中输入`setup_var 0xD9F 0x0`（感谢[@chencaidy](https://github.com/chencaidy)）
- 设置`64M` 预分配现存：在 `GRUB SHELL` 中输入 `setup_var 0x263 0x2` 
- 安全启动`Secure Boot` 设置为`Disable`
- ATA设备菜单：配置`SATA` 为`AHCI` 
- 其他保持默认

## 更新日志

- 2021-09-21
  - `Opencore`版本 `v0.7.3` 
  - 精简不必要驱动 简化结构
  - 更新 `AirportBrcmFixup`至`2.1.3` 
  - 更新 `AppleALC` 至  `1.6.4` 
  - 更新 `IntelMausiEthernet` 至 `1.0.7` 
  - 更新 `Lilu` 至 `1.5.6` 
  - 更新 `VirtualSMC` 至 `1.2.7` 
  - 更新 `WhateverGreen` 至 `1.5.3`   

## 屏幕截图

![1](https://github.com/Misumimikoto/dell-optiplex-9020m-hackintosh/blob/master/1.png)

![2](https://github.com/Misumimikoto/dell-optiplex-9020m-hackintosh/blob/master/2.png)

![3](https://github.com/Misumimikoto/dell-optiplex-9020m-hackintosh/blob/master/3.png)

## 致谢

- [@daliansky](https://github.com/daliansky)
- [@chencaidy](https://github.com/chencaidy)
- [@USBToolBox](https://github.com/USBToolBox)

