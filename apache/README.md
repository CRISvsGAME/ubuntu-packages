# CRISvsGAME

## Ubuntu 22.04

### Apache Config

```
sudo apt update
sudo apt upgrade
sudo apt install curl gpg
G_PATH="/etc/apt/trusted.gpg.d/ondrej.gpg"
R_PATH="/etc/apt/sources.list.d/ondrej-apache.list"
G_KEYS="https://keyserver.ubuntu.com/pks/lookup?op=get&search=0x"
R_FING="14AA40EC0831756756D7F66C4F4EA0AAE5267A6C"
R_LINK="https://ppa.launchpadcontent.net/ondrej/apache2/ubuntu"
R_INFO="deb [signed-by=$G_PATH] $R_LINK \
$(. /etc/os-release && echo "$VERSION_CODENAME") main"
curl -fsLS "$G_KEYS$R_FING" | sudo gpg --dearmor -o "$G_PATH"
echo "$R_INFO" | sudo tee "$R_PATH" >/dev/null
sudo apt update
sudo apt upgrade
sudo apt install apache2
```
