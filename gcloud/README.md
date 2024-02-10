# CRISvsGAME

## Ubuntu 22.04

### Gcloud Config

```
sudo apt update
sudo apt upgrade
sudo apt install curl gpg
G_PATH="/etc/apt/trusted.gpg.d/gcloud.gpg"
R_PATH="/etc/apt/sources.list.d/gcloud.list"
R_LINK="https://packages.cloud.google.com/apt"
G_KEYS="https://packages.cloud.google.com/apt/doc/apt-key.gpg"
R_INFO="deb [signed-by=$G_PATH] $R_LINK cloud-sdk main"
curl -fsLS "$G_KEYS" | sudo gpg --dearmor -o "$G_PATH"
echo "$R_INFO" | sudo tee "$R_PATH" >/dev/null
sudo apt update
sudo apt upgrade
sudo apt install google-cloud-cli
```
