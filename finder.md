## Dot files

To get rid of the dot-underscore files, the most efficient way is using find from the Unix side of things:  
```
find . -name '._*' -exec ls {} \;
```

Once you’ve verified that you’re only looking at files you want to delete, kill them with:  
```
find . -name '._*' -exec rm -v {} \;
```

And if you have .DS_Store files around that you need to zap as well, then you’d just do:  
```
find . -name '.DS_Store' -exec rm -v {} \;
```

Other way to delete dot files:  
```
dot_clean filepath
```

Delete ._files on Linux or PC:  
```
find . -type f -name '._*' -delete
```

---

## Hidden Files

Show hidden files on finder:  
```
defaults write com.apple.Finder AppleShowAllFiles true
```

Make a folder hidden:   
```
chflags hidden filepath
```  
Note: you can drag the folder into terminal for its filepath

Make a folder unhidden:  
```
chflags nohidden filepath
```

Restart Finder:  
```
killall Finder
```

Delete files with certain extensions:  
```
rm -rf ./*.tmp
```
