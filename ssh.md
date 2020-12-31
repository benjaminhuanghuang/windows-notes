


Enable ssh server in Linux
```
  sudo dpkg-reconfigure openssh-server

  sudo service ssh start

  sudo vi /etc/ssh/sshd_config    # allow usename/password connect

  sudo servie ssh restart
```


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