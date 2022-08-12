# Install-Canon-iP1880-in-Monterey
Workaround to make good old Canon iP1880 works in macOS Monterey

![IMG_9317 Small](https://user-images.githubusercontent.com/85201626/184353146-fe88ed5e-e6e9-408c-9e89-de00afde6155.jpeg)![Monterey about this mac_2](https://user-images.githubusercontent.com/85201626/184353932-bb2c5aa0-2045-44e8-98be-f2a6a5c9ebfb.png)



#### Tools and Files required:
  - Tool to unpack pkg files = [unpkg](https://www.macupdate.com/app/mac/16357/unpkg)
  - Finder
  - Terminal
  - Canon iP1900 Driver = [mcpd-mac-ip1900-11_7_1_0-ea17_2.dmg](https://id.canon/id/support/0100563701?model=3021B)
  - Canon iP1880 Driver = [mcpd-mac-ip1800-10_67_2-ea11.dmg](https://id.canon/id/support/0100215301?model=1855B)

#### How to:
1. Install _`mcpd-mac-ip1900-11_7_1_0-ea17_2.dmg`_
2. Open _`mcpd-mac-ip1800-10_67_2-ea11.dmg`_
  - select _`PrinterDriver_iP1800 series_106702.pkg`_ --> right click, open with _`unpkg`_
  - `PrinterDriver_iP1800 series_106702` folder will be put in ~/Desktop
  - Open _that_ folder
3. Using terminal:
  - $ sudo pkgutil --expand-full /Volumes/PrinterDriver_iP1800 series/PrinterDriver_iP1800 series_106702.pkg ~/Desktop/`CANON`
  - Open _that_ folder
4. Copy and paste the folder (and files inside), look at the table...
  - IF file exist, choose to `Replace`, not `Merge`

|**Item**|**From**|**To**|
|---|---|---|
|CFMSupport   |~/Desktop/PrinterDriver_iP1800 series_106702/Library/    |/Users/yourname/Library/CFMSupport|
|Canon   |~/Desktop/PrinterDriver_iP1800 series_106702/Library/Printers/   |/Library/Printers   |
|CanonIJPPD.tgz |~/Desktop/PRINTER/ip1800.pkg/Scripts/PPD/ |/Library/Printers/PPDs/Contents/Resources |

5. Add printer in System Preferences
6. Try to open `Printer Utility` and do some setting
  - System Preferences > Printers & Scanners > Option & Supplies... > Utility > Open Printer Utility
7. Print something
  - IF Print Queue `show a warning` icon and an option to "REPAIR". `Click that!`
8. And you're ready to print... (maybe).

You're welcome.


NOTE:
- IF you use VirtualBox or Parallels, make sure your printer not attached to Guest VM when you want to
print in macOS.
- IF needed, you may want to reset printing system.
![Canon iP1880 reset printing system](https://user-images.githubusercontent.com/85201626/184349715-beb98892-f4cf-437d-980f-9cd475e6244b.png)
