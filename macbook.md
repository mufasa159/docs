### Mails in terminal

| Function     | Commands |
|--------------|----------|
| Delete All   | `d *`      |
|Delete One | `d 1`|
|Read Mail  | Press enter|
|Scroll Msg | Press space|
|Exit       |   `q`|



### Boot on lid open settings

| Function     | Commands |
|--------------|----------|
|disable | `sudo nvram AutoBoot=%00` |
|enable  | `sudo nvram AutoBoot=%03` |



### Remove drop shadow from screenshots
```
defaults write com.apple.screencapture disable-shadow -bool true
killall SystemUIServer
```