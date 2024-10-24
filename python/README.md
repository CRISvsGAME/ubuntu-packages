# CRISvsGAME

## Ubuntu 22.04 & Ubuntu 24.04

### Python Config

```
sudo apt update
sudo apt upgrade
sudo apt install curl gpg
G_PATH="/etc/apt/trusted.gpg.d/deadsnakes.gpg"
R_PATH="/etc/apt/sources.list.d/deadsnakes-python.list"
G_KEYS="https://keyserver.ubuntu.com/pks/lookup?op=get&search=0x"
R_FING="F23C5A6CF475977595C89F51BA6932366A755776"
R_LINK="https://ppa.launchpadcontent.net/deadsnakes/ppa/ubuntu"
R_INFO="deb [signed-by=$G_PATH] $R_LINK \
$(. /etc/os-release && echo "$VERSION_CODENAME") main"
curl -fsLS "$G_KEYS$R_FING" | sudo gpg --dearmor -o "$G_PATH"
echo "$R_INFO" | sudo tee "$R_PATH" >/dev/null
sudo apt update
sudo apt upgrade
echo "Select the Python version you want to install:"
echo "1. Python 3.11"
echo "2. Python 3.12"
echo "3. Python 3.13"
echo "4. Python 3.14 (Prerelease)"
echo "q. Exit without installing Python"
read -p "Enter your choice ( 1 | 2 | 3 | q ): " CHOICE
case $CHOICE in
1) CHOICE=python3.11 ;;
2) CHOICE=python3.12 ;;
3) CHOICE=python3.13 ;;
4) CHOICE=python3.14 ;;
q) echo "Exiting." ;;
*) CHOICE="" && echo "Invalid Choice. Exiting." ;;
esac
if grep -q "python" <<<"$CHOICE"; then
sudo apt install "$CHOICE" && sudo ln -fs /usr/bin/"$CHOICE" /usr/bin/python
fi
```
