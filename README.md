# Ubuntu Desktop 20.04

**Goal:**
from a single command, create a ubuntu linux virtual machine ready to go with the basic applications.

![enter image description here](https://i.imgur.com/xpMpFkY.jpg)

**Pre requisites:**
- Have [Vagrant](https://www.vagrantup.com/downloads.html) installed
- Have [Virtualbox and the extension pack](https://www.virtualbox.org/wiki/Downloads) installed

**How to run:**
- Download this repo
- From a terminal, navigate to the projects folder and run the command `vagrant up`
- Once the provision complete, login with the user `vagrant` and password `vagrant`

**What is included?:**
- Base OS
- maven
- OpenJDK 8 (by default install the latest version)
- wget
- libgtk-3-0
- libcanberra-gtk-module
- Mulesoft Anypoint Studio 7.5.1

**What I want and/or need to fix:**
- Test on Windows host (Currently testing on MacOS)
- Terminal font is weird, need to script to use a specific font to Fix
- Create shortcut for Studio
- Script to change the wallpaper
- Setup screen resolution during the provision
- Add apps to the favorites panel
- Install more apps (why not right?)
