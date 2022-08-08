- 安装ufw命令
```
# apt-get install ufw
```
检查防火墙的状态（默认 inactive）  # ufw status

防火墙版本                                        # ufw version

启动ufw防火墙                                  #  ufw enable

关闭ufw防火墙                                 #  ufw  disable

默认禁止访问所有                             #  ufw default deny

开放22/TCP端口                               #  ufw allow 22/tcp

开放53端口(tcp/udp)                         #  ufw allow 53

禁止外部访问                                    #  ufw deny 3306

删除已经添加过的规则                      #  ufw delete allow 22

允许此IP访问所有的本机端口           #   ufw allow from 192.168.1.100

删除上面的规则                                #    ufw delete allow from 192.168.1.100
