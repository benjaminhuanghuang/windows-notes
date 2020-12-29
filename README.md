# Windows Subsystem for Linux (WSL)

Windows Subsystem for Linux is an optional feature of `Windows 10` that runs a Linux kernel inside a small `virtual machine`, allowing your Windows computer to run Linux tools and programs right alongside Windows itself

## WSL 1, WSL2

WSL 1 translates Linux system calls to NT kernek, share host's IP

WSL 2 run Linux kernel in small Hyper-V vm, called the utility vm. Requires virtualization. get DHCP adderss from the Hypuer-V virtual network.

## WSL kernel
- build from Linux kernal
- updates come through Windows Update
- open source


## Setup
- Enable Widnows Subsystem for Linux
  - through GUI: Windiws Features
  - power shell (admin)
  ```
    Enable-WidnowsOptionalFreature -Online -FeatureName VirtualMachinePlatform (Win 10 Home)
    Enable-WidnowsOptionalFreature -Online -FeatureName Microsoft-Hyper-V (Win 10 Pro)

    Enable-WidnowsOptionalFreature -Online -FeatureName Microsoft-Windows-Subsystem-Linux


  ```
- Install a distro
  - Install from MS Store
  - Install using PowserShell
  each windows user will need to download their own distro
  






