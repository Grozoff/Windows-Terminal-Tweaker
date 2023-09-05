# Let's get started!

1. Get Windows Terminal, get PowerShell (not a windows PowerShell) and set it as default:
   - Get Windows Terminal free [from the store](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701?activetab=pivot:overviewtab) or [GitHub releases page](https://github.com/microsoft/terminal/releases)
   - Get PowerShell free [from the store](https://www.microsoft.com/en-us/p/powershell/9mz1snwt0n5d?activetab=pivot:overviewtab)
   - Set it as default in terminal -> Settings -> Startup -> Default profile  
     ![](https://i.imgur.com/H0hskkH.jpeg)
2. ***(OPTIONAL)*** Change Terminal/Console fonts (includes hundreds of special characters that you can use to make your prompt cooler):
   - Download Cascaydia Cove Nerd Fonts [from here](https://www.nerdfonts.com/font-downloads)  
     ![](https://i.imgur.com/g0RQw7G.jpeg)
   - Unpack and install them in the standard way (right click on the font -> install)
   - Change font in PowerShell profile to CascaydiaCove NF: Terminal -> Settings -> Profiles -> PowerShell -> Appearance -> Font face  
     ![](https://i.imgur.com/xIpf83v.jpeg)
3. Install and use "Starship" The minimal, blazing-fast, and infinitely customizable prompt for any shell!:
   - Install [Starship](https://starship.rs/) with command `winget install --id Starship.Starship` and restart shell (terminal) to reload PATH
   - Edit `$PROFILE` and add the following line `Invoke-Expression (&starship init powershell)` and for the changes to take effect, restart the shell.
   - Change default configuration file location with `STARSHIP_CONFIG` environment variable, just add the following line to the `$PROFILE` - `$ENV:STARSHIP_CONFIG = "$HOME\example\non\default\path\starship.toml"`
   - Open configuration file `notepad "$HOME\example\non\default\path\starship.toml"` and insert my configuration `starship.toml` into it.
4. Installing additional features:

   - Installing color [icons](https://github.com/devblackops/Terminal-Icons) in the directory and files listing!
     - Run the command `Install-Module -Name Terminal-Icons -Repository PSGallery` And then add one line to my $PROFILE `Import-Module -Name Terminal-Icons`. Now if you run the command `ls` you will see this  
       ![](https://i.imgur.com/e4sj4Nm.jpeg)

   * [PSReadLine](https://docs.microsoft.com/en-us/powershell/module/psreadline/about/about_psreadline?view=powershell-7.2) provides an improved command-line editing experience in the PowerShell console:

     - Run `Install-Module PSReadLine -AllowPrerelease -Force` and add the following line to $PROFILE `Import-Module PSReadLine`
     - Enable Predictive IntelliSense
       ```
       Set-PSReadLineOption -PredictionSource History
       Set-PSReadLineOption -PredictionViewStyle ListView
       Set-PSReadLineOption -EditMode Windows
       ```

     After saving $PROFILE and restarting the shell, you will have an ANSI-style list with a prediction of what you want to see next and a history of what you have already used.
     ![](https://i.imgur.com/a6RTvXN.png)

   * For easy navigation through the list that we have set above, it is necessary to add the following lines to the $PROFILE

     ```
     Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
     Set-PSReadLineKeyHandler -Key DownArrow -Function HistorySearchForward
     ```

     Use the up and down arrows to navigate through the sheet
---

## My final result

- general user  
   ![](https://i.imgur.com/7i1xczW.png)
- administrator  
   ![](https://i.imgur.com/bETIHzb.png)
