# Yiimp_install_script (update June, 2022)

TUTO Youtube (16.04 / 18.04 - Without SSL) : https://www.youtube.com/channel/UCXdH6xeRM1v4uebHFVJaKww

Official Yiimp (used in this script for Yiimp Installation): https://github.com/MonkeyD-Core/yiimp-main

Original Yiimp Installer : https://github.com/cryptopool-builders/multipool_original_yiimp_installer


***********************************

## Install script for yiimp on Ubuntu Server 16.04 / 18.04 (use Tpruvot's Yiimp)

USE THIS SCRIPT ON FRESH INSTALL UBUNTU Server 16.04 / 18.04 !

Connect on your VPS =>
- apt update
- apt upgrade
- reboot
- adduser pool (pool it's just an example...)
- adduser pool sudo
- su - pool
- exit 
- su - pool
- sudo apt -y install git
- git clone https://github.com/MonkeyD-Core/yiimp-main
- cd yiimp-main/installer/
- bash install.sh (DO NOT RUN THE SCRIPT AS ROOT or SUDO)
- At the end, you MUST REBOOT to finalize installation...

Finish !
- Go http://xxx.xxx.xxx.xxx or https://xxx.xxx.xxx.xxx (if you have chosen LetsEncrypt SSL). Enjoy !
- Go http://xxx.xxx.xxx.xxx/site/myadmin or https://xxx.xxx.xxx.xxx/site/myadmin to access Panel Admin

If you are issue after installation (nginx,mariadb... not found), use this script : bash install-debug.sh (watch the log during installation)


###### :bangbang: **YOU MUST UPDATE THE FOLLOWING FILES :**
- **/var/web/serverconfig.php :** update this file to include your public ip (line = YAAMP_ADMIN_IP) to access the admin panel (Put your PERSONNAL IP, NOT IP of your VPS). update with public keys from exchanges. update with other information specific to your server..
- **/etc/yiimp/keys.php :** update with secrect keys from the exchanges (not mandatory)
- **If you want change 'AdminPanel' to access Panel Admin :** Edit this file "/var/web/yaamp/modules/site/SiteController.php" and Line 11 => change 'AdminPanel'


###### :bangbang: **IMPORTANT** : 

- The configuration of yiimp and coin require a minimum of knowledge in linux
- Your mysql information (login/Password) is saved in **~/.my.cnf**

***********************************

###### This script has an interactive beginning and will ask for the following information :

- Server Name (no http:// or www !!!!! Example : crypto.com OR pool.crypto.com OR 80.41.52.63)
- Are you using a subdomain (mypoolx11.crypto.com)
- Enter support email
- Set stratum to AutoExchange
- Your Public IP for admin access (Put your PERSONNAL IP, NOT IP of your VPS)
- Install Fail2ban
- Install UFW and configure ports
- Install LetsEncrypt SSL

***********************************

**This install script will get you 95% ready to go with yiimp. There are a few things you need to do after the main install is finished.**

While I did add some server security to the script, it is every server owners responsibility to fully secure their own servers. After the installation you will still need to customize your serverconfig.php file to your liking, add your API keys, and build/add your coins to the control panel. 

There will be several wallets already in yiimp. These have nothing to do with the installation script and are from the database import from the yiimp github. 

If you need further assistance we have a small but growing discord channel at https://discord.gg/zcCXjkQ

If this helped you or you feel giving please donate : 
- BTC Donation : 1NQ46aP2wgotA9dJs4U8jBv4a1cR9qF8DA
- ETH Donation : 0x0a61ec3546ff49bd3b9cb6a5d08397fb32ba1b91
- LTC Donation : LWxo5EXMJnrYGokcjC4K3RJ3sEcwCTGrw8
- DOGE Donation : DK8oQXVSsXCTu6vRhiAn8waF3v3hVsNg9G
- TRX Donation : TMdaz1ZSRQACYaVZMAC4F6nsQsuYXz54Hc
- TRC20 USDT Donation : TMdaz1ZSRQACYaVZMAC4F6nsQsuYXz54Hc
- ERC20/BEP20 USDT  : 0x0a61ec3546ff49bd3b9cb6a5d08397fb32ba1b91
