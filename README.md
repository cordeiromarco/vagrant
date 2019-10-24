# vagrant
Vagrant files repository

#Howto windows 10

#Disable HyperV
Disable-WindowsOptionalFeature -Online -FeatureName Microsoft-Hyper-V-All
restart
#Install ssh & rsync & curl & wget
https://sourceforge.net/projects/mingw/files/Installer/mingw-get-setup.exe/download
#Install VirtualBox
https://www.virtualbox.org/wiki/Downloads
#Install Vagrant
https://www.vagrantup.com/downloads.html
restart
#Install pug-in:
vagrant plugin install vagrant-vbguest

