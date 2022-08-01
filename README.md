# Actions-OpenWrt

[![LICENSE](https://img.shields.io/github/license/mashape/apistatus.svg?style=flat-square&label=LICENSE)](https://github.com/P3TERX/Actions-OpenWrt/blob/main/LICENSE)

This repository contains releases of [X-WRT](https://github.com/x-wrt/x-wrt) for Mi Router 3 (mt7620) | Этот репозиторий содержит релизы [X-WRT](https://github.com/x-wrt/x-wrt) для Mi Router 3 (mt7620)

Guide in English - [how to get ssh access, install X-WRT and so on](https://openwrt.org/toh/xiaomi/mir3#get_sshdropbear_access)

Includes support for PPPoE, WPA3, 3G/4G dongles (e.g. Huawei E3372), USB drives (NTFS, EXT4, exFAT and FAT32 file systems supported) | Включает в себя поддержку PPPoE, WPA3, 3G/4G модемов, USB флешек (NTFS, EXT4, exFAT и FAT32 файловые системы поддерживаются)

Установка:
- Получаем доступ по SSH - [гайд](https://4pda.to/forum/index.php?s=&showtopic=736801&view=findpost&p=49333132)
- Скопировать файлы openwrt-xxx-kernel1.bin и openwrt-xxx-rootfs0.bin на флешку, отформатированную в FAT32. Для удобства можно их переименовать в kernel1.bin и rootfs0.bin. Вставить флешку в роутер.
- В консоли вводим:

nvram set flag_last_success=1

nvram set boot_wait=on

nvram set uart_en=1

nvram commit

cd /extdisks/sda1

mtd write kernel1.bin kernel1

mtd write rootfs0.bin rootfs0

reboot

- Через несколько минут интерфейс будет доступен по адресу 192.168.15.1
- Последующие обновления файлом openwrt-xxx-sysupgrade.bin в интерфейсе во вкладке System -> Backup / Flash Firmware -> Flash new firmware image
- В случае неудачи - [возврат на сток через UART](https://4pda.to/forum/index.php?s=&showtopic=736801&view=findpost&p=50915904).

## Acknowledgments

- [P3TERX/Actions-OpenWrt](https://github.com/P3TERX/Actions-OpenWrt)
- [Aelliari/xwrt_action](https://github.com/Aelliari/xwrt_action)
- [Microsoft Azure](https://azure.microsoft.com)
- [GitHub Actions](https://github.com/features/actions)
- [OpenWrt](https://github.com/openwrt/openwrt)
- [X-WRT](https://github.com/x-wrt/x-wrt)
- [Lean's OpenWrt](https://github.com/coolsnowwolf/lede)
- [tmate](https://github.com/tmate-io/tmate)
- [mxschmitt/action-tmate](https://github.com/mxschmitt/action-tmate)
- [csexton/debugger-action](https://github.com/csexton/debugger-action)
- [Cowtransfer](https://cowtransfer.com)
- [WeTransfer](https://wetransfer.com/)
- [Mikubill/transfer](https://github.com/Mikubill/transfer)
- [softprops/action-gh-release](https://github.com/softprops/action-gh-release)
- [ActionsRML/delete-workflow-runs](https://github.com/ActionsRML/delete-workflow-runs)
- [dev-drprasad/delete-older-releases](https://github.com/dev-drprasad/delete-older-releases)
- [peter-evans/repository-dispatch](https://github.com/peter-evans/repository-dispatch)

## License

[MIT](https://github.com/P3TERX/Actions-OpenWrt/blob/main/LICENSE) © P3TERX
