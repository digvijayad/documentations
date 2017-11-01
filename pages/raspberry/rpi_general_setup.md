---
title: General Setup ( Rpi )
keywords: Setup, General
summary: Follow these instructions to setup the PI just after a fresh installation of Operating System.
sidebar: raspberry_sidebar
permalink: /rpi_general_setup.html
folder: raspberry
---

## Information about the documentation: 
```$ ``` followed by words means it is a command you have to type. Anything bellow it will be information given by command line. 

## Username and Password
The default username of the pi: ```pi``` and the default password is: ```raspberry```

Change the password to ```AsuBotics```
1. Open Terminal 
1. Type the command ```passwd```, and enter the current password, then choose the new password. 

Example:

```
$ passwd 
Changing password for ubuntu.
(current) password: 
(new) password: 

```

## Installing important softwares
We need to install ```nbtscan``` and ```nmap```. 
Type the following command and follow rest of the prompt given. 
```
$ sudo apt install nbtscan nmap
```

## Setup Hostname For SSH
The next thing we need to do is setup the host name of the pi so that we ssh into the Pi without worrying about it's ip address.
To do this we need to call a script every time Pi reboots which will update our host file with our latest ip address. 

1. First we will create a back up of the host file, so that if anything goes wrong, we can always restore it. 
```
$ sudo cp /etc/host /etc/hosts.bk
```
This should create a new file name hosts.bk with the content of our original hosts file. 

1. Now we will create a new file named updatehost, which will update our host file 60 seconds after the PI is restarted, and save it to ```/usr/local/bin/ fo``` folder.

```
$ sudo nano /usr/local/bin/updatehost
```
Then paste the following content inside. 
```
#/usr/local/bin/updatehost
#hosts.bk is the original hosts file
sleep 60s
cd /etc
rm -f /tmp/host1
nbtscan 10.221.55.0/24 |  cut  -c1-34| tr "A-Z" "a-z"| egrep 10.  >> /tmp/host1
nbtscan 10.222.55.0/24 |  cut  -c1-34| tr "A-Z" "a-z"| egrep 10. >> /tmp/host1
nbtscan 192.168.0.0/24 |  cut  -c1-34| tr "A-Z" "a-z"| egrep 192. >> /tmp/host1
nbtscan 10.217.56.0/24 |  cut  -c1-34| tr "A-Z" "a-z"| egrep 10. >> /tmp/host1
cp -v /tmp/host1 /etc/hosts
cat /etc/hosts.bk >> /etc/hosts
cat /etc/hosts

```