# Essentiels for Kubuntu v23.10 (normallement compatible Ubunu) - 

## Version de l'OS

```bash
lsb_release -a
```

## Outils de base

- **curl** : Curl est un outil en ligne de commande pour transférer des données à partir ou vers un serveur, utilisant divers protocoles pris en charge, tels que HTTP, HTTPS, FTP, etc. Il est souvent utilisé pour automatiser des tâches liées au téléchargement ou à l'envoi de données sur le web.
- **wget** : Wget est un autre outil en ligne de commande pour le téléchargement de fichiers depuis le web. Il permet de récupérer des fichiers à partir de serveurs web en utilisant divers protocoles tels que HTTP, HTTPS, FTP, et FTPS.
- **nano** : Nano est un éditeur de texte en ligne de commande qui est souvent utilisé pour modifier des fichiers texte directement dans un terminal. Il est conçu pour être simple à utiliser, avec une interface utilisateur intuitive.
- **tree** : Tree est une commande en ligne de commande qui affiche la structure arborescente des répertoires et des fichiers dans un système de fichiers. Il affiche les répertoires et les fichiers de manière hiérarchique, montrant les relations entre eux sous forme d'arborescence.
- **git** : Git est un système de contrôle de version distribué largement utilisé pour le suivi des modifications apportées aux fichiers et aux projets logiciels. Il est utilisé pour la gestion collaborative du code source, le suivi des versions, le travail en équipe et bien plus encore.
- **gitk** : Gitk est une interface graphique en ligne de commande pour Git. Elle permet de visualiser l'historique des commits, les branches et les fusions dans un dépôt Git. C'est un outil pratique pour examiner l'historique des modifications dans un projet Git.
- **gnupg** : GnuPG (Gnu Privacy Guard) est un logiciel de cryptographie qui implémente le standard OpenPGP pour le chiffrement et la signature de données. Il est utilisé pour sécuriser les communications, les fichiers et les emails en fournissant des mécanismes de chiffrement et de signature numérique.
- **zip & unzip** : Ce sont des utilitaires en ligne de commande utilisés pour compresser et décompresser des fichiers au format ZIP, respectivement. Zip est utilisé pour créer des archives compressées au format ZIP, tandis que Unzip est utilisé pour extraire des fichiers à partir d'archives ZIP.
- **p7zip-full** : Il s'agit d'un package qui inclut l'implémentation 7zip (p7zip) ainsi que les outils en ligne de commande pour créer et extraire des archives au format 7z, ainsi que d'autres formats de compression pris en charge par 7zip.
- **baobab** : Baobab est une application graphique utilisée pour visualiser l'utilisation de l'espace disque sur un système de fichiers. Elle affiche une représentation visuelle de la taille des fichiers et des répertoires, ce qui permet à l'utilisateur de comprendre rapidement quels fichiers ou répertoires occupent le plus d'espace sur le disque. Cela peut être utile pour gérer l'espace disque et identifier les fichiers ou répertoires volumineux qui pourraient être supprimés ou déplacés.

```bash
sudo apt -y install curl wget nano tree git gitk gnupg zip unzip baobab p7zip-full
```

```bash
curl --version
wget --version
nano --version
tree --version
git --version
gitk --version
gnupg --version
baobab --version
7z --version
```

## DevKits (SDK)

```bash     
sudo apt -y install libpcre3
sudo apt -y install php --no-install-recommends
sudo apt -y install php-amqp php-apcu php-bcmath php-cli php-ctype php-curl php-dom php-gd php-gmp php-imagick php-intl php-json php-mbstring php-mysql php-pdo php-pgsql php-redis php-simplexml php-sqlite3 php-tokenizer php-xdebug php-xml php-zip
#sudo apt -y install php-openssl
sudo apt -y install composer
sudo apt -y install python3 python3-pip python3-venv python3-dev python3-wheel python3-setuptools
sudo apt -y install openjdk-17-jdk maven gradle
sudo apt -y install nodejs npm
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
npm --versions
yarn --version
ng v
```

## Homebrew

```bash
sudo apt -y install build-essential procps curl file git
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

test -d ~/.linuxbrew && eval "$(~/.linuxbrew/bin/brew shellenv)"
test -d /home/linuxbrew/.linuxbrew && eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"
echo "eval \"\$($(brew --prefix)/bin/brew shellenv)\"" >> ~/.bashrc

brew install hello
```

> Test : `hello`
> ```bash
> dev@dev:~$ hello
> Hello, world!
> ```

## Oh My Posh

### Installation de la police de Oh My Posh

```bash
cd ~
mkdir .fonts
cd ~/Downloads/
wget https://github.com/ryanoasis/nerd-fonts/releases/download/v2.1.0/Meslo.zip
unzip ~/Downloads/Meslo.zip -d ~/.fonts/Meslo
fc-cache -fv
```

> Dans les terminals, il faut sélectionner la police **MesloLGS NF Regular**.

### Installation de Oh My Posh - Homebrew

```bash
brew install jandedobbeleer/oh-my-posh/oh-my-posh
```

### Installation de Oh My Posh - Manual

```bash
sudo wget https://github.com/JanDeDobbeleer/oh-my-posh/releases/latest/download/posh-linux-amd64 -O /usr/local/bin/oh-my-posh
sudo chmod +x /usr/local/bin/oh-my-posh
```

#### Installation des thèmes de Oh My Posh

```bash
mkdir ~/.poshthemes
wget https://github.com/JanDeDobbeleer/oh-my-posh/releases/latest/download/themes.zip -O themes.zip
unzip themes.zip -d ~/.poshthemes
chmod u+rw,g+r ~/.poshthemes/*.json
rm themes.zip
```

#### Configuration de Oh My Posh

```bash
oh-my-posh init bash --config .poshthemes/montys.omp.json > .oh-my-post-init.sh
sudo mv -v .oh-my-post-init.sh /etc/profile.d/oh-my-post-init.sh
source /etc/profile.d/oh-my-post-init.sh
echo "source .oh-my-post-init.sh" >> .bashrc
source .bashrc
```

#### Suppression de Oh My Posh

```bash
#---Suppression---
rm -v .oh-my-post-init.sh
sed -i '/source .oh-my-post-init.sh/d' .bashrc
source .bashrc
#rm -v .bashrc
#---Suppression des fichiers---
sudo rm -v /usr/local/bin/oh-my-posh
sudo rm -v /etc/profile.d/oh-my-post-init.sh
#---Suppression des thèmes---
rm -r -v ~/.poshthemes
#---Suppression de la police---
rm -r -v ~/.fonts/Meslo
fc-cache -fv
```

🚨🚨🚨 Pas stable, à revoir... 🚨🚨🚨
- https://brew.sh/
- https://docs.brew.sh/Homebrew-on-Linux#install
- https://ohmyposh.dev/docs/themes
- https://ohmyposh.dev/docs/installation/linux
- https://calebschoepp.com/blog/2021/how-to-setup-oh-my-posh-on-ubuntu/
- https://www.librebyte.net/en/cli-en/oh-my-posh-a-beatifull-prompt-for-your-shell/
- https://askubuntu.com/questions/963874/uninstall-oh-my-zsh

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
sudo apt -y install mysql-server
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

## MySQL Workbench (non finit)

Sources :
- https://gcore.com/learning/how-to-install-mysql-workbench/

```bash
sudo snap install mysql-workbench-community
```

```bash
cd ~/Downloads
wget -v https://repo.mysql.com//mysql-apt-config_0.8.26-1_all.deb
sudo dpkg -i mysql-apt-config_0.8.26-1_all.deb
sudo apt -y install mysql-workbench
mysql-workbench
rm mysql-apt-config_0.8.26-1_all.deb
```

> Selections :
> 1. **MySQL Server & Cluster**
> 2. **mysql-8.0**

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
sudo apt update && sudo apt -y install github-desktop
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

## Docker

Source :

- https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04

```bash
sudo apt -y install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
apt-cache policy docker-ce
sudo apt -y install docker-ce
sudo systemctl status docker
```

- Executing docker without sudo => https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04#step-2-executing-the-docker-command-without-sudo-optional


## Docker Desktop

### Pour installer

```
sudo apt -y install qemu-system-x86 pass uidmap
cd ~/Downloads
wget https://desktop.docker.com/linux/main/amd64/145265/docker-desktop-4.29.0-amd64.deb
sudo dpkg -i docker-desktop-4.29.0-amd64.deb
systemctl --user start docker-desktop
systemctl --user status docker-desktop
```

### Pour désintaller

```
sudo apt remove docker-desktop qemu-system-x86 pass uidmap
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
sudo apt -y install libfuse2
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
sudo apt -y install ./discord.deb -y
```

## WhatsApp

Sources :
- https://snapcraft.io/install/whatsapp-for-linux/ubuntu

```bash
sudo snap install whatsapp-for-linux
```

---

## Apps Mails

### Thunderbird

**Already installed!**

- Test :
	- Install : ✔ **SUCCESS**
	- Auto-Config : ❌ **FAIL**
	- Start : ❌ **FAIL**
	- Stable : 🤷‍♂️ **IN CHECK**

### KMail

Source : https://apps.kde.org/fr/kmail2/

```bash
sudo appstreamcli install org.kde.kmail2.desktop
```

- Test :
	- Install : ✔ **SUCCESS**
	- Auto-Config: ✔ **SUCCESS**
	- Start : ✔ **SUCCESS**
	- Stable : 🤷‍♂️ **IN CHECK**

### Mailspring

Source : https://www.getmailspring.com/

```bash
sudo snap install mailspring
```

- Test :
	- Install : ✔ **SUCCESS**
	- Auto-Config: ✔ **SUCCESS**
	- Start : ✔ **SUCCESS**
	- Stable : 🤷‍♂️ **IN CHECK**

### BlueMail

Source : https://bluemail.me/desktop/linux/

```bash
cd ~/Downloads/
mkdir BlueMail
cd BlueMail
wget https://download.bluemail.me/BlueMail/deb/BlueMail.deb
sudo dpkg -i BlueMail.deb
```

- Test :
	- Install : ✔ **SUCCESS**
	- Auto-Config : ❌ **FAIL**
	- Start : ❌ **FAIL**
	- Stable : 🤷‍♂️ **IN CHECK**

### Geary

Source : https://wiki.gnome.org/Apps/Geary

```bash
sudo apt -y install geary
```

- Test :
	- Install : ✔ **SUCCESS**
	- Auto-Config: ✔ **SUCCESS**
	- Start : ✔ **SUCCESS**
	- Stable : 🤷‍♂️ **IN CHECK**

### Evolution

Source : 
- wiki :
	- https://wiki.gnome.org/Apps/Evolution
	- https://wiki.gnome.org/Apps/Evolution#Get_the_Source_Code
- gitlab :
	- dépôts :
		- https://gitlab.gnome.org/GNOME/evolution/
		- https://gitlab.gnome.org/GNOME/evolution-data-server/
	- building :
		- https://gitlab.gnome.org/GNOME/evolution/-/wikis/Building

Dernières release :
	- evolution : **3.52.0**
	- evolution-data-server : **3.52.0**

```bash
sudo apt -y install cmake
#---
cd ~/Downloads/
mkdir Evolution
cd Evolution
#---
git clone https://gitlab.gnome.org/GNOME/evolution-data-server.git
git clone https://gitlab.gnome.org/GNOME/evolution.git
#---
cd evolution-data-server
git checkout -b gnome-3.52.0 origin/gnome-3.52.0
mkdir _build
#---
cd ../evolution
git checkout -b gnome-3.52.0 origin/gnome-3.52.0
mkdir _build
#---
tree -d -L 2
#---
export GSETTINGS_SCHEMA_DIR="/opt/evolution/share/glib-2.0/schemas"
export LD_LIBRARY_PATH=/opt/evolution/lib:$LD_LIBRARY_PATH
export PATH=/opt/evolution/bin:$PATH
export PKG_CONFIG_PATH=/opt/evolution/lib/pkgconfig:$PKG_CONFIG_PATH
```

🚨🚨🚨 **Pas finit, à revoir...** 🚨🚨🚨

- Test :
	- Install : ❌ **FAIL**
	- Auto-Config : ❌ **FAIL**
	- Start : ❌ **FAIL**
	- Stable : 🤷‍♂️ **IN CHECK**

---

## Petit script de création d'un environement de dépôts de développement

```bash
#---EnvProject---
cd
mkdir dev
mkdir dev/ldumay
mkdir dev/ldumay/local
mkdir dev/ldumay/org/
mkdir dev/ldumay/org/2023-esiee-projectlab
mkdir dev/ldumay/org/ldumay-dev
mkdir dev/ldumay/org/ldumay-dev-and-prod
mkdir dev/ldumay/org/ldumay-prod
mkdir dev/ldumay/org/ldumay-prod-dockers/
mkdir dev/ldumay/org/yama-soft
tree -d -L 3

#---DemoProject---
cd ~/dev/ldumay/local/
git clone https://github.com/davidmoten/maven-demo.git
cd maven-demo
mvn clean install
tree
```