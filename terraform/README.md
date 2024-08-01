# CRISvsGAME

## Ubuntu 22.04 & Ubuntu 24.04

### Terraform Config

```
sudo apt update
sudo apt upgrade
sudo apt install curl gpg
G_PATH="/etc/apt/trusted.gpg.d/hashicorp.gpg"
R_PATH="/etc/apt/sources.list.d/hashicorp.list"
R_LINK="https://apt.releases.hashicorp.com"
G_KEYS="https://apt.releases.hashicorp.com/gpg"
R_INFO="deb [signed-by=$G_PATH] $R_LINK \
$(. /etc/os-release && echo "$VERSION_CODENAME") main"
curl -fsLS "$G_KEYS" | sudo gpg --dearmor -o "$G_PATH"
echo "$R_INFO" | sudo tee "$R_PATH" >/dev/null
sudo apt update
sudo apt upgrade
sudo apt install terraform
```
