# 🍎 Mac Dev Setup — Dotfiles

> Setting up a fresh Mac for development shouldn’t take a whole weekend. Here’s the shortcut.

## Welcome

I’m Tobias, and these are my personal dotfiles and setup scripts. The idea: make it super easy to get a new Mac ready for work. Clean terminal, sharp CLI tools, and just enough opinionated defaults to keep things sane. If you care about speed, clarity, and not having to Google “how to install Homebrew” for the fifteenth time, you’ll probably like this.

## Quick Start

Copy, paste, and run top to bottom:

```bash
# Clone the repo
cd ~ && git clone https://github.com/<your-username>/dotfiles ~/.dotfiles && cd ~/.dotfiles

# Get Xcode CLI tools (safe to re-run)
xcode-select --install 2>/dev/null || true

# Install Homebrew (if missing)
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Install tools & apps via Brewfile
brew bundle

# Apply macOS defaults (asks for sudo, restarts a few things)
./setup-macos.sh

# Set up zsh config (symlink)
./setup-zsh.sh

# Optional: Mac App Store apps (sign in first)
./install-mac-apps.sh
```

Open a new terminal. Enjoy your new prompt and aliases. Update App Store apps later with `./update-mac-apps.sh`.

## What’s Included

- **Terminal:** zsh, powerlevel10k, autosuggestions, completions, fzf-tab, syntax highlighting
- **CLI tools:** eza, fzf, zoxide, bat, delta, gh, lazygit, neovim, bun, pnpm, fnm, uv
- **Apps:** iTerm2, VS Code, Zed, Docker, Raycast, Figma, TablePlus, Chrome, and friends
- **Mac App Store picks:** Dropover, Klack, ColorSlurp, Spark, Command X, Noir, Refined GitHub, Perplexity, etc.
- **Extras:** Quick Look plugins (JSON/Markdown), dev fonts (Hack Nerd Font, Lato), sensible macOS defaults
- **Git:** delta pager, 3-way merge, comfort tweaks

## Guided Setup

- Install Command Line Tools: `xcode-select --install`
- Install Homebrew, then `brew bundle` from repo root
- Apply macOS defaults: `./setup-macos.sh` (needs sudo; some changes require logout/restart)
- Link shell config: `./setup-zsh.sh` (symlinks `~/.zshrc`)
- Mac App Store apps: sign in, then `./install-mac-apps.sh`
- Keep MAS apps fresh: `./update-mac-apps.sh`

## iTerm2 Profile

Import settings from `iterm/com.googlecode.iterm2.plist`:
- iTerm2 → Settings → General → Preferences → “Load preferences from a custom folder or URL” → point to the repo’s `iterm` folder
- Or just import the plist manually

## Verify Your Setup

- Open a new terminal; run `p10k configure` if prompted
- Try aliases: `ls` (eza), `lg` (lazygit), `vim` (nvim)
- Check tools: `fzf`, `zoxide`, `fnm`, `gh`, `bat`, `rg` (if installed separately)

## Make It Yours

- **Packages:** tweak `Brewfile`, run `brew bundle` again (or `brew bundle cleanup` to prune)
- **Shell:** edit `~/.zshrc` and `source ~/.zshrc` or restart your shell
- **Git:** adjust `.gitconfig` for your name, email, and aliases

## FAQ / Tips

- *Brew not found?* Install Homebrew (see step 3), re-open terminal.
- *MAS install fails?* Open App Store, sign in, re-run `./install-mac-apps.sh`.
- Safe to re-run: `brew bundle` and MAS scripts are idempotent.
- Apple Silicon: paths set up for `/opt/homebrew`. Adjust if needed.

## Why This Exists

Because I want to start building, not spend hours hunting for fonts or toggling obscure settings. This repo is my shortcut to “ready to work.” Steal what you like, make it yours.

— Tobias