## Software Dev

### Mac OSX

Check which ports are currently being used:  
`sudo lsof -P -i TCP -s TCP:LISTE`

Services currently running:  
`brew services list`  

Kill localhost process  
`sudo lsof -i :8000`  
`kill -9 INSERT-PID-HERE`

