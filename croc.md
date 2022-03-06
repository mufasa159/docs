
To send a file:  
```croc send <filepath>```
  
To recieve a file:  
```croc <code-phrase>```  
  
Send with Custom code phrase:  
```croc send --code <code-phrase> <filepath>```  
  
Allow overwriting without prompt:  
```croc --yes --overwrite <code>```  
  

Using pipes (stdin, stdout):  
```cat <filename> | croc send```  
  
In this case `croc` will automatically use the stdin data and send and assign a filename like "croc-stdin-123456789". To receive to `stdout` at you can always just use the `--yes` will automatically approve the transfer and pipe it out to `stdout`.

  
Send text:  
```croc send --text "hello world"```  
  
Change encryption curve:  
```croc --curve p521 <codephrase>```  
  
Self host relay:  
```
croc relay  
croc --relay "myrelay.example.com:9009" send [filename]   

// With docker    
docker run -d -p 9009-9013:9009-9013 -e CROC_PASS='YOURPASSWORD' schollz/croc  
croc --pass YOURPASSWORD --relay "myreal.example.com:9009" send [filename]   
```