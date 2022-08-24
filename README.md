# Let's get started!

- Get Windows Terminal, get PowerShell (not a windows PowerShell) and set it as default:
  - Get Windows Terminal free [from the store](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701?activetab=pivot:overviewtab) or [GitHub releases page](https://github.com/microsoft/terminal/releases)
  - Get PowerShell free [from the store](https://www.microsoft.com/en-us/p/powershell/9mz1snwt0n5d?activetab=pivot:overviewtab)
  - Set it as default in terminal -> Settings -> Startup -> Default profile   
 ![](https://i.imgur.com/H0hskkH.jpeg)
- Change Terminal/Console fonts (includes hundreds of special characters that you can use to make your prompt cooler):
  - Download Cascaydia Cove Nerd Fonts [from here](https://www.nerdfonts.com/font-downloads)    
    ![](https://i.imgur.com/g0RQw7G.jpeg)
  - Unpack and install them in the standard way (right click on the font -> install)
  - Change font in PowerShell profile to CascaydiaCove NF: Terminal -> Settings -> Profiles -> PowerShell -> Appearance -> Font face   
![](https://i.imgur.com/xIpf83v.jpeg)
- Install and use "Oh My Posh" (A prompt theme engine for any shell):
  - Install [Oh My Posh](https://ohmyposh.dev/docs/) with command ```winget install JanDeDobbeleer.OhMyPosh -s winget``` and restart shell (terminal) to reload PATH
  - Install [Posh git](https://github.com/dahlbyk/posh-git) with command ```PowerShellGet\Install-Module posh-git -Scope CurrentUser -Force```
  - Edit `$PROFILE` and add the following line ```Import-Module posh-git``` and for the changes to take effect, restart the shell.
  - Run the command ```Get-PoshThemes``` and you should see a [list of all available themes](https://github.com/JanDeDobbeleer/oh-my-posh/tree/main/themes). Select the one you like and add the following line to `$PROFILE` ```oh-my-posh init pwsh --config "$env:POSH_THEMES_PATH\themename.omp.json" | Invoke-Expression``` instead of `themename`, enter the name of the topic you like. After saving the $PROFILE, don't forget to restart the shell!
- Installing additional features:
  -  Installing color [icons](https://github.com/devblackops/Terminal-Icons) in the directory and files listing!
     - Run the command ```Install-Module -Name Terminal-Icons -Repository PSGallery``` And then add one line to my $PROFILE ```Import-Module -Name Terminal-Icons```. Now if you run the command ```ls``` you will see this    
    ![](https://i.imgur.com/e4sj4Nm.jpeg)
  - [PSReadLine](https://docs.microsoft.com/en-us/powershell/module/psreadline/about/about_psreadline?view=powershell-7.2) provides an improved command-line editing experience in the PowerShell console:
    - Run ```Install-Module PSReadLine -AllowPrerelease -Force``` and add the following line to $PROFILE ```Import-Module PSReadLine```
    - Enable Predictive IntelliSense
      ```
      Set-PSReadLineOption -PredictionSource History
      Set-PSReadLineOption -PredictionViewStyle ListView
      Set-PSReadLineOption -EditMode Windows
      ```

      After saving $PROFILE and restarting the shell, you will have an ANSI-style list with a prediction of what you want to see next and a history of what you have already used.
      ![](https://i.imgur.com/rTPBe89.jpeg)
    - For easy navigation through the list that we have set above, it is necessary to add the following lines to the $PROFILE 

      ```
      Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
      Set-PSReadLineKeyHandler -Key DownArrow -Function HistorySearchForward
      ```

      Use the up and down arrows to navigate through the sheet

-------

## Preview my themes

- gsv    
    ![](https://i.imgur.com/fZRUhGZ.jpeg)   
- gs    
    ![](https://i.imgur.com/ydMb38X.jpeg)   
- gs-lite    
    ![](https://i.imgur.com/4moIPn2.jpeg)    
    P.S. I use it in a terminal that is running in VSCode, because some characters are displayed incorrectly there. Proof:   
    ![](https://i.imgur.com/zKeNl7r.jpeg)
