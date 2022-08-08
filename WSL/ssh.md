## Enable ssh server in WSL2

1. Install openssh-server in wsl

SSH默认端口是22，但Windows中内置了SSH Server For Windows占用了22端口，因此如果要在WSL中开启SSH Server，必须修改WSL中的默认SSH监听端口

```
  sudo apt-get install openssh-server

  sudo service ssh start

  sudo vim /etc/ssh/sshd_config    
  # Port 2222
  # PasswordAuthentication yes

  sudo service ssh --full-restart   # restart service
```

2. Add portproxy rule
get address in linux
```
  ip addr | grep eth0
```
```
  netsh interface portproxy add v4tov4 listenaddress=0.0.0.0 listenport=2222 connectaddress=172.29.149.140 connectport=2222
```

list all protproxy rules
```
  netsh interface portproxy show v4tov4
```
remove them all 
```
  netsh interface portproxy reset all

  netsh interface portproxy delete v4tov4 listenaddress=0.0.0.0 listenport=2222
```

3. open firewall
```
  netsh advfirewall firewall add rule name="Open Port 2222 for WSL2" dir=in action=allow protocol=TCP localport=2222
``` 
or use GUI
```
  wf.msc
```

## Check ssh status
```
  ps -e | grep ssh        # sshd process

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

## Send file from Windows to linux

Install Putty
```
  pscp -P 22 d:\test.zip ben@192.168.1.80:/mnt/d/download
```