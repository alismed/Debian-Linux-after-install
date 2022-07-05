## Debian After install

My setup after install Debian 11


<a id="system"></a>
**Update packages**

```
$ sudo apt upgrade && sudo apt update
```


```
pkg-config libgtk2.0-dev libxml2-dev libxv-dev libsdl-dev libsdl-dev intltool
```


```
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

**Hugo Static Site Generators **
```
sudo apt -y install hugo
```

<a id="Databases"></a>
```
sudo apt install -y mysql-clients
```

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

<a id="Terminal"></a>
```
sudo apt install -y tmux
```


<a id="Browsers"></a>
```
sudo apt install -y curl
sudo apt install -y lynx
```

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
