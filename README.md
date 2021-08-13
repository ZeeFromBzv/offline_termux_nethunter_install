#offline_termux_nethunter_install

WARNING: the offline innstallation is done by the script localinstall (for the minimal package) or localinstall_full (for the full package) after downloading it, you'll obviously need to be online to do the setups after the installation of your minimal or full package of nethunter.


user=kali (to log as custom user, you'll need to modify the login scripts)

this is a set of little scripts helping to install the minimal or full package of nethunter in termux
depending on your will.

So, follow the steps to install nethunter in termux...

1) open termux and make sure you are in the home directory

  #verify

     pwd

you should see: /data/data/com.termux/files/home

  #go to the home directory if you are not in /data/data/com.termux/files/home

     cd ~

2) install wget ; proot ; tar

#update apt

     apt update

#install wget

     apt install wget 

#install proot 

     apt install proot 

#install tar

     apt install tar


3) download a minimal or full nethunter image depending on your arch

#verify your arch

    getprop ro.product.cpu.abi

#for armf (armeabi or armeabi-v7a)

minimal

    wget https://build.nethunter.com/kalifs/kalifs-latest/kalifs-armhf-minimal.tar.xz

full

    wget https://build.nethunter.com/kalifs/kalifs-latest/kalifs-armhf-full.tar.xz

#for arm64 (arm64-v8a)

minimal

    wget https://build.nethunter.com/kalifs/kalifs-latest/kalifs-arm64-minimal.tar.xz

full

    wget https://build.nethunter.com/kalifs/kalifs-latest/kalifs-arm64-full.tar.xz

#unknown archs are not supported

4) download the locallinstall or localinstall_full script and add permission

  #download

     wget https://raw.githubusercontent.com/ZeeFromBzv/offline_termux_nethunter_install/main/localinstall

or
    
     wget https://raw.githubusercontent.com/ZeeFromBzv/offline_termux_nethunter_install/main/localinstall_full
  
  #add permission

     chmod +x localinstall

or

     chmod +x localinstall_full

5) execute the localinstall or localinstall_full script

       ./localinstall

or

       ./locallinstall_full

6) download the add_repos script and add permission

  #download

     wget https://raw.githubusercontent.com/ZeeFromBzv/offline_termux_nethunter_install/main/add_repos

  #add permission

     chmod +x add_repos

7) execute the add_repos scrip

        ./add_repos

8) start nethunter (it'll start as root)

by

     nethunter

or

     nh

9) install the repositories and update apt

install

        apt install ./kali-archive-keyring_2020.2_all.deb

update

        apt update

10) install sudo

        apt install sudo

11) add kali user

        adduser kali

11) add root and kali to the sudoers

        echo "root ALL=(ALL:ALL) ALL 
kali ALL=(ALL:ALL) ALL" > /etc/sudoers

12) exit from nethunter

        exit

13) start nethunter (you should now be logged as kali)

by        

      nethunter

or

      nh

14) install a desktop enviroment depending on your preferences and remove it's power manager plugins (choose one and install it)

#gnome

     sudo apt install kali-desktop-gnome

and

     sudo apt-get remove gnome-power-manager

#xcfe

     sudo apt install kali-desktop-xfce

and

     sudo apt-get remove xfce-power-manager-plugins

#kde
     sudo apt install kali-desktop-kde

and

     sudo apt-get rmove kde-power-manager


15) install tightvncserver

     sudo apt install tightvncserver

#start a vnc session, for the first time, it'll ask you to enter a password, this password will be your vnc password so, don't forget it and dont use a weak password

     tightvncserver -geometry (x)x(y)

(x)x(y) will be replaced by the resolution of your screen eg: 2220x1080

#you can also start a vnc session with tightvncserver's default resolution

     tightvncservser

#now, you have kali nethunter installed in your termux, so... enjoy !

# to login in nethunter

use
     nethunter

or

     nh

#to logout, use
     
     exit

#to start a vnc session in nethunter

    tightvncserver -geometry (x)x(y)

or

     tightvncserver
