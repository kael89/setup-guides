# Setting up a MacOS dev environment

## OS configuration

### Keyboard

1. Go to **Preferences -> Keyboard -> Shortcuts** tab, and select "Use keyboard navigation to move focus between controls"
2. If using a non-Mac keyboard:

   - System **Preferences -> Keybboard -> Modifier Keys** button
   - Select your keyboard from the list
   - Swap the **Option** and **Command** keys

### Window Management

Install **[Rectangle](https://rectangleapp.com/)**: `brew install --cask rectangle`

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

## JavaScript/TypeScript

1. Install **[nvm](https://github.com/nvm-sh/nvm#installing-and-updating)** for managing node versions
2. Use `nvm` to nstall a node version of your choice, eg `nvm install 12`. This will also install `npm`
3. Install **[yarn](https://classic.yarnpkg.com/lang/en/docs/install/#mac-stable)**: `npm install --global yarn`
