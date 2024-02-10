# CRISvsGAME

## Ubuntu 22.04

### Git Config

```
sudo apt update
sudo apt upgrade
sudo apt install curl gpg
G_PATH="/etc/apt/trusted.gpg.d/git.gpg"
R_PATH="/etc/apt/sources.list.d/git.list"
G_KEYS="https://keyserver.ubuntu.com/pks/lookup?op=get&search=0x"
R_FING="E1DD270288B4E6030699E45FA1715D88E1DF1F24"
R_LINK="https://ppa.launchpadcontent.net/git-core/ppa/ubuntu"
R_INFO="deb [signed-by=$G_PATH] $R_LINK \
$(. /etc/os-release && echo "$VERSION_CODENAME") main"
curl -fsLS "$G_KEYS$R_FING" | sudo gpg --dearmor -o "$G_PATH"
echo "$R_INFO" | sudo tee "$R_PATH" >/dev/null
sudo apt update
sudo apt upgrade
sudo apt install git
```
