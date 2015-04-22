# lookoutdoor
Lookoutdoor is a custom made Digital Signage

#Requirements
* Tiny PC, I used Fit2PC http://www.fit-pc.com (You can use any small PC, Raspberry Pi, etc)
* HDMI ready TV or Monitor

#Installation
Installing Look Outdoor Clients

1. Install Ubuntu 10.04
2. Install Intel 500 Graphic Drivers 
	#sudo add-apt-repository ppa:gma500/ppa && sudo aptitude update && sudo aptitude install poulsbo-driver-2d poulsbo-driver-3d poulsbo-config
3. Reboot
4. Install mplayer
 	#sudo apt-get install mplayer
5. Install wvdial and (tcl, usb-modeswitch –optional if it sees a modem)
#sudo apt-get install wvdial
6. edit wvdial.conf 
7. Set pppd permission.
	#sudo chown root:dip /usr/sbin/pppd
	#sudo chmod 4754 /usr/sbin/pppd
	#sudo chmod 777 /etc/ppp/pap-secrets 
	#sudo chmod 777 /etc/ppp/peers
Open terminal.
Open nautilus by typing "sudo nautilus".
Enter password when prompted.
When the file browser opens, go to the folder usr, then to folder sbin,where you will find the executable program pppd.
Right click on ppd, go to properties, then go to permissions tab under properties.
There, you will find an option for allow executing file as a program.
8. create Global video source
	#mkdir /opt/lookoutdoor/video
9. Install sshd
#sudo apt-get install ssh
10. Install ssh keys add publish to server
	#ssh-keygen -t dsa
	#scp ~/.ssh/id_dsa.pub server:.ssh/authorized_keys2
	#ssh-agent sh -c 'ssh-add < /dev/null && bash'
11. Test and set startup scripts
