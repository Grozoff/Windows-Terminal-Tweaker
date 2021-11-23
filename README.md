# My setup from Windows Terminal

- Get Windows Terminal, get PowerShell (not a windows PowerShell) and set it as default:
  - Get Windows Terminal free [from the store](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701?activetab=pivot:overviewtab) or [GitHub releases page](https://github.com/microsoft/terminal/releases)
  - Get PowerShell free [from the store](https://www.microsoft.com/en-us/p/powershell/9mz1snwt0n5d?activetab=pivot:overviewtab)
  - Set it as default in terminal -> Settings -> Startup -> Default profile    
 ![](https://i.imgur.com/H0hskkH.jpeg)
- Change Terminal/Console fonts (includes hundreds of special characters that you can use to make your prompt cooler):
  - Download Cascaydia Cove Nerd Fonts [from here](https://www.nerdfonts.com/font-downloads) ![](https://i.imgur.com/g0RQw7G.jpeg)
  - Unpack and install them in the standard way (right click on the font -> install)
  - Change font in PowerShell profile to CascaydiaCove NF: Terminal -> Settings -> Profiles -> PowerShell -> Appearance -> Font face   
![](https://i.imgur.com/xIpf83v.jpeg)
- Install and use [Oh My Posh](https://ohmyposh.dev/docs/) (A prompt theme engine for any shell):
  - Install "Oh My Posh" with command ```winget install JanDeDobbeleer.OhMyPosh``` and restart shell (terminal) to reload PATH
  - Edit $PROFILE ```notepad $PROFILE``` and add the following lines ```Import-Module posh-git``` ```Import-Module oh-my-posh``` and for the changes to take effect, restart the shell.
  - Run the command ```Get-PoshThemes``` and you should see a [list of all available themes](https://github.com/JanDeDobbeleer/oh-my-posh/tree/main/themes). Select the one you like and add the following line to $PROFILE ```Set-PoshPrompt -Theme name``` instead of `name`, enter the name of the topic you like, for example: ```Set-PoshPrompt -Theme ys``` after saving the $PROFILE, don't forget to restart the shell!
- Installing additional features:
  - 
