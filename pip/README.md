# CRISvsGAME

## Ubuntu 22.04 & Ubuntu 24.04

### Pip Config

-   Externally Managed Environment

```
sudo apt update
sudo apt upgrade
sudo apt install python3-pip
```

-   Internally Managed Environment

```
sudo apt update
sudo apt upgrade
sudo apt install curl
R_LINK="https://bootstrap.pypa.io/get-pip.py"
curl -fsLS "$R_LINK" | sudo python
```

### More Information

[PEP 668](https://peps.python.org/pep-0668/)
