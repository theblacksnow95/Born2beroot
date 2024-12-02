# BORN2BEROOT
## This repository is part of the B2BR project part of the common core of the ecole42 Lausanne. The goal is to lear how to use a Virtual Machine and personalize it to be able to work with it.
The **Born2beRoot** project is part of the curriculum for the 42 Network and is designed to introduce students to system administration and server configuration. Through this project, students gain hands-on experience setting up and managing a virtual server while adhering to specific technical guidelines. It focuses on understanding operating system fundamentals, system security, and network management, providing a strong foundation for managing Linux-based systems.

The primary goal of the project is to configure a Debian- or RockyOS-based server using virtualization tools like VirtualBox or UTM. Students are tasked with configuring a secure and stable system that includes SSH access, user management policies, firewall rules, and system monitoring tools. Additionally, the project emphasizes the importance of adhering to strict security protocols, such as enforcing strong password policies, configuring sudo access, and managing logging and system monitoring.

This project not only introduces you to essential Linux commands and services but also challenges you to implement and document your configuration choices. By the end of Born2beRoot, you will have developed a deeper understanding of system administration, gained practical experience with server management, and cultivated skills essential for a career in IT or cybersecurity.
## Practical guide to the proyect.

## 1. Install the virtual machine

### This must be handled using VirtuaBox (you can download it [here](https://www.virtualbox.org/wiki/Downloads))
- You can also use the terminal command:
- `sudo apt update -y`
- `sudo apt upgrade -y`
- `sudo apt-get install VirtualBox`

Once is installed we can download the iso image, for this example I have downloaded Debian iso v24
- Use the next [link](https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/) to download the version needed. It spell like this debian-x.x.x-amd64-netinst.iso
- Now we open VirtualBox and create the image
- Select the folder and set a name and click next
![image ](https://github.com/user-attachments/assets/12f18faa-b5d8-4828-a3fd-e17310dec9c2)
- Leave the memory at 1024MB and 1 core
![image](https://github.com/user-attachments/assets/d34850b2-4ebd-4753-88b2-94681f680cac)
- Set the memory of the disk to 12GB
![image](https://github.com/user-attachments/assets/72267ad4-df2b-423d-b561-9eacb422d7de)
- Finish
- Open the settings of the VM we just created
- Go to storage and choose the ISO from debian we have just downloaded on the Controller IDE option
![image](https://github.coBORN2BEROOT
m/user-attachments/assets/514b1e7e-8c66-42f8-aeba-7a3292057acf)
![image](https://github.com/user-attachments/assets/7e5f1d1c-9c8a-4594-9f51-c0ee6d93d90c)
- Click ok
- Now we can start the installation process
### Launch the VM and start the installation:
- Here we will see the next image from wich we have to choose the 'install' option 
![image](https://github.com/user-attachments/assets/b9292ddb-b3b8-4333-953a-9bb2026dd431)
- Select your prefered language and the region
![image](https://github.com/user-attachments/assets/fe093307-5fcb-4082-9ac6-420b51cedd69)
![image](https://github.com/user-attachments/assets/9caac38b-e577-4b39-a89f-932b583500d3)
- Select the locale as US
![image](https://github.com/user-attachments/assets/0d0288d8-d4cd-452d-9e0f-44b85f03ebcc)
- Once this is done it will start the process and it will ask you to set the host name, remember to use your login42 style
![image](https://github.com/user-attachments/assets/de7b86e7-7be3-4a96-9950-74b06c4fe378)
- Leave the domain in blank and continue
- Set the password for your server. Remeber this as you will need it for the whole process
- You will have to repeat your password to confirm it
![image](https://github.com/user-attachments/assets/8c916197-d344-46bd-b3b9-af62d5d99742)
- Set the name of your user. This shoould be your login
![image](https://github.com/user-attachments/assets/1d03466f-41da-4f7a-afb9-23d86f789920)
- Set the password for your user. Save it for the whole process
![image](https://github.com/user-attachments/assets/aec4096a-6e8f-4ca8-a47c-800332e54ad5)
- You will have to repeat it to confirm it
### LVM instalation
- Now it will ask you to choose the partition level, we will choose the Guided - Use entire disk and set up encrypted LVM
![image](https://github.com/user-attachments/assets/7957d8a5-cd14-45da-bef5-f2c6334cd09a)
- Now we choose our disk 
![image](https://github.com/user-attachments/assets/0831c2c4-a469-4e6b-ab9a-1e535be7cb73)
- Choose the last option to create the partitions
![image](https://github.com/user-attachments/assets/238b5aac-4cce-4ef0-b11b-936dd93bc0c4)
- Select "yes" to write changes to disk
![image](https://github.com/user-attachments/assets/e591c5ff-c3f4-4a61-b8c2-174a653eb2de)
- You can cancel the formatting of the volume
![image](https://github.com/user-attachments/assets/98f4ead1-c3e5-4f05-9f5c-d8d985d02c65)
- Set the encrpyption passphrase and repeat it to confirm it
![image](https://github.com/user-attachments/assets/86e88bbb-4aa7-4d8d-966b-04d9a3713381)
- Set the space to "max" and continue
![image](https://github.com/user-attachments/assets/a33f5500-f06b-49ff-b597-e5732c122d1e)
- Select "Finish partitioning and write changes to disk"
![image](https://github.com/user-attachments/assets/a9494a53-7d36-4dff-910d-7fd90cab62b1)
- Select <yes> to write changes to disk and set the partitions
![image](https://github.com/user-attachments/assets/245ea309-eadb-463e-8034-43594750e70c)

### Basic system and Grub installation
- Once the previous is done it will continue with the basic system installation

![image](https://github.com/user-attachments/assets/870ab765-6a25-41cb-b519-986c82dff927)

- Select "no" here

![image](https://github.com/user-attachments/assets/9132141b-3e41-413e-8fe2-4cf838d2c674)

- Select "deb.debian.org"
![image](https://github.com/user-attachments/assets/0ab410a8-8c8f-4d7a-b248-016a98af4e16)
- Leave in blank the proxy
![image](https://github.com/user-attachments/assets/0fd4efc6-2f46-48b8-8e27-7d9632e62652)
- Wait for the installation
- Select "no" for the popularity contest
![image](https://github.com/user-attachments/assets/f68ea609-38ac-4abd-a210-b91f901794ff)
- Use space to deselect the "ssh" and "standard system utilities"
![image](https://github.com/user-attachments/assets/cf761d23-3ff0-4917-a4b8-e90cdbc5445d)
- When asked about the GRUB select "yes" to install it at the primary drive

![image](https://github.com/user-attachments/assets/a2ab6210-84a2-45ff-a8dc-f88ec61dfc16)

- Select your drive

![image](https://github.com/user-attachments/assets/51a600a8-ed6a-4c25-98ee-e50906826a2a)

- Select "Continue" to reboot the system and lauch the VM

![image](https://github.com/user-attachments/assets/b9908381-3f16-40fa-9aa4-448654361b45)

## Virtual Machine configuration
### Sudo installation and strict configuration
On the CM restart it will ask for your passphrase and your login credentials
Once they are introduced you will be on your shell
Check your partitions usign th lsblk command
- `lsblk`

![image](https://github.com/user-attachments/assets/7d996153-8af8-4c75-9027-05d40000b416)


![image](https://github.com/user-attachments/assets/0de6806f-88a7-49b3-b0ea-342ac8ff06b9)

Change to the root user to be able to install packages using the su command
- `su - `

Introduce your host password to change to the root superuse
Use the next commands to update the package list and upgrade it:

- `apt-get update -y`
- `apt-get upgrade -y`

Install sudo usign the next command
- `apt-get install sudo`

Install the vim editor (just if you want, you can also use nano to edit files)
- `apt-get install vim`

Now that sudo is installed we have to add our user to the sudo group and to the sudoers file
To modify the sudoers file we use the visudo command on the root user:
- `sudo visudo`
- look for the line "# user privilege specification" and add the next line
- `<your_username>  ALL=(ALL) ALL`
![image](https://github.com/user-attachments/assets/96a07dd2-d581-4bfc-b55f-f47ec34d9082)

This will grant all the privileges to your user and you can use sudo with it.
Press ctrl+x then "y" and "enter" to save the changes
To add to a group we use the usermod command with the -aG flag, this means --append --group:
- `sudo usermod -aG <group> <username>`

To check the sudo group and confirm the change was correct:
- `sudo getent group sudo` 
### Now we can configure the sudo strict requisites:
We need to add to the sudoers file the requisites, we can do this in the first part of the file were the "Defaults" requisites are located
The ones we will be using will be the next:
- Defaults      requiretty
- Defaults      badpass_message="Wrong password, please try again"
- Defaults      passwd_tries=3
- Defaults      secure_path="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/snap/bin"
- Defaults      logfile="/var/log/sudo/sudo.log"
- Defaults      log_input, log_output

![image](https://github.com/user-attachments/assets/e8503b87-5dd9-4ff2-bce2-ac2d5d3debe5)

Save this changes and we can create the log file in the "/var/log/sudo/" directory
- `cd /var/log`
- `mkdir sudo`
- `touch sudo.log`

Use a sudo command to verify that the log is working and then check the log file using cat
- `sudo getent group sudo`
- `cat /var/log/sudo/sudo.log`

You should see the last used command with sudo:

![image](https://github.com/user-attachments/assets/6780c1b6-b2be-4d8b-8cbf-efbcb788ae69)

### Strong password configuration
To be able to have a secure password policy we will install the libpam-pwquality package
- `sudo apt install libpam-pwquality -y`

Once installed we will modify the common-password file at the /etc/pam.d/common-password using Vim
- `sudo vim /etc/pam.d/common-password`

We will the next text after the "# here are the pre-package modules (the "Primary" block) after the "retry=3"
- minlen=10 lcredit=-1 ucredit=-1 dcredit=-1 maxrepeat=3 difok=7 reject_username enforce_for_root

We can also use the pwquality.config file
- `sudo vim /security/pwquality.config`

And set all the values needed in this file, it does the same and we can use both.

Save the file and exit
Now we hace to modify the login defs to set the password expiry dates
This we can do using the login.defs file and look for the "#password aging controls"
- `sudo vim /etc/login.defs`

![image](https://github.com/user-attachments/assets/346a2546-0e0a-42a9-b42a-a0c0e46437fd)

The result must be like this:

![image](https://github.com/user-attachments/assets/b2464753-c401-4d07-bf5a-79acb4e27040)

Check yur user or the root aging with the chage command
- `sudo chage -l <your_user>`

You will see that the numbers have not changed, in this case use the chage command to modify them
- `sudo chage -M 30 <login>` for the maxdays
- `sudo chage -m 2 <login>` for the mindays
- `sudo chage -W 7 <login>` for the warning days










