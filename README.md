# HACKINTOSH-OPENCORE

## 硬件配置

| 配置   | 型号                                         |
| ------ | -------------------------------------------- |
| CPU    | Intel Core i5-10500                          |
| 主板   | MSI B460M MORTAR 迫击炮                      |
| 内存   | G.Skill 2666 8G\*2                           |
| 硬盘   | HP SSD EX950 1TB                             |
| 显卡   | AMD Radeon RX 5500 XT                        |
| 显示器 | ViewSonic VSC7338 VX2478-4K-HD ( 23.6 英寸 ) |
| 网卡   | BCM94360CS2                                  |

## BIOS 设置

- USB 设备从 S3/S4/S5 唤醒：允许
- PS/2 鼠标从 S3/S4/S5 唤醒：允许
- USB 键盘从 S3/S4/S5 唤醒：任意键
- 集成显卡多显示器：允许
- OC -> CPU 特征 -> Intel 虚拟化技术：允许
- OC -> CPU 特征 -> Intel VT-D 技术：禁止
- OC -> CPU 特征 -> CFG 锁定：禁止

## EFI

OpenCore: 0.6.4

macOS Big Sur 11.0.1 (注意: 安装系统时分区格式选择 APFS, 而不是 MacOS 扩展日志式)

> PS: 本次 EFI 升级为正式版，非图形界面直接选择 Reset NVRAM 选项，图形界面在选择启动盘时按空格，再选中 Reset NVRAM 选项，(回车键)重置 NVRAM，重置后可能需要在 BIOS 中重新设置磁盘启动优先顺序

若使用 4K 显示器，请将 "UIScale" 的值修改为 "Ag==" 以获得最佳 ui 体验

```xml
<key>UIScale</key>
<data>Ag==</data>
```

## 板载网卡设置

系统偏好设置 -> 网络 -> 以太网（高级） -> 硬件 -> 配置:手动, 速度:100baseTX(千兆网络环境可选择 1000baseT), 双工:全双工, MTU:标准 1500

## 设置默认启动项

在启动选择界面，先选中要启动的项，然后按键盘的 Ctrl + Enter (回车键) 进入系统，下次重启后默认就选中该项了

## 隐藏磁盘

```bash
sudo vim /etc/fstab

UUID=<UUID> none ntfs rw,noauto
UUID=<UUID> none msdos rw,noauto
```

## 软件

- [Hackintool](https://github.com/headkaze/Hackintool)
- [ProperTree](https://github.com/corpnewt/ProperTree)

## 资料

- [https://github.com/myqqiu/Hackintosh-B460M-MORTAR-i5-10500-iGPU-UHD630](https://github.com/myqqiu/Hackintosh-B460M-MORTAR-i5-10500-iGPU-UHD630)

- [Xjn´s Blog](https://blog.xjn819.com/)
