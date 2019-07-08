---
layout: post
title:  "Unbox Ubuntu Machine"
author: vkosuri
categories: [ linux ]
image: assets/images/ubuntu.png
tags: [notes]
---

The instruction will easier you Unbox your new linux machine, Hasslefree Python setup and Build best Continuation integration pipeline environments.


Recommendation would be to use
* Ubuntu 16.04 (xenial) or better - [https://wiki.ubuntu.com/Releases](https://wiki.ubuntu.com/Releases)
* Linux Mint 18.x or better - [https://linuxmint.com/](https://linuxmint.com/)
* Debian 9 (stretch) or later - [https://www.debian.org/](https://www.debian.org/)

## Create a new user

``` Bash
# Create Home directory
sudo useradd -m -d /home/vkosuri vkosuri
# Change Password
sudo passwd vkosuri
sudo usermod -s /bin/bash vkosuri
```

## Change Default Shell

```bash
# If you have administrative rights, just run as root:
usermod -s /bin/bash YOUR_USERNAME (replacing YOUR_USERNAME with your user name).
  
# If you don't have adm. rights, you can still just run bash --login at login, by putting the below line at the end of your .cshrc or .profile (in your home directory)

setenv SHELL /bin/bash
exec /bin/bash --login
```
## Python Virtual Environment

``` Bash
sudo apt-get install virtualenv
```
## Enterprise Pip configuration

```Bash
machine:~$ vi ~/.pip/pip.conf
[global]
index-url = https://artifactory.xyz.com/artifactory/pypi
```
## GNU make
```bash
# Update repository information
sudo apt-get update

# Install metapackage that contains make
sudo apt-get install build-essential
```

## Git
```bash
# Update repository information
sudo apt-get update

# Install git package
sudo apt-get install git

# Configure git
git config --global user.email "you@example.com"
git config --global user.name "Your Name"

```

## Docker CE
```bash
# Update repository information
sudo apt-get update

# Install Docker prerequisites
sudo apt-get install apt-transport-https ca-certificates curl gnupg2 software-properties-common

# Add Docker repository keys
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add -

# Add the Docker APT repository for the current Linux distro
DISTRO_CODENAME=$( (grep DISTRIB_CODENAME /etc/upstream-release/lsb-release || grep DISTRIB_CODENAME /etc/lsb-release) 2>/dev/null | cut -d'=' -f2 )
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $DISTRO_CODENAME stable"

# Update repository information
sudo apt-get update

# Install Docker Community Edition
sudo apt-get install docker-ce

# Add the current user to the docker group
sudo usermod -aG docker $USER

# Create the Docker config file with enterprise repositories and DNS server information
sudo tee /etc/docker/daemon.json << EOL
{
    "dns":["a.b.c.d","a.b.c.d"],
    "insecure-registries": ["docker.enterprise.com:5000", "cn-docker.enterprise.com:5000"]
}
EOL

# Restart Docker service to pick up the changes
sudo service docker restart
```

## .vmrc
``` Bash
set tabstop=4           " number of visual spaces per TAB
set softtabstop=4       " number of spaces in tab when editing
set expandtab           " tabs are spaces
set number              " show line numbers
set showcmd             " show command in bottom bar
set cursorline          " highlight current line
filetype indent on      " load filetype-specific indent files
set wildmenu            " visual autocomplete for command menu
set lazyredraw          " redraw only when we need to.
set showmatch           " highlight matching [{()}]
set incsearch           " search as characters are entered
set hlsearch            " highlight matches
```