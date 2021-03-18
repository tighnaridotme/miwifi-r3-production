# Actions-OpenWrt

[![LICENSE](https://img.shields.io/github/license/mashape/apistatus.svg?style=flat-square&label=LICENSE)](https://github.com/P3TERX/Actions-OpenWrt/blob/master/LICENSE)
![GitHub Stars](https://img.shields.io/github/stars/P3TERX/Actions-OpenWrt.svg?style=flat-square&label=Stars&logo=github)
![GitHub Forks](https://img.shields.io/github/forks/P3TERX/Actions-OpenWrt.svg?style=flat-square&label=Forks&logo=github)

This repository contains releases of x-wrt for Mi Router 3 (mt7620) | Этот репозиторий содержит релизы x-wrt для Mi Router 3 (mt7620)

Установка:
- Получаем доступ по SSH - [гайд](https://4pda.ru/forum/index.php?s=&showtopic=736801&view=findpost&p=49333132)
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
- Последующие обновления файлом x-wrt-xxx-sysupgrade.bin в интерфейсе во вкладке System -> Backup / Flash Firmware -> Flash new firmware image
- В случае неудачи - [возврат на сток через UART](https://4pda.ru/forum/index.php?s=&showtopic=736801&view=findpost&p=50915904).

Guide in English - [how to get ssh access, install x-wrt and so on](https://openwrt.org/toh/xiaomi/mir3#get_sshdropbear_access)

## Acknowledgments

- [Microsoft Azure](https://azure.microsoft.com)
- [GitHub Actions](https://github.com/features/actions)
- [OpenWrt](https://github.com/openwrt/openwrt)
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
