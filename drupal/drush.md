### Update Ubuntu ###
```
sudo apt update
```
### Install PHP & Composer ###

### Add latest HASH to Composer installation ###
```php
HASH=`curl -sS https://composer.github.io/installer.sig`
```

### Verify Composer HASH ###
```php
echo $HASH
```

### Verify Composer Installation ###
```php
php -r "if (hash_file('SHA384', 'composer-setup.php') === '$HASH') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
```

### Result ###
```
Installer verified
```

### Install PHP for Drush ###
```
sudo apt-get update 
sudo apt install php-xml php-mbstring
```

### Install Drush with Composer ###
```
sudo composer global require drush/drush
```
```
drush --version
```
### Result ###
```
Drush Commandline Tool 10.3.1
```

### Set Drush path ###
```
export PATH="$HOME/.composer/vendor/drush/drush:$PATH"
```

[Read More](https://tubemint.com/installing-drush-with-composer)

# Syntax clear cache in Drupal 9
```
drush cache-clear all --uri=<name_domain>
example: drush cache-clear all --uri=ttvl.local
```
Or clear cache for option
```
drush cc --uri=<name_domain>
```