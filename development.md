## Software Dev

### What's Running in Background?
Services currently running:  
```
brew services list
```  

---
### Something Already Running on A Port? 

Check who's using a port  
```
sudo lsof -i :8000
```
Then kill the process on that port

```
kill -9 INSERT-PID-HERE 

Or

kill -9 $(lsof -t -i:8000)
```

---
### External Disk Being Used by Another Program?
Check who's using the external disk
```
lsof | grep <filepath>
```

