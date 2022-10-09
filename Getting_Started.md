# How to work on HPC

## **Connecting to HPC**
- **using SSH command**
  - Go the "Command Prompt" 
  - Use the SSH command: `ssh username@remote_host_address`
  - After this it will ask you for a password. Enter the password and here you go. you are now connected to you HPC system.
- **Other methods which includes installing a software**
  - Putty : https://www.putty.org
  - MobaXterm : https://mobaxterm.mobatek.net
  -  Both of these are free network tools which helps connect to other computers using ssh
- **For a folder view of HPC**
  - In order to get a File explorer type view of your files in HPC, you can use FileZilla (https://filezilla-project.org).
  - You just need to enter your Host address, Username and password
  - And you will be able to access, view, edit and transfer your files on HPC
- Difference between Local terminal and Remote Terminal
  - `[local]$` or `C:\Users\username>` : Connected to local system
  - `[username@node ~]$` : Connected to remote system

## **Exploring the HPC system**
- `whoami` : Returns the username
- `which` command : Used to get location of any command. 
  &nbsp; For e.g. : `which ping` gives the location of ping command.
  This command could be useful to check the location of any installed command.
- `ping` command : Used to check the network connection. For e.g. : `ping www.google.com`
- `pwd` : Returns the current directory.
- `ls` : Shows all the files and folder in the current directory.
- `cd Folder_name` : cd = change directory. Changes your directory to Folder_name.
- `mkdir Name` : Makes a new folder/directory in the current directory
- `man Command_name` command : Opens up the manual of the specified command (Command_name). For e.g. : `man ping`. Opens up manual for ping command. Press q to exit the manual.
- `dos2unix file_name` : Converts the file to unix format. For e.g.: To convert all the script files in a given directory, go to the directory and run `dos2unix *.sh`. Always use this, when you have transferred the script from windows to unix based system. 

Note : Mostly the commands help menu can be aaccessed by `ping --help` or `ping -h`. But it would be more brief than the manual.


## **Writing text-files/scripts in HPC**
- **using nano text editor**
  - Once connection is established with the remote system, you can use nono to write text files or scripts in the HPC system.
  - `nano test.txt`
  - This will create a 'test.txt' file in the current directory. (You can change the directory using cd command)
  - Now the nano editor will be visible. You can write the text you want like "Hello World!" (The most well known starter for anything).
  - Below the editor would guide you how you can save, exit and ...
  - Use Ctrl for `^`. For e.g. : `^O` is for saving the file which is done by pressing `Ctrl + O`

- **using Filezilla**
  - Go the directory of your interest.
  - Right-click and go to the `Create new File` option.
  - It will then ask for the name of the file. Enter the name.
  - The file will be created and then you can right-click on the file and select `View/Edit` option to write something in the file created

## **Transferring Files**
- **using scp command**
  - Go to the "Command Prompt"
  - For transferring a file from local system to host : 
  `scp -p file_address username@remote_host_adddress:destination_address`
  - NOTE: -p option is for progress bar there are ther options as well for example -r can also be added if the whole folder needs to be transferred
  - The above command can be reversed to get files from host to local system as well `scp -p username@remote_host_address:file Destination_address`
  - For more information : https://www.geeksforgeeks.org/scp-command-in-linux-with-examples/#:~:text=scp%20(secure%20copy)%20command%20in,or%20between%20two%20remote%20hosts

- **Using Filezilla**
  - You can just select and drag the files to transfer them between the two systems
