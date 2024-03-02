# CRISvsGAME

## Ubuntu 22.04

### Composer Config

```
COMPOSER_CHECKSUM="$(php -r 'copy("https://composer.github.io/installer.sig", "php://stdout");')"
sudo php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
sudo php -r "if (hash_file('sha384', 'composer-setup.php') === '$COMPOSER_CHECKSUM') \
{ echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
sudo php composer-setup.php --filename=composer --install-dir=/usr/local/bin
sudo php -r "unlink('composer-setup.php');"
```
