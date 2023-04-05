# Setting up a Windows dev environment

## Packet manager

Install [Chocolatey](https://docs.chocolatey.org/en-us/choco/setup#installing-chocolatey)

## OS configuration

### Window Management

1. Install [Sizer](http://www.brianapps.net/sizer/): `choco install sizer`
2. Follow the instructions in [window-management.md](/shortcuts/window-management.md) to setup the desired shortcuts

### Clipboard manager

1. Install [CopyQ](https://copyq.readthedocs.io/en/latest/): `choco install copyq`
2. Open CopyQ, go to **Preferences** and change the settings as follows:

   - **Shortcuts:** set the shortcut for **Show/hide main window** to `Ctrl + Shift + V`:
   - **Notifications:** change **Maximum width**/**Maximum height** to as desired _(optional)_

### Linux compatibility layer

1. Install [WSL2](https://docs.microsoft.com/en-us/windows/wsl/install)
2. Install the latest [Ubuntu LTS](https://wiki.ubuntu.com/Releases) version from the [Microsoft Store](https://www.microsoft.com/en-au/p/ubuntu-20044-lts/9mttcl66cpxj#activetab=pivot:overviewtab)

## Monospace font

Install [Fira Code](https://github.com/tonsky/FiraCode) and its [Nerd Font version](https://github.com/ryanoasis/nerd-fonts/tree/master/patched-fonts/FiraCode): `choco install firacode firacodenf`

## Terminal

### Terminal app

1. Install [Windows Terminal](https://docs.microsoft.com/en-us/windows/terminal/): `choco install microsoft-windows-terminal`
2. Open the app Settings and select **Open JSON file**. Set the following settings:

   ```jsonc
   {
     "actions": [
       {
         "command": "paste",
         "keys": "ctrl+v"
       },
       {
         "command": "find",
         "keys": "ctrl+shift+f"
       },
       {
         "command": {
           "action": "copy",
           "singleLine": false
         },
         "keys": "ctrl+c"
       },
       {
         "command": {
           "action": "splitPane",
           "split": "auto",
           "splitMode": "duplicate"
         },
         "keys": "alt+shift+d"
       },
       {
         "command": "unbound",
         "keys": "ctrl+shift+w"
       },
       {
         "command": "unbound",
         "keys": "ctrl+shift+v"
       },
       {
         "command": "closePane",
         "keys": "ctrl+w"
       }
     ],
     "defaultProfile": "{guid_for_your_wsl_profile}",
     "profiles": {
       "defaults": {
         "font": {
           "face": "FiraCode NF",
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

1. Install [zsh](https://www.zsh.org/):

   ```bash
   sudo apt install zsh
   chsh -s $(which zsh)
   ```

2. Install [oh-my-zsh](https://github.com/ohmyzsh/ohmyzsh#basic-installation), a zsh plugin manager
3. Install my custom [oh-my-zsh configuration](https://github.com/kael89/ohmyzsh-config#setup)
4. Install [Powerlevel10k](https://github.com/romkatv/powerlevel10k#oh-my-zsh), an oh-my-zsh theme.

   > **Tip:** the first time you open your terminal after installing Powerlevel10k, a configuration wizard will appear. You can go through all the settings at once by pasting the following code: `ynn312111111y1y`. This sets the following:
   >
   > - **Prompt style:** Rainbow
   > - **Character set:** Unicode
   > - **Show current time?** 24-hour format
   > - **Prompt Separators:** Angled
   > - **Prompt Heads:** Sharp
   > - **Prompt Tails:** Flat
   > - **Prompt Height:** One line
   > - **Prompt Spacing:** Compact
   > - **Prompt Flow:** Concise
   > - **Enable Transient Prompt?** Yes
   > - **Instant Prompt Mode:** Verbose

## IDEs

### IntelliJ IDEA

1. Install [Jetbrains Toolbox](https://www.jetbrains.com/help/idea/installation-guide.html#233c6a64)
2. Use the Toolbox to install **IntelliJ IDEA Community Edition**
3. Sync your settings using a repository

   - Open the app and go to **File -> Manage IDE Settings -> Settings Repository**
   - Set the Upstream URL to `https://github.com/kael89/intellij-config`
   - Click **Merge**

   You may want to adjust the following settings, as there is no way to exclude them from being shared:

   - Font size

4. Plugins are not synced through Settings Repository, so we have to install them manually:

   - Atom Material Icons
   - Material Theme UI
   - VSCode Keymap

### Visual Studio Code

1. Install [VSCode](https://code.visualstudio.com/): `choco install vscode`
2. Turn on Settings Sync:

   - Open the app and go to **File -> Preferences -> Turn on Settings Sync...**
   - Sign in using your GitHub account
   - If you are syncing a new machine and are prompted to merge/replace your settings, you can use "Replace Local"

   Note: with the exception of keybindings, VSCode does not support [platform-specific settings](https://github.com/microsoft/vscode/issues/5595) yet. We have excluded some settings from syncing to avoid cross-platform conflicts. We have to manually set those in our machine:

   - **Editor: Font Family:** add `'Fira Code'` at the start of the list
   - **Terminal > Integrated: Font Family:** `'FiraCode NF'`

## Programming Languages

### JavaScript/TypeScript

Under WSL:

1. Install [nvm](https://github.com/nvm-sh/nvm#installing-and-updating) for managing node versions
2. Use `nvm` to install a node version of your choice, e.g. `nvm install 16`. This will also install `npm`
3. Install [yarn](https://classic.yarnpkg.com/lang/en/docs/install/#mac-stable): `npm install --global yarn`

## Tools

- Install [AutoHotkey](https://www.autohotkey.com/)
