# CRISvsGAME

## Ubuntu 22.04 & Ubuntu 24.04

### Nginx Config

```
sudo apt update
sudo apt upgrade
sudo apt install curl gpg
G_PATH="/etc/apt/trusted.gpg.d/ondrej.gpg"
R_PATH="/etc/apt/sources.list.d/ondrej-nginx.list"
G_KEYS="https://keyserver.ubuntu.com/pks/lookup?op=get&search=0x"
R_FING="B8DC7E53946656EFBCE4C1DD71DAEAAB4AD4CAB6"
R_LINK="https://ppa.launchpadcontent.net/ondrej/nginx/ubuntu"
R_INFO="deb [signed-by=$G_PATH] $R_LINK \
$(. /etc/os-release && echo "$VERSION_CODENAME") main"
curl -fsLS "$G_KEYS$R_FING" | sudo gpg --dearmor -o "$G_PATH"
echo "$R_INFO" | sudo tee "$R_PATH" >/dev/null
sudo apt update
sudo apt upgrade
sudo apt install nginx
```
