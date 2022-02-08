# Setting up a MacOS dev environment

## OS configuration

### Keyboard

1. Go to **Preferences -> Keyboard -> Shortcuts** tab, and select "Use keyboard navigation to move focus between controls"
2. If using a non-Mac keyboard:

   - System **Preferences -> Keyboard -> Modifier Keys** button
   - Select your keyboard from the list
   - Swap the **Option** and **Command** keys

### Window Management

Install **[Rectangle](https://rectangleapp.com/)**: `brew install --cask rectangle`

### Clipboard Management

1. Install **[Clipy](https://github.com/Clipy/Clipy)**: `brew install --cask clipy`
2. Open Clipy, go to **Preferences -> Menu** and change the settings as follows:

   - **Number of items place _(sic)_ inline:** 10
   - **Number of characters in the menu:** 40

## Packet Management

Install **[brew](https://brew.sh/)**

## Monospace Font

Install **[Fira Code Nerd Font](https://github.com/ryanoasis/nerd-fonts/tree/master/patched-fonts/FiraCode):**

```bash
brew tap homebrew/cask-fonts
brew install --cask font-fira-code
```

## Terminal

### Terminal app

1. Install **[iTerm2](https://iterm2.com/)**: `brew install --cask iterm2`
2. Open iTerm2 preferences (**iTerm2 → Preferences** or **Cmd + ,**). Select **Profiles** and edit the default profile as follows:
   - **Text → Font**: FiraMono Nerd Font Mono
   - **Terminal → Scrollback lines**: 5,000

### Shell

1. **[zsh](https://www.zsh.org/)** should be the default shell in newer MacOS versions. Follow [these steps]() if this is not the case
2. Install **[oh-my-zsh](https://github.com/ohmyzsh/ohmyzsh#basic-installation)**, a zsh plugin manager
3. Install my custom [oh-my-zsh configuration](https://github.com/kael89/ohmyzsh-config#setup)
4. Install **[Powerlevel10k](https://github.com/romkatv/powerlevel10k#oh-my-zsh)**, an oh-my-zsh theme

## IDE

### Visual Studio Code

1. Run `brew install --cask visual-studio-code` to install VSCode
2. Turn on Settings Sync:

   - Open the app and go to **Code -> Preferences -> Turn on Settings Sync...**
   - Sign in using your GitHub account
   - If you are syncing a new machine and are prompted to merge/replace your settings, you can use "Replace Local"

   Note: with the exception of keybindings, VSCode currently does not support [platform-specific settings](https://github.com/microsoft/vscode/issues/5595). We thus have to manually update the following settings and [prevent them from syncing](https://code.visualstudio.com/docs/editor/settings-sync#_configuring-synced-data) in our MacOS machine:

   - **Editor: Font Family:** add `'FiraMono Nerd Font'` at the start of the list
   - **Terminal > Integrated: Font Family:** `'FiraMono Nerd Font'`

## JavaScript/TypeScript

1. Install **[nvm](https://github.com/nvm-sh/nvm#installing-and-updating)** for managing node versions
2. Use `nvm` to install a node version of your choice, e.g. `nvm install 12`. This will also install `npm`
3. Install **[yarn](https://classic.yarnpkg.com/lang/en/docs/install/#mac-stable)**: `npm install --global yarn`
