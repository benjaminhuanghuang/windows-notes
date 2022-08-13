# Use PSReadLine
https://github.com/PowerShell/PSReadLine

- How to set up an awesome prompt with your Git Branch, Windows Terminal, PowerShell, + Cascadia Code!

    https://www.youtube.com/watch?v=lu__oGZVT98 

- Tips & Tricks #1 : How to enable Bash style auto suggestion for PowerShell
    
    https://www.youtube.com/watch?v=I0iIZe0dUNw



Install PSReadLine
```
    Install-Module PSReadLine -AllowPrerelease -Force
```

Modify C:\Users\<myname>\Documents\PowerShell\Microsoft.PowerShell_profile.ps1
```
    code $PROFILE
```

paste code into PowerShell_profile.ps1
```
Import-Module PSReadLine

# Shows navigable menu of all options when hitting Tab
Set-PSReadLineKeyHandler -Key Tab -Function MenuComplete

# Autocompleteion for Arrow keys
Set-PSReadLineOption -HistorySearchCursorMovesToEnd
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
Set-PSReadLineKeyHandler -Key DownArrow -Function HistorySearchForward

Set-PSReadLineOption -ShowToolTips
Set-PSReadLineOption -PredictionSource History
```