Home Assistant Supervised Instalação no Debian Linux

Video muito bom do canal KPeyanski sobre a instalação do Home Assistant Supervised no Debian Linux: [Home Assistant Supervised Installation on Debian Linux](https://www.youtube.com/watch?v=Ruk7OO0piJU&t=245s)

Tutorial de Matheson Steplock sobre instalação do Home Assistant Supervised no Debian Linux: 
[Install Home Assistant (Supervised) on Debian By  Matheson Last Updated On June 28, 2020](https://mathesonsteplock.ca/install-home-assistant-supervised-on-debian/)

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

Link para baixar a última versão do Home Assistant Supervised: 
                                    
>`wget https://github.com/home-assistant/supervised-installer/releases/latest/download/homeassistant-supervised.deb`

Comando para instalação do pacote da versão do Home Assistant Supervised: `sudo dpkg -i homeassistant-supervised.deb`

Tutorial para utilização do módulo [UPS 18650 Lite](https://github.com/linshuqin329/UPS-18650-Lite) na versão Supervised do Home Assistant. [Clique aqui](https://github.com/edilsoncorrea/upsraspberryhomeassistant)
