# Essentiels for Kubuntu v23.10 (normallement compatible Ubunu) - 

## Version de l'OS

```bash
lsb_release -a
```

## Outils de base

```bash
sudo apt install curl wget nano tree git gitk gnupg zip unzip
```

```bash
curl --version
wget --version
nano --version
tree --version
git --version
gitk --version
gnupg --version
```

## DevKits (SDK)

```bash     
sudo apt install libpcre3
sudo apt install php --no-install-recommends
sudo apt install php-amqp php-apcu php-bcmath php-cli php-ctype php-curl php-dom php-gd php-gmp php-imagick php-intl php-json php-mbstring php-mysql php-pdo php-pgsql php-redis php-simplexml php-sqlite3 php-tokenizer php-xdebug php-xml php-zip
#sudo apt install php-openssl
sudo apt install composer
sudo apt install python3 python3-pip python3-venv python3-dev python3-wheel python3-setuptools
sudo apt install openjdk-17-jdk maven gradle
sudo apt install nodejs npm
sudo npm install -g yarn
sudo npm install -g @angular/cli@16
```

```bash
php --version
composer --version
python3 --version
java --version
mvn --version
node --version
npx --version
npm --version
yarn --version
ng v
```

## DevKit (SDK) - Symfony

```bash
sudo apt -y install php-symfony
sudo apt -y install php-symfony-console
sudo wget https://get.symfony.com/cli/installer -O - | bash
sudo mv /home/dev/.symfony5/bin/symfony /usr/local/bin/symfony
symfony version
```

## MySQL

[Source](https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-20-04)

### Installation

```bash
sudo apt install mysql-server
sudo systemctl start mysql.service
```

### Configuration

```bash
sudo mysql
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'root';
exit
```

```bash
mysql -u root -p
ALTER USER 'root'@'localhost' IDENTIFIED WITH auth_socket;
exit

```

```bash
sudo mysql_secure_installation
```

## Github Desktop

Sources :
- Source du guide pour **GitHub Desktop sur Ubuntu** :
	- [Issue - berkorbay/6feda478a00b0432d13f1fc0a50467f1](https://gist.github.com/berkorbay/6feda478a00b0432d13f1fc0a50467f1)
- Source pour **GitHub Desktop - The Linux Fork** :
	- [Official - shiftkey/desktop/](https://github.com/shiftkey/desktop/)
	- [Official - shiftkey/desktop/releases/](https://github.com/shiftkey/desktop/releases/)


### Installation automatique

```bash
wget -qO - https://apt.packages.shiftkey.dev/gpg.key | gpg --dearmor | sudo tee /usr/share/keyrings/shiftkey-packages.gpg > /dev/null
sudo sh -c 'echo "deb [arch=amd64 signed-by=/usr/share/keyrings/shiftkey-packages.gpg] https://apt.packages.shiftkey.dev/ubuntu/ any main" > /etc/apt/sources.list.d/shiftkey-packages.list'
sudo apt update && sudo apt install github-desktop
```

### Installation manuelle

#### Version 3.1.1

```bash
cd Downloads/
https://github.com/shiftkey/desktop/releases/download/release-3.1.1-linux1/GitHubDesktop-linux-3.1.1-linux1.deb
sudo gdebi GitHubDesktop-linux-3.1.1-linux1.deb
```

#### Version 3.3.6

```bash
cd Downloads/
https://github.com/shiftkey/desktop/releases/download/release-3.3.6-linux1/GitHubDesktop-linux-3.3.6-linux1.deb
sudo gdebi GitHubDesktop-linux-3.3.6-linux1.deb
```

## VScode

Sources :
- Source - doc.ubuntu-fr.org : https://doc.ubuntu-fr.org/visual_studio_code
- Source - Microsoft : https://code.visualstudio.com/docs/setup/linux

```bash
sudo snap install code --classic
```

## Toolbox Jetbrains

Sources :
- Source - doc.ubuntu-fr.org : https://doc.ubuntu-fr.org/visual_studio_code
- Source - Microsoft : https://code.visualstudio.com/docs/setup/linux

```bash
sudo apt install libfuse2
cd Downloads
wget -v https://download-cdn.jetbrains.com/toolbox/jetbrains-toolbox-2.1.3.18901.tar.gz
tar -xzf jetbrains-toolbox-*.tar.gz --one-top-level=jetbrains --strip-components 1
cd jetbrains
./jetbrains-toolbox
cd ../
rm -r jetbrains
rm jetbrains-toolbox-2.1.3.18901.tar.gz
```

## Navigateur web

### Brave

```bash
sudo snap install brave
```

### Google Chrome

Sources :
- https://doc.ubuntu-fr.org/google_chrome

```bash
sudo sh -c 'echo "deb [arch=amd64] https://dl.google.com/linux/chrome/deb/ stable main" > /etc/apt/sources.list.d/google-chrome.list'
wget -O- https://dl-ssl.google.com/linux/linux_signing_key.pub | sudo tee /etc/apt/trusted.gpg.d/linux_signing_key.pub
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 78BD65473CB3BD13
sudo apt-get update
sudo apt-key export D38B4796 | sudo gpg --dearmour -o /etc/apt/trusted.gpg.d/chrome.gpg
sudo apt-get install google-chrome-stable
```

## Discord

Sources :
- https://doc.ubuntu-fr.org/google_chrome

### Installation automatique

```bash
sudo snap install discord
```

### Installation manuelle

```bash
wget "https://discord.com/api/download?platform=linux&format=deb" -O discord.deb
sudo apt install ./discord.deb -y
```

## WhatsApp

Sources :
- https://snapcraft.io/install/whatsapp-for-linux/ubuntu

```bash
sudo snap install whatsapp-for-linux
```

## Docker

Source :

- https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04

```bash
sudo apt install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
apt-cache policy docker-ce
sudo apt install docker-ce
sudo systemctl status docker
```

- Executing docker without sudo => https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04#step-2-executing-the-docker-command-without-sudo-optional


## MySQL Workbench (non finit)

Sources :
- https://gcore.com/learning/how-to-install-mysql-workbench/

```bash
cd Downloads
wget -v https://repo.mysql.com//mysql-apt-config_0.8.26-1_all.deb
sudo dpkg -i mysql-apt-config_0.8.26-1_all.deb
```

> Selections :
> 1. **ubuntu lunar**
> 2. **mysql-8.0**
> 	- mysql-8.0

```bash
sudo apt install mysql-workbench
mysql-workbench
rm mysql-apt-config_0.8.26-1_all.deb
```

## MongoDB

Source :

- https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/

```bash
curl -fsSL https://pgp.mongodb.com/server-7.0.asc | \
   sudo gpg -o /usr/share/keyrings/mongodb-server-7.0.gpg \
   --dearmor
echo "deb [ arch=amd64,arm64 signed-by=/usr/share/keyrings/mongodb-server-7.0.gpg ] https://repo.mongodb.org/apt/ubuntu jammy/mongodb-org/7.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-7.0.list
sudo apt-get update
sudo apt-get install -y mongodb-org
sudo systemctl start mongod
sudo systemctl status mongod
```

- Usage : 
	- https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/#begin-using-mongodb
	- MongoDB Compass

## MongoDB Compass

Source :

- https://www.mongodb.com/docs/compass/current/install/

```bash
cd Downloads
wget https://downloads.mongodb.com/compass/mongodb-compass_1.40.4_amd64.deb
sudo dpkg -i mongodb-compass_1.40.4_amd64.deb
mongodb-compass
rm mongodb-compass_1.40.4_amd64.deb
```