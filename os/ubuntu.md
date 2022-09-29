# Setting up an Ubuntu dev environment

_Version: Ubuntu 20.04_

## Packet manager

We will use `apt`/`apt-get`, which is installed in Ubuntu by default.

## OS configuration

### Window Management

### Clipboard manager

Install **[CopyQ](https://github.com/hluk/CopyQ#debian-10-ubuntu-1804-and-their-derivatives/)**

## Monospace font

Install **[Fira Code](https://github.com/tonsky/FiraCode)**:

```bash
sudo add-apt-repository universe
sudo apt install fonts-firacode
```

Install **[Fira Code Nerd Font](https://github.com/ryanoasis/nerd-fonts/tree/master/patched-fonts/FiraCode)**:

- Download the font from [this link](https://github.com/ryanoasis/nerd-fonts/releases/latest/download/FiraCode.zip)
- Install `Fira Code Regular Nerd Font Complete.ttf`

## Terminal

### Terminal app

We will use the default Terminal app.

Open Terminal, go to **Preferences -> Profiles** and edit your profile as follows:

- **Text → Custom Font**: Enable and select "FiraCode Nerd Font Regular"

## IDE

### IntelliJ IDEA

1. Install [Jetbrains Toolbox](https://www.jetbrains.com/help/idea/installation-guide.html#6ce14e72)
2. Use the Toolbox to install **IntelliJ IDEA Community Edition**
3. Sync your settings using a repository

   - Open the app and go to **File -> Manage IDE Settings -> Settings Repository**
   - Set the Upstream URL to https://github.com/kael89/intellij-config
   - Click **Merge**

   You may want to adjust the following settings, as there is no way to exclude them from being shared:

   - Font size

4. Plugins are not synced through Settings Repository, so we have to install them manually:

   - Atom Material Icons
   - Material Theme UI
   - VSCode Keymap

### Visual Studio Code

1. Install **[VSCode](https://code.visualstudio.com/docs/setup/linux#_debian-and-ubuntu-based-distributions)**
2. Turn on Settings Sync:

   - Open the app and go to **File -> Preferences -> Turn on Settings Sync...**
   - Sign in using your GitHub account
   - If you are syncing a new machine and are prompted to merge/replace your settings, you can use "Replace Local"

   Note: with the exception of keybindings, VSCode does not support [platform-specific settings](https://github.com/microsoft/vscode/issues/5595) yet. We have excluded some settings from syncing to avoid cross-platform conflicts. We have to manually set those in our machine:

   - **Editor: Font Family:** add `'Fira Code'` at the start of the list
   - **Terminal > Integrated: Font Family:** `'FiraCode Nerd Font'`

## Programming Languages

### JavaScript/TypeScript

1. Install **[nvm](https://github.com/nvm-sh/nvm#installing-and-updating)** for managing node versions
2. Use `nvm` to install a node version of your choice, e.g. `nvm install 16`. This will also install `npm`
3. Install **[yarn](https://classic.yarnpkg.com/lang/en/docs/install/#mac-stable)**: `npm install --global yarn`
