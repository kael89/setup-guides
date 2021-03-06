# Setting up an Ubuntu dev environment

_Version: Ubuntu 20.04_

## Packet manager

We will use `apt`/`apt-get`, which is installed in Ubuntu by default.

## OS configuration

### Window Management

### Clipboard manager

Install **[CopyQ](https://github.com/hluk/CopyQ#debian-10-ubuntu-1804-and-their-derivatives/)**

## Monospace font

Install **[Fira Code](https://github.com/tonsky/FiraCode/wiki/Linux-instructions#ubuntu-zesty-1704-debian-stretch-9-or-newer)**

## IDE

### Visual Studio Code

1. Install **[VSCode](https://code.visualstudio.com/docs/setup/linux#_debian-and-ubuntu-based-distributions)**
2. Turn on Settings Sync:

   - Open the app and go to **File -> Preferences -> Turn on Settings Sync...**
   - Sign in using your GitHub account
   - If you are syncing a new machine and are prompted to merge/replace your settings, you can use "Replace Local"

   Note: with the exception of keybindings, VSCode currently does not support [platform-specific settings](https://github.com/microsoft/vscode/issues/5595). Thus, we have to manually update the following settings to [prevent them from syncing](https://code.visualstudio.com/docs/editor/settings-sync#_configuring-synced-data) in our machine:

   - **Editor: Font Family:** add `'Fira Code'` at the start of the list
   - **Terminal > Integrated: Font Family:** `'Fira Code'`

## JavaScript/TypeScript

1. Install **[nvm](https://github.com/nvm-sh/nvm#installing-and-updating)** for managing node versions
2. Use `nvm` to install a node version of your choice, e.g. `nvm install 16`. This will also install `npm`
3. Install **[yarn](https://classic.yarnpkg.com/lang/en/docs/install/#mac-stable)**: `npm install --global yarn`
