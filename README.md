# node-systemd
Challenges...

1. run Node.js services in background
2. automatically restart them if they are crashing
3. collect output/error logs for analyzing them later or watching them in real time.

## SystemD
Handles and processes long running background tasks/services.

*SystemD is an init system.*

## Server.js
Make `server.js` an executable and create a symlink.
```
chmod +x server.js
ln server.js /app/services/hello_moto/server.js
```


```
ln etc/systemd/system/hello_moto.service /etc/systemd/system/hello_moto.service
```
