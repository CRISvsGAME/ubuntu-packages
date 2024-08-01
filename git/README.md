# CRISvsGAME

## Ubuntu 22.04 & Ubuntu 24.04

### Git Config

```
sudo apt update
sudo apt upgrade
sudo apt install curl gpg
G_PATH="/etc/apt/trusted.gpg.d/git.gpg"
R_PATH="/etc/apt/sources.list.d/git.list"
G_KEYS="https://keyserver.ubuntu.com/pks/lookup?op=get&search=0x"
R_FING="F911AB184317630C59970973E363C90F8F1B6217"
R_LINK="https://ppa.launchpadcontent.net/git-core/ppa/ubuntu"
R_INFO="deb [signed-by=$G_PATH] $R_LINK \
$(. /etc/os-release && echo "$VERSION_CODENAME") main"
curl -fsLS "$G_KEYS$R_FING" | sudo gpg --dearmor -o "$G_PATH"
echo "$R_INFO" | sudo tee "$R_PATH" >/dev/null
sudo apt update
sudo apt upgrade
sudo apt install git
```
