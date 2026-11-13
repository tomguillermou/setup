# Setup

## 1. Install

```sh
brew install --cask ghostty
brew install starship zsh-autosuggestions zsh-syntax-highlighting
```

## 2. Ghostty

```sh
mkdir -p ~/.config/ghostty
cat > ~/.config/ghostty/config << 'EOF'
keybind = cmd+z=text:\x1f
keybind = cmd+shift+z=text:\x18\x1f
keybind = alt+up=text:\x1b[1;3A
keybind = alt+down=text:\x1b[1;3B
unfocused-split-opacity = 0.5
unfocused-split-fill = #1e2127
window-save-state = always
EOF
```

## 3. zsh

```sh
cat > ~/.zshrc << 'EOF'
alias ga="git add -A"
alias gco="git checkout"
alias gcb="git checkout -b"
alias gl="git pull"
alias gp="git push"
alias gpf="git push --force-with-lease"
alias gc="git commit -m"
alias gs="git status"
alias gstu="git stash --include-untracked"

source /opt/homebrew/share/zsh-autosuggestions/zsh-autosuggestions.zsh

bindkey '^_' undo
bindkey '^X^_' redo
bindkey '^[[1;3A' up-history
bindkey '^[[1;3B' down-history

eval "$(starship init zsh)"

source /opt/homebrew/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh
EOF
```

## 4. Starship

```sh
mkdir -p ~/.config
cat > ~/.config/starship.toml << 'EOF'
[python]
disabled = true

[git_status]
disabled = true

[gcloud]
disabled = true
EOF
```
