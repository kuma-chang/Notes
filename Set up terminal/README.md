# Set up Terminal

- [Set up Terminal](#set-up-terminal)
  - [Homebrew](#homebrew)
  - [iTerm2](#iterm2)
  - [oh-my-zsh](#oh-my-zsh)
  - [Vim](#vim)
  - [oh-my-posh](#oh-my-posh)

## Homebrew

Link: [Homebrew](https://brew.sh/)

## iTerm2

- Homebrew install

  ```Bash
    brew install --cask iterm2
  ```

- Setting color scheme
  - Launch iTerm2
  - Go to **Settings**
  - Navigate to **Colors** tab
  - Choose **solorized dark** from **Color Presets**

## oh-my-zsh

Link: [oh-my-zsh](https://ohmyz.sh/)

```Bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

- Agnoster Theme
  - Use vim open `.zshrc`
  - set theme `ZSH_THEME="agnoster"`

- Powerline Fonts

  ```Bash
  git clone https://github.com/powerline/fonts.git
  cd fonts
  ./install.sh
  cd ..
  rm -rf fonts
  ```

  - iTerm2 font setting
    - Settings -> Profile -> Text -> Font
    - set to `Meslo LG L DZ For Powerline`
    - VS code terminal font setting
      - Settings -> Features -> Terminal -> Integrated: Font Family
      - set to `Meslo LG L DZ For Powerline`
      - reopen VS code

- Powerlevel10k Theme
  - open iTerm2
  - Install with oh-my-zsh

    ```Bash
    git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
    ```

  - Use vim open `.zshrc`
  - set theme `ZSH_THEME="powerlevel10k/powerlevel10k"`
  - reopen iTerm2
  - Follow Powerlevel10k setting prompt
  - VS code terminal font setting
    - Settings -> Features -> Terminal -> Integrated: Font Family
    - set to `MesloLGS NF`
    - reopen VS code

## Vim

- Vundle
  - Link: [Vundle.vim](https://github.com/VundleVim/Vundle.vim)
  - set up directory

    ```Bash
    mkdir ~/.vim
    mkdir ~/.vim/bundle
    ```

  - Set up Vundle:

    ```Bash
    git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
    ```

  - Configure Plugins:

    Put this at the top of your .vimrc to use Vundle. Remove plugins you don't need, they are for illustration purposes. (see Github page)
  
  - Install Plugins:

    Launch `vim` and run `:PluginInstall`

- Solarized color theme
  - Link: [vim-colors-solarized](https://github.com/altercation/vim-colors-solarized)
  - clone and move

    ```Bash
    git clone git@github.com:altercation/vim-colors-solarized.git
    cd vim-colors-solarized/colors
    mv solarized.vim ~/.vim/colors/
    ```

  - Modify .vimrc

    ```Bash
    syntax enable
    set background=dark
    colorscheme solarized
    ```

## oh-my-posh

- [Install and set up](https://ohmyposh.dev/)
- [Set up fonts](https://blog.danskingdom.com/Update-your-terminal-prompt-and-font-in-Windows-Terminal-and-VS-Code-and-Visual-Studio/)