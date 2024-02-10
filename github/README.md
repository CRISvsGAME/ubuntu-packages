# CRISvsGAME

## Ubuntu 22.04

### Github Config

```
read -p "Enter your GitHub name: " GITHUB_NAME
read -p "Enter your GitHub email: " GITHUB_EMAIL
SSH_PATH="$HOME/.ssh/github"
SSH_CONF="$HOME/.ssh/config"
SSH_INFO="Host github.com
    Hostname github.com
    IdentityFile $SSH_PATH"
if [ -f "$SSH_PATH" ] && [ -f "$SSH_PATH.pub" ]; then
    echo "SSH keys already exist"
else
    mkdir -p "$HOME/.ssh"
    ssh-keygen -t ed25519 -C "$GITHUB_EMAIL" -N "" -f "$SSH_PATH"
fi
if [ ! -f "$SSH_CONF" ] || ! grep -qF "$SSH_INFO" "$SSH_CONF"; then
    echo "$SSH_INFO" | tee -a "$SSH_CONF"
else
    echo "SSH config already exists"
fi
git config --global init.defaultBranch main
git config --global user.email "$GITHUB_EMAIL"
git config --global user.name "$GITHUB_NAME"
```
