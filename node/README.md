# CRISvsGAME

## Ubuntu 22.04

### Node Config

```
sudo apt update
sudo apt upgrade
sudo apt install curl gpg
G_PATH="/etc/apt/trusted.gpg.d/node.gpg"
R_PATH="/etc/apt/sources.list.d/node.list"
R_LINK="https://deb.nodesource.com/node_20.x"
G_KEYS="https://deb.nodesource.com/gpgkey/nodesource-repo.gpg.key"
R_INFO="deb [signed-by=$G_PATH] $R_LINK nodistro main"
curl -fsLS "$G_KEYS" | sudo gpg --dearmor -o "$G_PATH"
echo "$R_INFO" | sudo tee "$R_PATH" >/dev/null
sudo apt update
sudo apt upgrade
sudo apt install nodejs
```
