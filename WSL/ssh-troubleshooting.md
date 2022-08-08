
Fix `kex_exchange_identification: read: Connection reset`

```
netsh interface portproxy add v4tov4 listenaddress=0.0.0.0 listenport=2222 connectaddress=127.0.0.1 connectport=2222

netsh interface portproxy add v4tov4 listenaddress=0.0.0.0 listenport=2222 connectaddress=localhost connectport=2222


netsh interface portproxy show all

netsh interface portproxy delete v4tov4 listenport=2222 listenaddress=0.0.0.0
```

Fix `kex_exchange_identification: Connection closed by remote host`
```
```

Fix `ssh: connect to host 172.29.149.140 port 2222: Connection refused`
```
# check ssh service status
sudo service ssh status

# check configration of the port
grep Port /etc/ssh/sshd_config
```