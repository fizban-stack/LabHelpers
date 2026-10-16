Install Chezmoi and Age(for encryption).
```bash
sudo pacman -S chezmoi age
```

Create Git Repository for Chezmoi config. (Forgejo Web UI)
Initialize Chezmoi and Create Age Encryption Key.
```bash
chezmoi init
chezmoi cd
```
```bash
chezmoi age-keygen | chezmoi age encrypt --passphrase --output key.txt.age
```
Enter a passphrase for the private key.
Create Chezmoi Ignore File.
```bash
printf '%s\n' \
'key.txt.age' \
'.ssh/known_hosts' \
'.ssh/known_hosts.old' \
>> .chezmoiignore
```
Create Scripts to run with Chezmoi. 
This one asks for the passphrase and then syncs the private key.
run_onchange_before_decrypt-private-key.sh.tmpl
```bash
#!/bin/sh

set -eu

KEY="${HOME}/.config/chezmoi/key.txt"

if [ ! -f "${KEY}" ]; then
    mkdir -p "${HOME}/.config/chezmoi"

    chezmoi age decrypt \
        --output "${KEY}" \
        --passphrase \
        "{{ .chezmoi.sourceDir }}/key.txt.age"

    chmod 600 "${KEY}"
fi
```
Create Scripts to add packages to new computer.
run_once_before_10-install-packages.sh.tmpl
```bash
#!/bin/bash
set -e

SOURCE="{{ .chezmoi.sourceDir }}"

if [[ -f "$SOURCE/packages-pacman.txt" ]]; then
    sudo pacman -S --needed --noconfirm \
        $(grep -vE '^\s*(#|$)' "$SOURCE/packages-pacman.txt")
fi

if command -v paru >/dev/null 2>&1 && [[ -f "$SOURCE/packages-aur.txt" ]]; then
    paru -S --needed --noconfirm \
        $(grep -vE '^\s*(#|$)' "$SOURCE/packages-aur.txt")
fi
```
Create Package Manifest Files
```bash
printf '%s\n' \
chromium \
ttf-jetbrains-mono-nerd \
tailscale \
fzf \
zoxide \
eza \
fd \
bat \
tmux \
openai-codex \
obsidian \
dua-cli \
yay \
nautilus \
neovim \
git \
ripgrep \
lazygit \
> packages-pacman.txt
```

```bash
printf '%s\n' \
facelock-bin \
> packages-aur.txt
```
Retrieve Age Public Key and Create Chezmoi Config File.
```bash
chezmoi age decrypt --passphrase ./key.txt.age
```

```bash
exit
```

```toml
encryption = "age"

[age]
    identity = "~/.config/chezmoi/key.txt"
    recipient = "age1ks93xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
```

```bash
chezmoi init --apply
```

Add files to Chezmoi. Change files added to suit your setup.
```bash
chezmoi add -r ~/.config/{hypr,noctalia,alacritty,fish,nvim}
```

```bash
chezmoi add --encrypt -r ~/.ssh
```
Push first commit to repository.
```bash
chezmoi cd;
git add .;
git commit -m "First Commit";
git branch -M main;
git remote add origin ssh://forgejo.wellslabs.org:2222/James/CACHYOS-LT.git;
git push -u origin main
```
Apply Chezmoi Configuration
```bash
chezmoi apply -v
```

