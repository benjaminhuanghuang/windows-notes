
Windows Terminal opens up with a tab running PowerShell

Window terminal can be used for cmd.exe, PowerShell, WSL shell

## Open the linux
- Use the distro shell directly in cmd.exe
```
  bash
  exit
```

- Use wsl.exe
```
  wsl -l -v                           # list all distro

  wsl --set-version Ubuntu-20.04 2    # set wsl 2

  # set wsl 2 to all distro, need to enable cpu virtualization in BIOS and enable VM platform feature
  wsl --set-default-version 2         

  dir c: | wsl wc -l                  # windows command > linux command


  wsl --set-default Ubuntu-20.04      # set default distro
  wsl -d Ubuntu-20.04                 # run specify distro
  wsl.exe -d MyDebian ls -l ~         # run command in distro 

  wsl --export <dictro> .\Desktop\ubuntu.tar
  wsl --import Ubun02 .\Desktop\Ubun-2 .\Desktop\ubuntu.tar
```

## Run windows exe in Linux
```
  Notepad.exe readme.txt
```


