## Debian After install

My setup after install Debian 11

- [System](#system)
- [Git](#git)
- [Text Editors & IDE's](#ides)
- [Games](#games)
- [Databases](#databases)
- [Languages](#languages)
- [Browsers](#browsers)
- [Docker](#docker)
- [Comumunicators](#communicators)
- [Termninal & CLI's](#terminal)
- [Microsoft](#microsoft)
- [Audio](#audio)
- [Video](#video)


<a id="system"></a>
**Update packages**

```
$ sudo apt upgrade && sudo apt update
```

**Libraries**
```
sudo apt install -y 
          pkg-config libgtk2.0-dev \ 
          libxml2-dev libxv-dev \ 
          libsdl-dev libsdl-dev intltool \ 
          libssl-dev libbz2-dev \
          libyaml-dev libreadline-dev
```

**Tools**
```
sudo apt install -y tree
sudo apt install -y sl
sudo apt install -y cowsay
sudo apt install -y fortune
sudo apt install -y htop
sudo apt install -y neofetch
sudo apt install -y putty
sudo apt install -y netsniff-ng
sudo apt install -y tcpdump
sudo apt install -y wireshark-gtk
sudo apt install -y openvpn network-manager-openvpn
```

**SpeedTest**
```
curl -L https://packagecloud.io/ookla/speedtest-cli/gpgkey | gpg --dearmor | sudo tee /usr/share/keyrings/speedtestcli-archive-keyring.gpg >/dev/null
echo "deb [signed-by=/usr/share/keyrings/speedtestcli-archive-keyring.gpg] https://packagecloud.io/ookla/speedtest-cli/debian/ $(lsb_release -cs) main" | sudo tee  /etc/apt/sources.list.d/speedtest.list
sudo apt update
sudo apt install speedtest
```

**Login**

Hide user from login list

Create the file /etc/dconf/profile/gdm
```
user-db:user
system-db:gdm
file-db:/usr/share/gdm/greeter.dconf-defaults
```

Create the directory `sudo mkdir /etc/dconf/db/gdm.d`

Create the file /etc/dconf/db/gdm.d/00-login-screen
```
[org/gnome/login-screen]
# Do not show the user list
disable-user-list=true
```

Execute `sudo dconf update`


<a id="packages"></a>
```
sudo apt install -y snap
sudo apt install -y flatpak
```

<a id="games"></a>
```
sudo apt install -y snes9x
sudo apt install -y stella
sudo apt install -y chocolate-doom

#snes9x
flatpak install --from https://flathub.org/repo/appstream/com.snes9x.Snes9x.flatpakref
# blastem
flatpak install --user https://flathub.org/repo/appstream/com.retrodev.blastem.flatpakref
# duke3d
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
flatpak install flathub com.eduke32.EDuke32
```

**Hugo Static Site Generators**
```
sudo apt -y install hugo
```

<a id="microsoft"></a>
```
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
```

**Edge**
```
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/edge stable main" > /etc/apt/sources.list.d/microsoft-edge-dev.list'
sudo apt update -y
sudo apt install -y microsoft-edge-dev
```

**Teams**
```
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/ms-teams stable main" > /etc/apt/sources.list.d/teams.list'
sudo apt update -y
sudo apt install -y teams
```

**Databases**
<a id="databases"></a>
```
sudo apt install -y default-mysql-client
sudo apt install -y postgresql-client
sudo apt install -y redis-tools
sudo apt install -y sqlite3
```

**DBeaver**
```
git clone https://github.com/dbeaver/dbeaver.git dbeaver
cd dbeaver
mvn package
```
Binaries are in product/community/target/products/

<a id="git"></a>
```
$ sudo apt install -y git tig

# ssh key
$ ssh-keygen -t rsa -b 4096 -C "<your_email@example.com>"
cat ~/.ssh/id_rsa.pub
```

<a id="languages"></a>
**asdf**
```
git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.10.2
```

Edit `~/.bashrc` adding:
```
. $HOME/.asdf/asdf.sh
. $HOME/.asdf/completions/asdf.bash
```

Update your current shell environment
```
source .bashrc
```

Add the plugin and install. _Example: Ruby_
```
asdf plugin-add ruby
```

List of available versions
```
asdf list all ruby
```

Install
```
asdf install ruby 3.1.0
asdf global ruby 3.1.0
```

<a id="terraform"></a>
**Terraform**
```
curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo apt-key add -
sudo apt-add-repository "deb [arch=$(dpkg --print-architecture)] https://apt.releases.hashicorp.com $(lsb_release -cs) main"
sudo apt update
sudo apt install terraform
terraform -install-autocomplete
```

**Java**
Using asdf:
```
asdf plugin add java
asdf install java openjdk-11
asdf global java openjdk-11
. ~/.asdf/plugins/java/set-java-home.bash
```

**Maven**
```
sudo apt install maven
```

**Python**
Using asdf:
```
asdf plugin add python
asdf install python 3.10.0
asdf global python 3.10.0
```


**.Net Core**
```
wget https://packages.microsoft.com/config/debian/11/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
rm packages-microsoft-prod.deb
sudo apt upgrade
sudo apt install dotnet-sdk-5-0
```

**Remmina** 
```
echo 'deb http://ftp.debian.org/debian stretch-backports main' | sudo tee --append /etc/apt/sources.list.d/stretch-backports.list >> /dev/null
sudo apt update
sudo apt install -y remmina remmina-plugin-rdp remmina-plugin-secret remmina-plugin-spice
```

**Terminal and CLI Tools**
<a id="Terminal"></a>
**Powerline**
```
sudo apt install -y powerline fonts-powerline powerline-gitstatus
```

Add the following lines to the `bashrc`
```
# Powerline configuration
powerline-daemon -q
POWERLINE_BASH_CONTINUATION=1
POWERLINE_BASH_SELECT=1
. /usr/share/powerline/bindings/bash/powerline.sh
```

Execute `source ~/.bashrc`


**TMUX**
```
sudo apt install -y tmux
```

```
## Heroku
curl https://cli-assets.heroku.com/install.sh | sh

## AWS CLI
sudo apt install awscli

## AWS SAM
wget https://github.com/aws/aws-sam-cli/releases/latest/download/aws-sam-cli-linux-x86_64.zip
unzip aws-sam-cli-linux-x86_64.zip
sudo ./sam-installation/install
rm aws-sam-cli-linux-x86_64.zip

## AWS Vault
sudo curl -L -o /usr/local/bin/aws-vault https://github.com/99designs/aws-vault/releases/download/v6.6.0/aws-vault-linux-amd64
sudo chmod 755 /usr/local/bin/aws-vault
```

<a id="browsers"></a>
```
sudo apt install -y curl
sudo apt install -y lynx
sudo apt install -y chromium
sudo apt install -y qbittorrent
```
See Microsoft section to install Edge


<a id="ides"></a>
```
sudo apt install -y vim
sudo apt install -y arduino
```

**IntelliJ IDEA Community**
```
wget https://download-cf.jetbrains.com/idea/ideaIC-2020.1.tar.gz
tar -zxvf ideaIC-2022.2.1.tar.gz
sudo mkdir /opt/idea
sudo chmod 777 /opt/idea
mv idea-IC-222.3739.54/* /opt/idea/
rm ideaIC-2022.2.1.tar.gz

sh /opt/idea/bin/idea.sh
```
Finish following the instructions in the wizard window.
In the gear icon create a desktop entry


**VS Code**

Import Repository
```
wget -O- https://packages.microsoft.com/keys/microsoft.asc | sudo gpg --dearmor | sudo tee /usr/share/keyrings/vscode.gpg

echo deb [arch=amd64 signed-by=/usr/share/keyrings/vscode.gpg] https://packages.microsoft.com/repos/vscode stable main | sudo tee /etc/apt/sources.list.d/vscode.list
```

Update and Install
```
sudo apt update
sudo apt install code -y
```

**Insomnia**
```
echo "deb [trusted=yes arch=amd64] https://download.konghq.com/insomnia-ubuntu/ default all" \
    | sudo tee -a /etc/apt/sources.list.d/insomnia.list

# Refresh repository sources and install Insomnia
sudo apt-get update
sudo apt-get install insomnia
```

<a id="docker"></a>
**Docker**
```
sudo apt-get install ca-certificates curl gnupg lsb-release
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/debian $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-compose docker-compose-plugin
```

<a id="nodejs"></a>
**Nodejs**

Using [Node Version Manager](https://github.com/nvm-sh/nvm)
```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
source .bashrc 
```

List the versions and install
```
nvm ls-remote
nvm install [x.x.x]
```
