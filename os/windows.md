# Setting up a Windows dev environment

## Packet manager

Install **[Chocolatey](https://docs.chocolatey.org/en-us/choco/setup#installing-chocolatey)**

## OS configuration

### Clipboard manager

1. Install **[CopyQ](https://copyq.readthedocs.io/en/latest/)**: `choco install copyq`
2. Open CopyQ, go to **Preferences** and change the settings as follows:

   - **Shortcuts:** set the shortcut for **Show/hide main window** to `Ctrl + Shift + V`:
   - **Notifications:** change **Maximum width**/**Maximum height** to as desired _(optional)_

### Linux compatibility layer

1. Install [WSL2](https://docs.microsoft.com/en-us/windows/wsl/install)
2. Install the latest [Ubuntu LTS](https://wiki.ubuntu.com/Releases) version from the [Microsoft Store](https://www.microsoft.com/en-au/p/ubuntu-20044-lts/9mttcl66cpxj#activetab=pivot:overviewtab)

## Monospace font

Install **[Fira Code](https://github.com/ryanoasis/nerd-fonts/tree/master/patched-fonts/FiraCode)**: `choco install firacode`

## Terminal

### Terminal app

1. Install **[Windows Terminal](https://docs.microsoft.com/en-us/windows/terminal/)**: `choco install microsoft-windows-terminal`
2. Open the app Settings and select **Open JSON file**. Set the following settings:

   ```jsonc
   {
     "defaultProfile": "{guid_for_your_wsl_profile}",
     "profiles": {
       "defaults": {
         "font": {
           "face": "Fira Code",
           "size": 10
         }
       },
       "list": {
         // You can move/delete profiles in the list
       }
     }
   }
   ```

### Shell

1. Install **[zsh](https://www.zsh.org/)**:

   ```bash
   sudo apt install zsh
   chsh -s $(which zsh)
   ```

2. Install **[oh-my-zsh](https://github.com/ohmyzsh/ohmyzsh#basic-installation)**, a zsh plugin manager
3. Install my custom [oh-my-zsh configuration](https://github.com/kael89/ohmyzsh-config#setup)
4. Install **[Powerlevel10k](https://github.com/romkatv/powerlevel10k#oh-my-zsh)**, an oh-my-zsh theme

## IDE

### Visual Studio Code

1. Install **[VSCode](https://code.visualstudio.com/)**: `choco install vscode`
2. Turn on Settings Sync:

   - Open the app and go to **File -> Preferences -> Turn on Settings Sync...**
   - Sign in using your GitHub account
   - If you are syncing a new machine and are prompted to merge/replace your settings, you can use "Replace Local"

   Note: with the exception of keybindings, VSCode currently does not support [platform-specific settings](https://github.com/microsoft/vscode/issues/5595). Thus, we have to manually update the following settings to [prevent them from syncing](https://code.visualstudio.com/docs/editor/settings-sync#_configuring-synced-data) in our machine:

   - **Editor: Font Family:** add `'Fira Code'` at the start of the list
   - **Terminal > Integrated: Font Family:** `'Fira Code'`
