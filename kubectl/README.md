# CRISvsGAME

## Ubuntu 22.04 & Ubuntu 24.04

### Kubectl Config

```
sudo apt update
sudo apt upgrade
sudo apt install curl gpg
G_PATH="/etc/apt/trusted.gpg.d/kubernetes.gpg"
R_PATH="/etc/apt/sources.list.d/kubernetes.list"
R_LINK="https://pkgs.k8s.io/core:/stable:/v1.31/deb/ /"
G_KEYS="https://pkgs.k8s.io/core:/stable:/v1.31/deb/Release.key"
R_INFO="deb [signed-by=$G_PATH] $R_LINK"
curl -fsLS "$G_KEYS" | sudo gpg --dearmor -o "$G_PATH"
echo "$R_INFO" | sudo tee "$R_PATH" >/dev/null
sudo apt update
sudo apt upgrade
sudo apt install kubectl
```
