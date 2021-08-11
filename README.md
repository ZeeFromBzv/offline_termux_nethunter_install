#local_termux_nethunter_install
user=kali (to use custom users, you'll need to modify the login scripts)

this is a set of little scipts helping to install the minimal package of nethunter in termux

So, follow the steps bellow to install nethunter in termux

1) open termux and make sure you are in the home directory

  #verify

     pwd

  #go to the home directory

     cd ~

2) install wget ; proot ; tar

     apt update
     apt install wget
     apt install proot
     apt install tar

3) download a minimal nethunter image depending on your arch

  #to see the arch

uname -m

  #for armf

wget https://build.nethunter.com/kalifs/kalifs-latest/kalifs-armhf-minimal.tar.xz
  
  #for arm64

wget https://build.nethunter.com/kalifs/kalifs-latest/kalifs-arm64-minimal.tar.xz

  #unknown archs are not supported

4) download the locallinstall script and add permission

  #download

wget https://raw.githubusercontent.com/ZeeFromBzv/offline_termux_nethunter_install/main/localinstall
  
  #add permission

chmod +x localinstall

5) execute the localinstall script

./localinstall

6) download the add_repos script and add permission

  #download

wget https://raw.githubusercontent.com/ZeeFromBzv/offline_termux_nethunter_install/main/add_repos

  #add permission

chmod +x add_repos

7) execute the add_repos scrip

./add_repos

8) start nethunter (it'll start as root)

nethunter

or

nh

9) install the repositories and update apt

apt install ./kali-archive-keyring_2020.2_all.deb && apt update

10) install sudo

apt install sudo

11) add kali user

adduser kali

11) add root and kali to the sudoers

echo "root ALL=(ALL:ALL) ALL" > /etc/sudoers && echo "kali ALL=(ALL:ALL) ALL" > /etc/sudoers

12) exit from nethunter

exit

13) start nethunter (you should now be logged as kali)

nethunter

or

nh

14) install a desktop enviroment depending on your preferences and remove it's power manager plugins

#gnome

sudo apt install install kali-desktop-gnome && sudo apt remove
