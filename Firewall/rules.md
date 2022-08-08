## 允许端口转发
```
  netsh advfirewall firewall add rule name="Open Port 2222 for WSL2" dir=in action=allow protocol=TCP localport=2222


  # 确认配置
  netsh advfirewall firewall show rule name="Open Port 22 for WSL2"

  # Delete rule
  netsh advfirewall firewall delete rule name="Open Port 22 for WSL2"
``` 

## Add proxy
```
  netsh interface portproxy add v4tov4 listenaddress=0.0.0.0 listenport=2222 connectaddress=172.29.153.66 connectport=2222


  netsh int portproxy delete v4tov4 protocol=tcp listenaddress=0.0.0.0 listenport=22
```

## List all protproxy rules
```
  netsh interface portproxy show v4tov4
```

## remove them all 
```


  netsh interface portproxy reset all
```