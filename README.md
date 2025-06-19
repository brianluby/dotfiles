# Dotfiles

These dotfiles are managed with [chezmoi](https://www.chezmoi.io/). Use them as a starting point when setting up a new Mac.

## Requirements

- macOS
- [Homebrew](https://brew.sh)
- [chezmoi](https://www.chezmoi.io)
- [oh-my-zsh](https://ohmyz.sh/) (optional)
- [1Password CLI](https://developer.1password.com/docs/cli/) if retrieving secrets

## Initialize chezmoi

1. Install Homebrew if it's not already installed:
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```
2. Install chezmoi with Homebrew:
   ```bash
   brew install chezmoi
   ```
3. Initialize chezmoi pointing at this repository and apply the dotfiles:
   ```bash
   chezmoi init <repository-url>
   chezmoi apply
   ```
   Replace `<repository-url>` with a path to these dotfiles, such as a GitHub SSH URL.

## Customizing oh-my-zsh

1. Install oh-my-zsh if desired:
   ```bash
   sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
   ```
2. Edit `~/.zshrc` (see `dot_zshrc` in this repo) to configure plugins and themes. You can place additional configuration in `~/.oh-my-zsh/custom`.

## Installing Homebrew packages

Use Homebrew to install the tools you need. For example:
```bash
brew install git
brew install --cask 1password
```
This repository includes a `Brewfile` that lists recommended packages and casks.
Run `brew bundle` from the repository directory to install everything in that file.

## Configuring 1Password secret retrieval

1. Install the 1Password CLI (`op`) with Homebrew:
   ```bash
   brew install --cask 1password/tap/1password-cli
   ```
2. Sign in to 1Password using `op signin` and export the session variables.
3. chezmoi can retrieve secrets using the `op` template functions. See the chezmoi documentation for details.


