## 1.  Instalirati host za virtualke..
```console
wsl --install
```
## 2. Instalirati virtualku sa *Linux Ubuntu 20.04 LTS*

```console
https://www.releases.ubuntu.com/22.04/ubuntu-22.04.1-live-server-amd64.iso

$ sudo apt update
```

## 3. Instalirati Apache server, MySQL server, PHP i Composer
```console
$ sudo apt install apache2 mysql-server php libapache2-mod-php php-mysql

$ sudo apt install curl php-cli php-mbstring php-curl git unzip

$ cd ~

$ curl -sS -L https://getcomposer.org/installer -o composer-setup.php

$ HASH=`curl -sS https://composer.github.io/installer.sig`

$ php -r "if (hash_file('SHA384', '/tmp/composer-setup.php') === '$HASH') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"

$ sudo php /tmp/composer-setup.php --install-dir=/usr/local/bin --filename=composer

$ sudo mysql_secure_installation
```
## 4. Postaviti *'/var/www/html/ParicjalniIspit'* kao "root"
```console
$ sudo vim /etc/apache2/sites-available/000-default.conf

	> DocumentRoot /var/www/html/ParcijalniIspit
	> :wq
```
## 5. Inicijalizirati repozitorij
```console
$ git init

$ - git config --global user.name ""
$ - git config --global user.email ""
```

## 6. Kreirajte udaljeni repozitorij

```console

$ sudo apt install gh

$ gh auth login


$ git remote add origin https://github.com/mrAtimed/parcijalni-ispit-radno-okruzenje.git

$ git branch -M main

$ git add README.md

$ git commit -m "..."

$ git push -u origin main
```

## 7. Instalirate composer paket po zelji
```console
$ sudo composer require symfony/serializer

$ git add .
```

## 8. Kreirajte *.gitignore* i dodajte mapu *./vendor*
```console
$ sudo touch .gitignore

$ vim .gitignore

	> i
	> /vendor
	> esc
	> :sq

```

## 9. Inicijalni "commit" i push

```console
$ git add .

$ git commit -m "inicijalni commit"

$ git push -u origin master
```
