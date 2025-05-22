# Setting up a MacOS dev environment

## Packet manager

Install [brew](https://brew.sh/)

## OS configuration

### Keyboard

1. Open **System Settings** and go to **Keyboard**
1. Enable "Keyboard navigation" to allow switching between menu options using the keyboard
1. If using a non-Mac keyboard:

   - Search for **Modifier Keys** in System Settings
   - Select your keyboard from the list
   - Swap the **Option** and **Command** keys

### Trackpad

1. Open **System Settings** and go to **Trackpad**
2. Enable "Tap to click"
3. Go to the **Scroll & Zoom** and disable "Natural Scrolling"

### Window Management

1. Install [Rectangle](https://rectangleapp.com/): `brew install --cask rectangle`
2. Go to **Settings -> settings tab (3rd tab)** and enable:
   - Launch on login
   - Hide menu bar icon

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
   - **Text**
     - Font: FiraCode Nerd Font
     - Enable "Use ligatures"
   - **Terminal**
     - Scrollback lines: 5,000
   - **Keys**
     - Key Mappings -> Presets: Natural Text Editing
3. (Optional) Change the font for Terminal (MacOS default) to FiraCode Nerd Font

### Shell

1. [zsh](https://www.zsh.org/) should be the default shell in newer MacOS versions. Follow [these steps](https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH#macos) if this is not the case
2. Install [oh-my-zsh](https://github.com/ohmyzsh/ohmyzsh#basic-installation), a zsh plugin manager
3. Install my custom [oh-my-zsh configuration](https://github.com/kael89/ohmyzsh-config#setup)
4. Install [Powerlevel10k](https://github.com/romkatv/powerlevel10k#oh-my-zsh), an oh-my-zsh theme.

   A configuration wizard will appear in your terminal after installing Powerlevel10k. Suggested settings:

   - **Prompt style:** Rainbow
   - **Character set:** Unicode
   - **Show current time?** 24-hour format
   - **Prompt Separators:** Angled
   - **Prompt Heads:** Sharp
   - **Prompt Tails:** Flat
   - **Prompt Height:** One line
   - **Prompt Spacing:** Compact
   - **Prompt Flow:** Concise
   - **Enable Transient Prompt?** Yes
   - **Instant Prompt Mode:** Verbose

5. Install the following plugins: `zsh-autocomplete`, `zsh-autosuggestions`, `zsh-syntax-highlighting`

   ```
   git clone --depth 1 -- https://github.com/marlonrichert/zsh-autocomplete.git $ZSH_CUSTOM/plugins/zsh-autocomplete
   git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions
   git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
   ```

6. Edit `~/.zshrc` and set the list of plugins:

   ```bash
   # zsh-syntax-highlighting must be last in the list
   plugins=(git zsh-autocomplete zsh-autosuggestions zsh-syntax-highlighting)
   ```

### Utilities

#### bat

Install using these [instructions](https://github.com/sharkdp/bat?tab=readme-ov-file#on-macos-or-linux-via-homebrew). You can then optionally add the following to `~/.zshrc` to replace `cat` with `bat`:

```
alias cat="bat"
```

#### nano

Recent versions of MacOS symlink nano to pico, so we need to install it using

```
brew install nano
```

See [scopatz/nanorc](https://github.com/scopatz/nanorc) for improved syntax highlighting.

## VCS

See [git.md](../git.md)

## IDEs

### IntelliJ IDEA

1. `brew install --cask intellij-idea-ce`
2. **Settings -> Backup and Sync -> Login in with Jetbrains Account...**
3. Restart the app to enable plugins

### Visual Studio Code

1. Install [VSCode](https://code.visualstudio.com/): `brew install --cask visual-studio-code`
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
2. Install `jenv` to manage Java versions: `brew install jenv`. Update `.zshrc` as per the installation instructions
3. Add Java 21 to your jenv versions: `jenv add /Library/Java/JavaVirtualMachines/amazon-corretto-21.jdk/Contents/Home`
