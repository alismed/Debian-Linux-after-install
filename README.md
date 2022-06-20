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
