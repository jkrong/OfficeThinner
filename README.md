# Things You Must Understand Before Using:
Read it twice, please:
请慎重，再读一遍。
https://github.com/goodbest/OfficeThinner/issues/7

# OfficeThinner
Save your disk space with Office 2016 for Mac.
节省安装在你硬盘里的 Office 2016 空间
Nearly 2.9GB HDD/SDD space can be saved.
几乎可以清理出 2.9GB 的空间

![compare](fig_compare.jpg)

## Attention!
注意！
- This script is only for `Office 2016 for Mac`, tested on 
这个脚本仅测试于 Office 2016 for Mac
  - version `15.16 (151105)`
  - version `15.17 (151206)`
  - version `15.18 (160109)`
  - version `15.25 (160817) x64`
  - version `15.29.1(161215) x64`
- Use at your own risk.
若使用本脚本，责任自负
- Read the code before you run.
运行前请阅读一遍代码
- Make sure all the 5 Office Apps are in the same version.
确保5个 Office 组件均为同一个版本。

## Usage
用法
```
sudo bash -c "curl -s https://raw.githubusercontent.com/goodbest/OfficeThinner/master/OfficeThinner.sh | bash"
```
复制上面代码至 Terminial 即可，按提示要求输入密码和单击 Y 即可。
- As Microsoft Office 2016 for Mac is installed with `root` on `/Applications`, you have to run this script with `sudo`.
Office 2016是需要 root 权限的，所以你需要 sudo 这个命令行。
- The backup files are located at `~/Desktop/OfficeThinner`, you can do whatever you like with them if everything is fine.
使用完成后，备份文档位于：桌面\Office Thinner，你可以选择备份也可以删除。
- Everytime after you install Microsoft Office Updates, you may have to re-run this script. 
每次升级后，你可能都需要重新运行一次这个脚本。

## Explain
释义
Some large-sized duplicate files exist in `Word.app`, `Excel.app`, `PowerPoint.app`, `Outlook.app` and `OneNote.app` in Office 2016 for Mac.
一些重复的大文档存在于 Word, Excel,PowerPoint,Outlook,OneNote 里。

It's wasting your precious HDD/SSD space as these files are just 5 duplicate copies in these apps.
这些重复的大文档浪费了你宝贵的硬盘空间。

This script moves the following duplicate files from Excel, PowerPoint, Outlook and OneNote into a backup directory on your desktop (you may later delete them safely), and then soft link neccesary paths back to the real files in Word.app alone.
这个小脚本可以清除这些重复的大文件，并且给你留出一个备份，你可以选择删除或保留。原理很简单，利用 soft link (类似于快捷方式)，所以不必担心出什么问题。不过请参阅上部分，本脚本仅仅测试过以上版本。

- /Contents/Resources/Fonts (<=15.16)
- /Contents/Resources/DFonts (>=15.17)
- /Contents/SharedSupport/Proofing Tools
- ~~/Contents/Frameworks/MicrosoftOffice.framework/Versions/A/Resources~~
