## Enable ssh server in Kali (WSL2)

1. Install openssh-server in wsl
```
  sudo apt-get install openssh-server

  sudo service ssh start

  sudo vi /etc/ssh/sshd_config    # Port 2222, PasswordAuthentication yes

  sudo service ssh --full-restart   # restart service
```

2. add portproxy rull
```
  netsh interface portproxy add v4tov4 listenaddress=0.0.0.0 listenport=2222 connectaddress=172.23.129.80 connectport=2222
```

list all protproxy rules
```
  netsh interface portproxy show v4tov4
```
remove them all 
```
  netsh interface portproxy reset all
```

3. open firewall
```
  netsh advfirewall firewall add rule name="Open Port 2222 for WSL2" dir=in action=allow protocol=TCP localport=2222
``` 
or use GUI
```
  wf.msc
```



## Readhat
```
rpm -qa | grep ssh 可以看到系统中ssh安装包
```

## Enable ssh server in Linux
```
  sudo dpkg-reconfigure openssh-server

  sudo service ssh start

  sudo vi /etc/ssh/sshd_config    # allow usename/password connect

  sudo servie ssh restart
```


<<<<<<< HEAD
## Check ssh status
```
  netstat -ntlp
  如果看到如下内容:
  tcp 0 0 0.0.0.0:22 0.0.0.0:* LISTEN
  这说明sshd已经能够正常工作了,如果利用客户端(SecurCRT,putty等)连接不上,尝试关闭防火墙试试: service iptables stop
```
或者：根据某个端口号或进程名来查

```
  netstat -anp |grep 22
  netstat -anp |grep ssh
  lsof -i :22
```

## SSH into WSL
Port 22 does not work because Windows comes with a built in SSH server.


=======
Enable ssh server on Ubuntu
```
  sudo apt-get install openssh-server

  sudo /etc/init.d/ssh start
  sudo /etc/init.d/ssh stop
  sudo /etc/init.d/ssh restart

  ps -e | grep ssh
```


send file from Windows to linux

Install Putty
```
  pscp -P 22 d:\test.zip ben@192.168.1.80:/mnt/d/download
```
>>>>>>> 263771932612fe299ac5cd37eb996d57daa17f6d
