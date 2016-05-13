---
layout: post
title: Elementary Os Post Install
tags: [Elementary Os]
categories: ['Operating Systems']
---

Some things to do after installing Elementary OS

### Update
    sudo apt-get update
    sudo apt-get upgrade

### Spotify (Yes, I can't work without music.)
    sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys D2C19886
    echo deb http://repository.spotify.com stable non-free | sudo tee /etc/apt/sources.list.d/spotify.list
    sudo apt-get update
    sudo apt-get install spotify-client

### VLC Media Player
    sudo apt-get install vlc

### LibreOffice
    sudo apt-get install libreoffice

### Java
    sudo apt-get install icedtea-7-plugin openjdk-7-jre

### Dropbox
Apparently the original links from the dropbox website doesn't seem to work with the Elementary OS. Fortunately,
[Zant95](https://github.com/zant95/elementary-dropbox) provides required stuff to install dropbox to Elementary OS Freya.

    git clone https://github.com/zant95/elementary-dropbox /tmp/elementary-dropbox bash /tmp/elementary-dropbox/install.sh
