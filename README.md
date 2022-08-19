## Debian After install

My setup after install Debian 11

- [IDE's](#ides)
- [System](#system)
- [Git](#git)
- [Games](#games)
- [Databases](#databases)
- [Languages](#languages)
- [Browsers](#browsers)
- [Docker](#docker)
- [Javascript packages](#jspackage)
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


```
sudo apt install -y pkg-config libgtk2.0-dev libxml2-dev libxv-dev libsdl-dev libsdl-dev intltool libssl-dev
```


```
sudo apt install -y tree
sudo apt install -y cowsay
sudo apt install -y fortune
sudo apt install -y htop
sudo apt install -y neofetch
sudo apt install -y putty
```

<a id="packages"></a>
```
sudo apt install -y snap
sudo apt install -y flatpak
```

<a id="games"></a>
```
sudo apt install -y snes9x
sudo apt install -y stella

flatpak install --from https://flathub.org/repo/appstream/com.snes9x.Snes9x.flatpakref
flatpak install --user https://flathub.org/repo/appstream/com.retrodev.blastem.flatpakref
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
<a id="Databases"></a>
```
sudo apt install -y mysql-clients
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
$ sudo apt install -y tig

# ssh key
$ ssh-keygen -t rsa -b 4096 -C "<your_email@example.com>"
cat ~/.ssh/id_rsa.pub<a id="Text Editors"></a>
```

```
sudo apt install -y vim
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
asdf java install openjdk-11
asdf global java openjdk-11
. ~/.asdf/plugins/java/set-java-home.bash
```

**Maven**
```
sudo apt install maven
```


**Terminal and CLI Tools**
<a id="Terminal"></a>
```
sudo apt install -y tmux
sudo apt install awscli
curl https://cli-assets.heroku.com/install.sh | sh
```

<a id="browsers"></a>
```
sudo apt install -y curl
sudo apt install -y lynx
```
See Microsoft section to install Edge


<a id="ides"></a>
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

<a id="docker"></a>
**Docker**
```
sudo apt-get install ca-certificates curl gnupg lsb-release
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/debian $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
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
