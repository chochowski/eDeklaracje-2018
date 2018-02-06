# eDeklaracje-2018 
how to run eDeklaracje 2018 on Ubuntu 17.10

# install necesary i386 libraries
sudo apt-get install libgtk2.0-0:i386 libstdc++6:i386 libxml2:i386 libxslt1.1:i386 libcanberra-gtk-module:i386 gtk2-engines-murrine:i386 libqt4-qt3support:i386 libgnome-keyring0:i386 libnss-mdns:i386 libnss3:i386

# make keyring visible for Adobe Air
sudo ln -s /usr/lib/i386-linux-gnu/libgnome-keyring.so.0 /usr/lib/libgnome-keyring.so.0

sudo ln -s /usr/lib/i386-linux-gnu/libgnome-keyring.so.0.2.0 /usr/lib/libgnome-keyring.so.0.2.0

# Download Adobe Air
cd ~/Downloads

wget http://airdownload.adobe.com/air/lin/download/2.6/AdobeAIRSDK.tbz2

sudo mkdir /opt/adobe-air-sdk

sudo tar jxf AdobeAIRSDK.tbz2 -C /opt/adobe-air-sdk

# Download Air runtime/SDK from Archlinux

wget https://aur.archlinux.org/cgit/aur.git/snapshot/adobe-air.tar.gz

sudo tar xvf adobe-air.tar.gz -C /opt/adobe-air-sdk

sudo chmod +x /opt/adobe-air-sdk/adobe-air/adobe-air

# Get e-Deklaracje.air from mf

wget http://www.e-deklaracje.gov.pl/files/dopobrania/e-dek/app/e-DeklaracjeDesktop.air


sudo mkdir /opt/e-Deklaracje-2018

sudo mv e-DeklaracjeDesktop.air /opt/e-Deklaracje-2018

sudo rm /usr/lib/libgnome-keyring.so.0.2.0 

sudo rm /usr/lib/libgnome-keyring.so.0

# Start e-Deklaracje

/opt/adobe-air-sdk/adobe-air/adobe-air /home/mchochowski/Downloads/e-DeklaracjeDesktop.air
