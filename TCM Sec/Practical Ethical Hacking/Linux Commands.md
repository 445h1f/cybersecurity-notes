*For command explanation:* https://explainshell.com/
*or* **man \<command>**
* * *

# Admin commands: 

- ## sudo
To run commands with priviliged (root) mode.
**Usage: sudo <command_name>**

**Normal:**
![0166e353de62b9bf471ebaf9883a182f.png](../_resources/0166e353de62b9bf471ebaf9883a182f.png)
**Sudo:**
![6d69761d8cff4298733ee5ef9f3247f8.png](../_resources/6d69761d8cff4298733ee5ef9f3247f8.png)

**Run all commands in root by switch to root mode using:**
 **Command: sudo su -**
 su: superuser
 ![e22d7f12309b57d171eef5b71bf09565.png](../_resources/e22d7f12309b57d171eef5b71bf09565.png)

- ## passwd
Change password of user

- ## adduser
creates new user.
**Usage: sudo adduser  \<new_user>**

- ## su 
Switch to user
**Usage: su \<user>**

- ## sudo -l
Which commands can be ran
![8169e4a2e0597275b8d983e6357bdf21.png](../_resources/8169e4a2e0597275b8d983e6357bdf21.png)

# File Navigation:


- ## cd
Change to directory
**Usage:  cd <dir_name>** 
**cd ..** : go one level back to dir

- ## mkdir
Create new directory
**Usage: mkdir <dir_name>**

- ## rmdir
Remove/delete directory
**Usage: rmdir <dir_name>**

- ## ls
 List contents of directory
 **Usage: ls**
 Use **ls -la**  for more info and include hidden files
 
- ## cp
Copy file
**Usage: cp <file_name> <copy_location>**

- ## mv
Move/rename file
**Usage: mv <file_name> <new_location>**
To rename insert new file name in place of new location

- ## locate
To search/locate file
**Usage: locate**
To update file locate database:  **sude updatedb**

- ## grep
To narrow down search of text in file
**Usage: grep 'keyword' \<file>**
![0b6bd149f5a224e59bac7184cb6eecfb.png](../_resources/0b6bd149f5a224e59bac7184cb6eecfb.png)

> ## file permissions:
r: read (4)
w: write (2)
x: execute (1)

3 groups: owner, group, current_user

**To change permissions:**
**chmod** comnand is used

First way:
**chmod +{rwx}**: add r,w,x permission

Second Way (octal):
**chmod 777**: rwx for all 3 groups

- r = 4
- w = 2
- x = 1
- rw = 4+2
- rwx = 7



# Networking:

- ## ip a [colorful] (old- ifconfig)
to show network info like ip etc.
![673a5c682b30e2ad639d474c17855d07.png](../_resources/673a5c682b30e2ad639d474c17855d07.png)

- ## iwconfig
to show wireless connections.
![a768768e1440da1a763188f5480c5e95.png](../_resources/a768768e1440da1a763188f5480c5e95.png)

-## ip n | arp -a
shows what ip address is asscoiated with what mac address.
![977b82d90e3cde5de1ad309431e3062a.png](../_resources/977b82d90e3cde5de1ad309431e3062a.png)

-## ip r | route
to know routing table
![67b30add0de49b1e30773e9570313eb5.png](../_resources/67b30add0de49b1e30773e9570313eb5.png)

- ## ping \<ip> or \<address>
to know connectivity with ip
![3e39b6b2bc36d86467565eb9794ecb10.png](../_resources/3e39b6b2bc36d86467565eb9794ecb10.png)

- ## netstat

# View, Create, Edit files:
- ## echo "content" > file
write content in file
**>** for overwrite
**>>** for append
![96f8c4e00a13aea5f45b8c7f98aaacc7.png](../_resources/96f8c4e00a13aea5f45b8c7f98aaacc7.png)

- ## touch \<file>
to create empty file
![891d2c5a9899b2b594897830091863ce.png](../_resources/891d2c5a9899b2b594897830091863ce.png)

- ## cat \<filename>
to create, view and concatenate files
![0fce8f66470ef6a5f09b27cc3329ce51.png](../_resources/0fce8f66470ef6a5f09b27cc3329ce51.png)
![113e358b958198536db499a2bc53c1b7.png](../_resources/113e358b958198536db499a2bc53c1b7.png)

- ## nano \<filename>
terminal editor for creating and editing file
![9646be3318606a40cf538bda2f76e878.png](../_resources/9646be3318606a40cf538bda2f76e878.png)
![e9621ef255d73b85135d10f357e003a8.png](../_resources/e9621ef255d73b85135d10f357e003a8.png)

- ## mousepad \<filename>
to view, edit file in mousepad (similar to notepad)
![8bc61dfd8858c3a03ce01b3df986e727.png](../_resources/8bc61dfd8858c3a03ce01b3df986e727.png)



# Start / Stop services:
- ## start/stop apache web server
### sudo service apache2 start/stop
![45b7bd0ce364debe6983d06cf0020710.png](../_resources/45b7bd0ce364debe6983d06cf0020710.png)
![9bc36750f7a4c65e3b05a6d868129db0.png](../_resources/9bc36750f7a4c65e3b05a6d868129db0.png)

### direct from where files are served
![b095878a7271e8a2744c846ed422e89e.png](../_resources/b095878a7271e8a2744c846ed422e89e.png)
![908ebe9772bbfd79aafb7b06b939e73e.png](../_resources/908ebe9772bbfd79aafb7b06b939e73e.png)
![53b89952bb52fe96f650d7d4a040d952.png](../_resources/53b89952bb52fe96f650d7d4a040d952.png)
https://www.cyberciti.biz/faq/star-stop-restart-apache2-webserver/

- ## to start python web server
### python3 -m http.server 80 
80 is port number
![a8cd42b82900fe57e7d5b1d54af318bf.png](../_resources/a8cd42b82900fe57e7d5b1d54af318bf.png)
![0bae52b25ac4f6ad6758606690496928.png](../_resources/0bae52b25ac4f6ad6758606690496928.png)

- ## sudo systemctl <start/stop/status> \<service>
![b7c17894eba9f636c6e1e053c33d7552.png](../_resources/b7c17894eba9f636c6e1e053c33d7552.png)
![47d920aeb4b85a33fa4498e82fcfeb85.png](../_resources/47d920aeb4b85a33fa4498e82fcfeb85.png)


# Installing / Updating apps:
- ## Update (root user may required)
![c92c1335518aade1aca5d918da0fd88d.png](../_resources/c92c1335518aade1aca5d918da0fd88d.png)

- ## Install
![b250a3660174af8e5df8d65334339a65.png](../_resources/b250a3660174af8e5df8d65334339a65.png)

# Installing via Git:
### in (/opt) directory
![caa6764ee15e04354a83605bd0fb5269.png](../_resources/caa6764ee15e04354a83605bd0fb5269.png)
![6cc2c4355c4a50399d3864f480e686a3.png](../_resources/6cc2c4355c4a50399d3864f480e686a3.png)
