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

**Note: symlink path must be absolute.**

```
chmod +x server.js
ln /home/yoda/Github/app/services/hello_moto/server.js /app/services/hello_moto/server.js
```

```
ln /home/yoda/Github/etc/systemd/system/hello_moto.service /etc/systemd/system/hello_moto.service
```

## Enable and Start the Service

```
systemctl enable hello_moto.service
```

```
systemctl start hello_moto.service
```

## Troubleshooting
If troublshooting make sure to reload the daemon.

```
systemctl daemon-reload
```

To view all output logs use the following command.

```
sudo journalctl -u hello_moto.service
# For real time logs just add -f argument
sudo journalctl -fu hello_moto.service
```

