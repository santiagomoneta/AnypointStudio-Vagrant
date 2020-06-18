# Anypoint Studio 7 on headless Ubuntu 20.04

**Goal:**
To run Studio 7 from a directly from a dynamically created VM

**Pre requisites (all OS):**
- Have [Vagrant](https://www.vagrantup.com/downloads.html) installed
- Have [Virtualbox and the extension pack](https://www.virtualbox.org/wiki/Downloads) installed

**Pre-check (MacOS):**
- Install [Homebrew](https://docs.brew.sh/Installation).
- Install XQuartz
	- option 1: Command: `brew cask install xquartz`
	- option 2: https://www.xquartz.org/

- Install Socat
	- Command: `brew install socat`
- Make sure XQuartz accept client connections:
	- run the command: open -a Xquartz
	- On the top left menu, click on "XQuartz" and select "Preferences"
	- On the "Security" section, be sure "Allow connections from network clients" is marked.
- Make sure socat is listening on the port 6000:
	- Command: `socat TCP-LISTEN:6000,reuseaddr,fork UNIX-CLIENT:\"$DISPLAY\"`

**Pre-checks (windows):**
- Download and install VcXsrv Windows X Server from [here](https://sourceforge.net/projects/vcxsrv/)
- Run the VcXsrv server and leave all options as default, just click next until finish.
- The VcXsrv icon is now on the windows task manager and if you hover the cursor over it, you will see your hostname and the display number, usually is zero.

**How to run:**
- Download this repo
- From a terminal, navigate to the projects folder and run the command `vagrant up`
- Wait until provisioning process is complete
- From VirtualBox, Login to the VM with the user `vagrant` and password `vagrant`
- Run the command `export DISPLAY=192.168.0.15:0` (replace 192.168.0.15 with your host IP)
- Run Studio with the command `/home/vagrant/AnypointStudio/AnypointStudio`
- You should see the Studio splash screen and that is it :) have fun

**What is included?:**
- Base OS
- net-tools
- maven
- OpenJDK 8 (by default install the latest version)
- wget
- libgtk-3-0
- libcanberra-gtk-module
- Mulesoft Anypoint Studio 7.5.1

**What I want and/or need to fix:**
- You still have to manually launch studio from the VM
- need to add the export DISPLAY variable to the provision, make it interactive and persisten when the VM is rebooted.
- Add studio to the vm startup
