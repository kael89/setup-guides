# Setting up a MacOS dev environment

## Packet manager

Install [brew](https://brew.sh/)

## OS configuration

### Keyboard

1. Go to **Preferences -> Keyboard** tab, and enable "Keyboard navigation"
2. If using a non-Mac keyboard:

   - System **Preferences -> Keyboard -> Modifier Keys** button
   - Select your keyboard from the list
   - Swap the **Option** and **Command** keys

### Window Management

Install [Rectangle](https://rectangleapp.com/): `brew install --cask rectangle`

### Clipboard manager

1. Install [Clipy](https://github.com/Clipy/Clipy): `brew install --cask clipy`
2. Open Clipy, go to **Preferences -> Menu** and change the settings as follows:

   - **Number of items place _(sic)_ inline:** 10
   - **Number of characters in the menu:** 40

## Monospace font

Install [Fira Code](https://github.com/tonsky/FiraCode) and its [Nerd Font version](https://github.com/ryanoasis/nerd-fonts/tree/master/patched-fonts/FiraCode):

```bash
brew install --cask font-fira-code --cask font-fira-code-nerd-font
```

## Terminal

### Terminal app

1. Install [iTerm2](https://iterm2.com/): `brew install --cask iterm2`
2. Open iTerm2, go to **Preferences -> Profiles** and edit the default profile as follows:
   - **Text → Font**: FiraCode Nerd Font
   - **Terminal → Scrollback lines**: 5,000
   - **Keys → Key Mappings -> Presets**: Natural Text Editing
3. (Optional) Change the font for Terminal (MacOS default) to FiraCode Nerd Font

### Shell

1. [zsh](https://www.zsh.org/) should be the default shell in newer MacOS versions. Follow [these steps](https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH#macos) if this is not the case
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

1. `brew install --cask intellij-idea-ce`
2. **File -> Manage IDE Settings -> Settings Sync...** and Enable Settings Sync
3. Restart the app to enable plugins

### Visual Studio Code

1. Install [VSCode](https://code.visualstudio.com/): `choco install vscode`
2. Turn on Settings Sync:

   - Open the app and go to **Code -> Settings -> Back up and sync settings**
   - Sign in using your GitHub account
   - If you are syncing a new machine and are prompted to merge/replace your settings, you can use "Replace Local"

   Note: with the exception of keybindings, VSCode does not support [platform-specific settings](https://github.com/microsoft/vscode/issues/5595) yet. We have excluded some settings from syncing to avoid cross-platform conflicts. We have to manually set those in our machine:

   - **Editor: Font Family:** add `'Fira Code'` at the start of the list
   - **Terminal > Integrated: Font Family:** `'FiraCode Nerd Font'`

## Programming Languages

## JavaScript/TypeScript

1. Install [nvm](https://github.com/nvm-sh/nvm#installing-and-updating) for managing node versions
2. Use `nvm` to install a node version of your choice, e.g. `nvm install 22`. This will also install `npm`
3. Install [yarn](https://classic.yarnpkg.com/lang/en/docs/install/#mac-stable): `npm install --global yarn`

## Java

1. Install **Java 21** (Amazon Corretto): `brew install --cask corretto@21`
2. Install `jenv` to manage Java versions: `brew install jenv`
3. Add Java 21 to your jenv versions: `jenv add /Library/Java/JavaVirtualMachines/amazon-corretto-21.jdk/Contents/Home`
