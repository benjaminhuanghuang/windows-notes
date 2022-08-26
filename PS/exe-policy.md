## Policy:
    
- Restricted 

- AllSigned 

- RemoteSigned 

- Unrestricted 

- Bypass 

- Undefined


## Scopes：
- Process
- CurrentUser 
- LocalMachine



```
# show current policy
Get-ExecutionPolicy -List


# Set policy for current user 要求所有脚本签名
Set-ExecutionPolicy -Scope CurrentUser AllSigned


# 临时使用，不想修改执行策略为较低的权限
Set-ExecutionPolicy Bypass -Scope Process -Force; <script>


# Developer频繁使用powershell脚本，运行本地脚本运行
Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
```