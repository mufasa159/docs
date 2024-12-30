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


### LaTeX compile
```
pdflatex <file>.tex      // pdftex
latexmk -pdf <file>.tex  // bibtex and others
```


### Remove local snapshots to free up space
```
tmutil listlocalsnapshots /
```

It should list all local snapshots like the following:

```
com.apple.TimeMachine.2017-12-14-173102
com.apple.TimeMachine.2017-12-14-212356
```

To delete all local snapshots, run the following command:

```
sudo tmutil deletelocalsnapshots 2017-12-14-173102
sudo tmutil deletelocalsnapshots 2017-12-14-212356
```
