# CRISvsGAME

## Ubuntu 22.04

### Docker Config

```
sudo apt update
sudo apt upgrade
sudo apt install curl gpg
G_PATH="/etc/apt/trusted.gpg.d/docker.gpg"
R_PATH="/etc/apt/sources.list.d/docker.list"
R_LINK="https://download.docker.com/linux/ubuntu"
G_KEYS="https://download.docker.com/linux/ubuntu/gpg"
R_INFO="deb [arch=$(dpkg --print-architecture) \
signed-by=$G_PATH] $R_LINK \
$(. /etc/os-release && echo "$VERSION_CODENAME") stable"
curl -fsLS "$G_KEYS" | sudo gpg --dearmor -o "$G_PATH"
echo "$R_INFO" | sudo tee "$R_PATH" >/dev/null
sudo apt update
sudo apt upgrade
sudo apt install docker-ce docker-ce-cli containerd.io \
    docker-buildx-plugin docker-compose-plugin
sudo groupadd docker
sudo usermod -aG docker "$(whoami)"
newgrp docker
```
