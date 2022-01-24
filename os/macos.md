# Setting up a MacOS dev environment

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

### Shell

1. **[zsh](https://www.zsh.org/)** should be the default shell in newer MacOS versions. Follow [these steps]() if this is not the case
2. Install **[oh-my-zsh](https://github.com/ohmyzsh/ohmyzsh#basic-installation)**, a zsh plugin manager
3. Install my custom [oh-my-zsh configuration](https://github.com/kael89/ohmyzsh-config#setup)
4. Install **[Powerlevel10k](https://github.com/romkatv/powerlevel10k#oh-my-zsh)**, an oh-my-zsh theme

## Windows Management

Install **[Rectangle](https://rectangleapp.com/)**: `brew install --cask rectangle`
