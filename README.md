https://www.youtube.com/watch?v=Ruk7OO0piJU&t=245s

https://mathesonsteplock.ca/install-home-assistant-supervised-on-debian/

#Atualizar a sources-list/ls
#https://techviewleo.com/add-debian-11-bullseye-official-repositories-to-sources-list/
sudo tee /etc/apt/sources.list<<EOF
deb http://deb.debian.org/debian bullseye main
deb-src http://deb.debian.org/debian bullseye main

deb http://security.debian.org/debian-security bullseye-security main
deb-src http://security.debian.org/debian-security bullseye-security main

deb http://deb.debian.org/debian bullseye-updates main
deb-src http://deb.debian.org/debian bullseye-updates main

deb http://deb.debian.org/debian bullseye-backports main
deb-src http://deb.debian.org/debian bullseye-backports main
EOF

sudo apt-get update && sudo apt-get upgrade -y

sudo apt --fix-broken install

sudo apt-get install jq wget curl avahi-daemon udisks2 libglib2.0-bin network-manager dbus apparmor -y

sudo apt --fix-broken install

sudo reboot

sudo su

#Para ir para o raíz
cd

wget https://github.com/home-assistant/os-agent/releases/download/1.2.2/os-agent_1.2.2_linux_x86_64.deb

sudo dpkg -i os-agent_1.2.2_linux_x86_64.deb

wget https://github.com/home-assistant/supervised-installer/releases/latest/download/homeassistant-supervised.deb

sudo dpkg -i homeassistant-supervised.deb

Criar o arquivo para ler os dados do UPS na versão Supervised (https://github.com/edilsoncorrea/upsraspberryhomeassistant)
