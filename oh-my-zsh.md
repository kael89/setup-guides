# Oh-my-zsh

## Fix performance

oh-my-zsh performance is often degraded because of:

1. Slow plugins
2. Language env managers (`nvm`, `jenv`, `pyenv`)

[Speeding Up My Shell (Oh My Zsh)](https://blog.mattclemente.com/2020/06/26/oh-my-zsh-slow-to-load/#lazy-loading) has an interesting exploration of the topic.

### Analyze performance

1. Add `zmodload zsh/zprof` to the start of ~/.zshrc
2. Run `zprof` to get profiling information. The commands that take longer will be shown in the top - look for self percentage.

This can can be used to detect slow plugins.

### Fix slow env managers

For `nvm` we will use the [nvm](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/nvm) plugin with lazy loading. In `.zshrc`:

- `zstyle ':omz:plugins:nvm' lazy yes` (this should run first)
- `plugins=(... nvm)`
- Make sure that `nvm` is not loaded by any other existing commands (sometimes these are specified in tutorials)

For `jenv`/`pyenv` and similar env managers, we will use the [evalcache](https://github.com/mroth/evalcache) plugin.

1. Install evalcache: `git clone https://github.com/mroth/evalcache ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/evalcache`
2. Edit `~/.zshrc` and

- Add it to the plugins list: `plugins=(... evalcache)`
- Replace `eval` commands with evalcache:

  ```diff
  - eval "$(jenv init -)"
  + _evalcache jenv init -
  ```
