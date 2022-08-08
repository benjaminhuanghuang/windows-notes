
Ubuntu 启用SSH所需设置

```
#设置root的口令（密码），用作后续登陆使用
sudo passwd root

#安装openssh-server
sudo apt remove openssh-server
sudo apt install openssh-client openssh-server

#备份原始的sshd_config
sudo cp /etc/ssh/sshd_config /etc/ssh/sshd_config.bak
sudo cp /etc/ssh/ssh_config /etc/ssh/ssh_config.bak

#使用vim进行编辑，按i进入insert模式
sudo vim /etc/ssh/sshd_config

#在vim中找到对应项并修改，ESC，输入`wq`保存退出：
Port 2222
ListenAddress 0.0.0.0        # 如果需要指定监听的IP则去除最左侧的井号，并配置对应IP，默认即监听PC所有IP
PermitRootLogin no           # 如果你需要用 root 直接登录系统则此处改为 yes
PasswordAuthentication yes    # 将 no 改为 yes 表示使用帐号密码方式登录


sudo service ssh start             #启动SSH服务

sudo service ssh status            #检查状态

sudo systemctl enable ssh          #开机自动启动ssh命令
```