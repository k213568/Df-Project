# Df-Project
Submit the experiment report using the following site. This will be considered as your class project.
https://computersecuritystudent.com/cgi-bin/CSS/process_request_v3.pl?HID=310ac205e9fd07c189cdc417fb336a74&TYPE=MAIN

Forensics Experiment:
- Data Hiding
- Lime Forensics (Lesson 1), 
- LoseBuntu(Experiment1, 2 and 3)

Perform Security tool Lab
- SQL injection



# Report 



DF FINAL PROJECT  
              
    SUBMITTED BY : 

NABIHA FATIMA   -k213634
SEHER SIDDIQUE -k213568

SUBMITTED TO : 

MS. MAFAZA MOHI
SIR SAAD JAVED









TABLE OF CONTENT                                                      
 
Executive Summary ……………………………………………………………………….. 3
Introduction ……………………………………………………………………………………3
Methodology ……………………………………………………………………………………4
Data Hiding Techniques ……………………………………………………………………6
Lime Forensics …………………………………………………………………………………14
SQL Injection…………………………………………………………………………………….21
LOS BUNTU ……………………………………………………………………………………..35
        Lesson 1………………………………………………………………………………………35
        Lesson 3………………………………………………………………………………………46
Acknowledgement ………………………………………………………………………………56





















Executive Summary:
The field of digital forensics plays a crucial role in uncovering and analyzing digital evidence in today's technologically advanced world. In this digital forensics project, we undertook a series of experiments aimed at exploring various aspects of data hiding, Lime Forensics, and LoseBuntu. These experiments allowed us to delve into different techniques and tools used in the field, enabling us to better understand and address the challenges associated with digital investigations.

Introduction:
The purpose of digital forensic investigations is paramount in today's technologically advanced world. It involves the meticulous extraction, preservation, and analysis of data from diverse digital devices, ranging from computers to mobile phones and other digital storage media. However, criminals and malicious actors constantly seek ways to hide data and obfuscate their activities using sophisticated techniques, thereby presenting significant challenges for investigators.

Methodology:
The methodology employed in this digital forensics project encompassed a comprehensive approach involving literature review, practical experiments, and case studies to investigate the influence of data hiding techniques, Lime forensics, LosBuntu, and SQL injection on digital forensic investigations.
To begin, a thorough literature review was conducted to gather knowledge and insights into the latest advancements and best practices in digital forensics. This review served as a foundation for the subsequent experiments and case studies.

The practical experiments comprised a hands-on exploration of various digital forensic tools, including MetaSploit and SQL injection. These tools were utilized to identify and extract hidden data, enabling the evaluation of their efficacy in uncovering concealed information. Furthermore, dedicated steganography tools like OpenStego and Steghide were employed to assess the effectiveness of data hiding techniques. Virtual machines created with VirtualBox were utilized to simulate diverse scenarios and investigate the impact of the aforementioned techniques and tools.

Real-world scenarios involving the implementation of data hiding techniques were analyzed to gain insights into their practical implications. While the original plan was to employ commercial forensic tools like Cellebrite UFED and Magnet AXIOM to extract digital evidence from various devices, time constraints necessitated the use of alternative methods. Therefore, the focus shifted towards utilizing Bmap, a Linux command that displays the allocation of blocks in a file system, to detect the presence of hidden data.

Lime forensics was investigated by leveraging the Lime kernel function "insmod lime -2.6.24-16" to extract relevant data. Experiments were conducted using the LosBuntu Linux distribution to assess its suitability and effectiveness in digital forensic investigations.

Moreover, SQL injection attacks were performed on a web application utilizing tools such as DWVA. This allowed for an exploration of the impact of SQL injection techniques on digital forensic investigations, enabling an understanding of the challenges and potential ramifications associated with such attacks.

The practical experiments provided valuable insights into the effectiveness of various techniques and tools employed in digital forensic investigations. These findings hold significance for forensic investigators, law enforcement agencies, and organizations involved in cybersecurity, enabling them to enhance their methodologies, processes, and strategies to effectively combat digital crimes and preserve the integrity of digital evidence.










FORENSICS EXPERIMENTS : 
1. DATA HIDING TECHNIQUES :
INTRODUCTION:

Bmap is a tool for data hiding that can use empty space in blocks to conceal data. It has many capabilities that the computer forensics and security communities will find fascinating.

STEP NO 01:
Instructions:
1.	Select BackTrack5R1 VM
2.	Click Edit virtual machine settings



  

STEP NO 02:
Instructions:
1.	Login: root
2.	Password: whatever you changed it to.

 


STEP NO 03:
Bring up the GNOME
 Instructions:
1.	Type startx


 
STEP NO 04:

Start up a terminal window
Instructions:
1.Click on the Terminal Window


STEP NO 05:

Navigate to bmap
Instructions:
1. In your Firefox browser navigate to the following address	http://dl.packetstormsecurity.net/linux/security/bmap-1.0.17.tar.gz
2. Select the Save File Radio Button
3. Click the OK Button



 
STEP NO 06:
Change the current directory to /opt/bmap and unzip and untar the file using these commands

Instructions:
1.	gunzip bmap-1.0.17.tar.gz
2.	tar xovf bmap-1.0.17.tar
 

STEP NO 07:

Change the directory to /var/tmp, create a test file and store some text in the file. Now check the slack space using the following command bmap --mode slack test.txt
 

STEP NO 08:

Now to hide the data in the slack space using the command "<text>" | bmap --mode putslack <name of file> . To ensure that the data is in the slack space we will check the file and as a proof it will not show the hidden data until the file is read using bmap









STEP NO 09:
Delete the test file using rm command and view the file with bmap by using the command bmap --mode slack test.txt  to ensure that the data in the slack space is still available despite the fact that the file is deleted. 

PROOF OF THE LAB



CONCLUSION :

In this lab, we attempted to show how simple it is to conceal data in a file's slack area.


2. LIME FORENSICS:

INTRODUCTION:
In today's digital era, information technology has evolved into a need. A lot of the information is private. Security is therefore also crucial. Although Metasploit is one of the frameworks that penetration testers frequently use to audit or test the security of a computer system lawfully, it is still possible that Metasploit might also be used illegally
DOWNLOADING AND CONFIGURATION:
Metasploitable Project: Lesson 1: Downloading and Configuring
STEP NO 01:
Logging into Metasploitable
Instructions
Username: msfadmin
Password: msfadmin 

 
 STEP NO 02:
    Check The IP Address
Instructions:
ifconfig -a
Note(FYI):
This is the IP Address of the Victim Machine.
My IP Address is 192.168.1.112.
Record your IP Address.


STEP NO 03:
Become Root
Instructions:
sudo su -
Supply The Password




STEP NO 04:
Looking for kernel build directory
Instructions:
cd /lib/modules/`uname -r`
ls -la
*special kernel files, libraries, and utilities which is located in the following directory:
/lib/modules/`uname -r`/build




STEP NO 05:
Installing kernel headers
Instructions:
apt-cache search `uname -r` | grep header
apt-get install linux-headers-2.6.24-16-server
Do you want to continue [Y/n]? Y





STEP NO 06:
Verifying the build directory exists
Instructions:
ls -ld /lib/modules/`uname -r`/build
Download Lime Forensics
Instructions:
mkdir -p /var/tmp/tools
cd /var/tmp/tools
wget–http://lime-forensics.googlecode.com/files/lime-forensics-1.1-r14.tar.gz
ls -l lime-forensics-1.1-r14.tar.gz


STEP NO 07:
Un-tar Lime Forensics
Instructions:
tar zxovf lime-forensics-1.1-r14.tar.gz

STEP NO 08:
Compile Lime Forensics
Instructions:
cd src
make



STEP NO 08:
Create Lime Forensics Image
Instructions:
mkdir -p ../../images
insmod lime-2.6.24-16-server.ko "path=/var/tmp/images/ram.lime format=lime"
ls -l ../../images/ram.lime



STEP NO 09:
Proof of Lab
ls -l /var/tmp/images/ram.lime
date
echo "Your Name"


CONCLUSION :
We have accomplished the following in this lab:
Prepared to construct the Ubuntu 8.04 virtual machine's kernel source.
Download Lime Forensics
Compile Lime Forensics.
Capture an Ubuntu 8.04 image using Lime Forensics


3. SQL INJECTION:

STEP NO 01:
First of all we have we will use the chown command to change the ownership of the directory or the file used

Instructions:
sudo chown -R www-data:www-data /var/www/html
sudo chown -R 755 /var/www/html
sudo service apache2 restart
sudo systemctl restart apache2
ifconfig -a(It provides the IP address) 

STEP NO 02:
We will direct to the directory where the config file is saved
As the config file is initially in html so we will copy the config file to the dwva folder to make a duplicate file and after doing do we will move the file back to html
Instructions:
cd /var/www/html/
cp config/config.inc.php.dist config/config.inc.php


STEP NO 03:

Now we will open the config.inc.php folder. I've kept everything by default because there is no need to do any change.



STEP NO 04:

Open the firefox and type the following command. It will only start if apache and mysql are active and working on the terminal.

Instructions:
localhost/setup.php




As we can see there are alot of functions that are not granted the permissions so we will run more commands for that.

STEP NO 05:
Now for safe side we have to restart all the regarding servers like sql , mariadb etc then we will go to a specific path and edit the data inside

Instructions:


STEP NO 06:

Keep the following document by default

STEP NO 07:
Now we will again restart the apache server


STEP NO 08:

Grant the permission as display_error =On
Allow_url_include =On


STEP NO 9:
Now as we can see all The permissions are granted

STEP NO 10:
Go to The Dvwa Security and set it to low.Now when we try to create the database it will give us some error on the page.

STEP NO 11:
To create a database successfully on the DVWA these commands will be executed.

STEP NO 12:
This will check all the queries regarding the database and also grant the permission.

STEP NO 13:

And Now we can see that the database is successfully logged in now when we enter any query it will successfully run on the Dvwa .








CONCLUSION : 
An online security flaw known as SQL injection (SQLi) enables an attacker to tamper with database queries that an application makes. In most cases, it enables an attacker to view data that they would not typically be able to access.











LOSBUNTU
LESSON 1:
In order to start LosBuntu we first had to launch a Denial of Service (DoS) attack, in order to crash the machine and render the notorious Blue Screen of Death (BSOD). To do so we:
(1) set up a memory crash dump file,
(2) captured the crash dump file for later investigation,
(3) added and configured a new Virtual Hard Disk, and
(4) installed BlueScreenView.
STEP NO 01:
Instructions:
Click on Windows 7
Click on Edit virtual machine settings

STEP NO 02:
Instructions:
1.     Select CD/DVD (IDE)
2.     Click on the Use physical drive radio button, Select Auto detect
3.     Select Memory, Click on "512 MB"
4.     Select Network Adapter,  Click the radio button "NAT: Used to share the host's IP address”
5.     Start Windows 7 on VMWARE
We temporarily configured the windows 7 settings to limit the size of the crash dump file that we will analyze later.
  6. Configure Remote Settings and advance system settings
7. Complete memory dump
8. Verify crash dump file


 
STEP NO 03:
Instructions:
1. Bring up Command Prompt
2. Record IP Address

 

 STEP NO 04:
Instructions:
1. Save Blue Screen of Death Screenshot

 

STEP NO 05:
Instructions:
1. Open VMware Player on your windows machine
2. Edit Virtual Machine Settings
3. Add Hard Disk
 
 
 
STEP NO 06:
Instructions:
1. Start Windows 7
2. Windows Error Recovery, start windows normally

 
 STEP NO 07:
Instructions:
1. Configure Hard Drive
2. Initialize Disk
3. Create New Simple Volume
4. Download BlueScreenView
5. Select All Blue Screen Text after extracting blue screen view
6. Copy Blue Screen Text, paste it on notepad and save it



 We conducted a forensics memory investigation on the Crash Dump file we captured in Windows 7 after the MS12-020 RDP exploit was performed.
STEP NO 08:
Instructions:
1. Download LosBuntu ISO
2. Open VMware Player on your windows machine
3. Click on Windows 7, click on Edit virtual machine settings
4. Configure Memory, select on "2048 MB"
5. Configure CD/DVD Settings, check Connected
6. Select Use ISO image file, navigate to the LosBuntu_2015_12_14.iso
By following these steps, we ensure that the virtual machine is properly configured to use the LosBuntu ISO as the installation source on Windows 7 setup. This allows us to install the LosBuntu operating system on the virtual machine and run it within the VMware Player environment on Windows 7.






STEP NO 09:
Instructions:
1. Access the Boot Menu
2. Boot from CD-ROM Drive
3. Login To LosBuntu
4. Obtain IP Address
5. Obtain Hard Disk Information





                 
We couldn't continue this further, as we were unable to open the Boot menu after pressing the esc button. 

LESSON 3:

STEP NO 01:
Instructions:
Download LosBuntu ISO
Create a New Virtual Machine, for LosBuntu
Configure settings for LosBuntu
Start the LosBuntu VM
Select live - boot the Live System for boot selection and login to LosBuntu

STEP NO 02:
Instructions:
Complete LosBuntu Installation




STEP NO 02:
Instructions:
Poweroff the virtual machine by running the command on terminal

STEP NO 03:
Instructions:
Power on the VM after configuring the settings again for LosBuntu

STEP NO 04:
Instructions:
Configure Terminal Window Settings



STEP NO 05:
Instructions:
Become root
Obtain IP Address

STEP NO 05:
Instructions:
Proof of Lab
grep mtk /etc/passwd
usermod -c "Your Name" mtk
grep mtk /etc/passwd
tune2fs -l /dev/sda1 | grep "Filesystem created:"
Date
echo "Your Name"


ACKNOWLEDGEMENT :

We would Like to Express Our Greatest Gratitude To the course teacher Miss Mafaza Mohi (Our theory Teacher) and Sir Saad Javed(Our Lab Instructor), Without their continuous guidance the project would not have been completed.










