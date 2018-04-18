# Guake appearance:
Font - DejaVu Sans Mono for Powerline Book 10;

Built-in schemes - Neutron.

# Install beautifull terminall:
1. Install zsh:

   `sudo apt-fast install zsh`

2. Install oh-my-zsh:

   via curl

   `sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"`

   via wget

   `sh -c "$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"`

3. Install Powerlevel9k:

    `git clone https://github.com/bhilburn/powerlevel9k.git ~/.oh-my-zsh/custom/themes/powerlevel9k`

4. Install zsh-syntax-highlighting:

   `git clone https://github.com/zsh-users/zsh-syntax-highlighting.git`

   *Optional:* Run zsh-syntax-highlighting:

   `source ./zsh-syntax-highlighting/zsh-syntax-highlighting.zsh`

5. Install Powerline fonts:

   ```bash
   git clone https://github.com/powerline/fonts.git
   cd fonts
   ./install.sh
   cd ..
   rm -rf fonts
   ```

   or

   ``` bash
   sudo apt-get install fonts-powerline
   ```

   Fontconfig: 

   ``` bash
   cp <pathToFontsRepo>/fontconfig/50-enable-terminess-powerline.conf ~/.config/fontconfig/conf.d
   fc-cache -vf
   ```

6. Install Awesome terminal fonts:

   ``` bash
   git clone https://github.com/gabrielelana/awesome-terminal-fonts.git
   cd awesome-terminal-fonts
   ./install.sh
   ```

   Customize the configuration file `./config/10-symbols.conf` replacing `PragmataPro` with the name of the font you want to use in the terminal.

   ``` bash
   cp ./config/10-symbols.conf ~/.config/fontconfig/conf.d
   ```

   Restart system!!

7. Copy this in .zshrc:

```bash
export DEFAULT_USER="stargrif"
export TERM="xterm-256color"

export ZSH=~/.oh-my-zsh

ZSH_THEME="powerlevel9k/powerlevel9k"
POWERLEVEL9K_MODE="awesome-fontconfig"

source $ZSH/oh-my-zsh.sh

POWERLEVEL9K_FOLDER_ICON="" 
POWERLEVEL9K_HOME_SUB_ICON="$(print_icon "HOME_ICON")"
POWERLEVEL9K_DIR_PATH_SEPARATOR=" $(print_icon "LEFT_SUBSEGMENT_SEPARATOR") "

POWERLEVEL9K_COMMAND_EXECUTION_TIME_THRESHOLD=0

POWERLEVEL9K_DIR_OMIT_FIRST_CHARACTER=true

CUSTOM_POWERLEVEL9K_EDGE_BACKGROUND="006"
CUSTOM_POWERLEVEL9K_EDGE_FOREGROUND="black"

POWERLEVEL9K_CONTEXT_DEFAULT_BACKGROUND="$CUSTOM_POWERLEVEL9K_EDGE_BACKGROUND"
POWERLEVEL9K_CONTEXT_DEFAULT_FOREGROUND="$CUSTOM_POWERLEVEL9K_EDGE_FOREGROUND"
POWERLEVEL9K_CONTEXT_REMOTE_BACKGROUND="$CUSTOM_POWERLEVEL9K_EDGE_BACKGROUND"
POWERLEVEL9K_CONTEXT_REMOTE_FOREGROUND="$CUSTOM_POWERLEVEL9K_EDGE_FOREGROUND"
POWERLEVEL9K_CONTEXT_ROOT_BACKGROUND="$CUSTOM_POWERLEVEL9K_EDGE_BACKGROUND"
POWERLEVEL9K_CONTEXT_ROOT_FOREGROUND="$CUSTOM_POWERLEVEL9K_EDGE_FOREGROUND"

POWERLEVEL9K_DIR_WRITABLE_FORBIDDEN_FOREGROUND="015"

POWERLEVEL9K_TIME_BACKGROUND="$CUSTOM_POWERLEVEL9K_EDGE_BACKGROUND"
POWERLEVEL9K_TIME_FOREGROUND="$CUSTOM_POWERLEVEL9K_EDGE_FOREGROUND"
POWERLEVEL9K_TIME_FORMAT="%D{\uf017 %H:%M}"

POWERLEVEL9K_PROMPT_ON_NEWLINE=true
POWERLEVEL9K_RPROMPT_ON_NEWLINE=true
POWERLEVEL9K_MULTILINE_FIRST_PROMPT_PREFIX=""
POWERLEVEL9K_MULTILINE_LAST_PROMPT_PREFIX="❯ "

POWERLEVEL9K_COMMAND_EXECUTION_TIME_BACKGROUND="012"
POWERLEVEL9K_COMMAND_EXECUTION_TIME_FOREGROUND="$CUSTOM_POWERLEVEL9K_EDGE_FOREGROUND"

POWERLEVEL9K_SHORTEN_STRATEGY="truncate_middle"
POWERLEVEL9K_SHORTEN_DIR_LENGTH=4

POWERLEVEL9K_OS_ICON_BACKGROUND="$CUSTOM_POWERLEVEL9K_EDGE_BACKGROUND"
POWERLEVEL9K_OS_ICON_FOREGROUND="$CUSTOM_POWERLEVEL9K_EDGE_FOREGROUND"

POWERLEVEL9K_ROOT_ICON="\uf069"

POWERLEVEL9K_SSH_ICON="\uf090"

POWERLEVEL9K_LEFT_PROMPT_ELEMENTS=(os_icon root_indicator ssh context dir dir_writable vcs)
POWERLEVEL9K_RIGHT_PROMPT_ELEMENTS=(status command_execution_time time)

POWERLEVEL9K_SHOW_CHANGESET=true
HYPHEN_INSENSITIVE="true"

plugins=(k tig gitfast colored-man colorize command-not-found cp 
         dirhistory autojump sudo zsh-syntax-highlighting)

source ~/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh

ZSH_HIGHLIGHT_HIGHLIGHTERS=(main brackets pattern cursor)
ZSH_HIGHLIGHT_STYLES[cursor]='bold'

ZSH_HIGHLIGHT_STYLES[alias]='fg=green,bold'
ZSH_HIGHLIGHT_STYLES[suffix-alias]='fg=green,bold'
ZSH_HIGHLIGHT_STYLES[builtin]='fg=green,bold'
ZSH_HIGHLIGHT_STYLES[function]='fg=green,bold'
ZSH_HIGHLIGHT_STYLES[command]='fg=green,bold'
ZSH_HIGHLIGHT_STYLES[precommand]='fg=green,bold'
ZSH_HIGHLIGHT_STYLES[hashed-command]='fg=green,bold'
```


