# Ancora-Education-Ucertify-Lab56
# Managing File Permissions

> **Original Lab Source**
> 
> This lab was available through:
>
> [https://ancoraeducation.ucertify.com/app/?func=navigate_items&item_sequence=9]

## Objective of the Lab 
In this lab, you will learn to manage file permissions. Command used: chmodo The chmod command is used to change permissions for a file or directory on a Unix machine. The chmod command is used to display, assign, and change permissions to files.
## Instructions
## Caution 
* Enter password as uC@135246, whenever required.
### STEP 1 
From the desktop, open the Terminal window.
### STEP 2
Execute the following command to display the permissions on the /etc/chrony.keys file:
```bash
ls -l /etc/chrony.keys
```
### NOTES
* Based on the output of the command from STEP 2, the root user owns the /etc/chrony.keys file.
*  Based on the output of the command from STEP 2, the chrony group owns the /etc/chrony.keys file.
### STEP 3 
Execute the following command to view the contents of the file:
```bash
more /etc/chrony.keys
```
### Note 
* The more /etc/chrony.keys command failed because only the owner and group members can view the contents of this file, and the current account is not the owner and is not a member of the correct group.
### STEP 4 
Execute the following command to add the student user to the chrony group:
```bash
usermod -G chrony -a student
```
### STEP 5
On the desktop, click the icon set in the upper-right corner to log out of the system and then click root, click Log Out, and again click Log Out.
## CAUTION
* This is necessary for the group ownership to take effect.
### STEP 6
On the login screen, click Student and provide the password as uC@135246 for this user and click Sign In.
### STEP 7 
From the left sidebar, open the Terminal window. 
### STEP 8
Execute one of the given two commands to display the current user's groups:
```bash
id
```
```bash
groups
```
### STEP 9
 Execute the following command to verify that this file's contents can now be displayed by the student user:
 ```bash
more /etc/chrony.keys
```
### NOTE
* The current directory is the home directory for the student user.
``` bash
sudo cp /etc/chrony.keys /keys
```
### STEP 11 
Execute the following command to use octal notation and change the permissions of the chrony.keys file that is in the current directory to -r---------:
```bash
sudo chmod +r /etc/chrony.keys
```
### NOTE
* Using octal notation, trying to change the permissions of the chrony.keys file that is in the /etc directory to -r---------.
### STEP 13
Execute the following command to change the mask value for the current shell so any new directory would have the drwxr-x--- permissions:
```bash
umask 027
```
### STEP 14 
Execute the following command in the Terminal window to create a file named test.txt and see the permissions of the new file that are created have is -rw-r-----:
```bash
touch test.txt
```
```bash
ls -l test.txt
```
## Disclaimer

This repository is for **educational and personal learning purposes only**.  

The original lab content belongs to **uCertify / Ancora Education** and remains their copyrighted material.  
This repository is not affiliated with, endorsed by, or sponsored by uCertify or Ancora Education.  

No copyright infringement is intended.  
Use of any tools or techniques mentioned here should only be performed in authorized, legal environments.
