# **Linux Fundamentals**
- sudo 
    - needed for admin permissions
- cd ~
    - home directory
- ls
    - list of contents
- ls -la
    - detailed list of contents
- ipconfig
- ping
- wget/curl **{URL}**
- sudo dnf update
    - updates packages available to install or update
- sudo dnf upgrade
    - upgrades any out of date packages
- sudo apt install *package* **or** sudo dnf install *package* 
    - installs specific package requested
- sudo systemctl enable *package*
- sudo systemctl start *package*
- sudo systemctl status *package*
### Files
- touch *filename.txt*
    - create a file
- vi *file name*
    - helps to edit the file 
    - :wq
        - writes and quits 
    - :q!
        - force quits without saving 
### Folders
- mkdir **newfolder**
- mkdir **newfolder/subfolder**
    - creates a sub folder in the first folder
- mkdir -p **newfolder/subfolder**
    - creates both folders at once
### Files and Folders
- cp **(file/folder) (file/folder 2)**
    - copies files or folders to the new folder
- mv **(file/folder) (file/folder 2)**
    - moves/renames file or folder
- rm **file/folder**
    - removes file or folder
- rm **(folder/*)**
    - removes all files from folder
- rm -d **folder**
    - deletes folder
- rm -rf **folder**
    - brute force deletes folder and files
    - **CAN BE VERY DANGEROUS BE VERY CAREFUL**
### Tree
- sudo dnf -y install tree
    - installs tree
- tree
    - shows the folder and file structure
### Users
- sudo useradd *{username}* -c "Users Name"
- cat /etc/passwd
    - lists the user account
- sudo passwd *{username}*
    - input password **(nothing will appear when typed)**
- sudo groupadd **groupname**
    - creates a group
- sudo usermod **{username}** -aG **{groupname}**
    - adds user to group

#### User Permissions
| read | write | execute |
| -----|-------|---------|
| read | write | execute |
|   4  |   2   |    1    |
7
#### Group Permissions
| read | write | execute |
| -----|-------|---------|
| read |   -   | execute |
|   4  |   2   |    1    |
5
#### Other Permissions
| read | write | execute |
| -----|-------|---------|
| read | - | - |
|   4  |   2   |    1    |
4

- sudo chmod **(u/g/o)=(rwx)**
    - changes users, groups,or others permissions
- sudo chown **{username} folder**
    - changes the owner of the folder/directory
- sudo chmod #(table above) **directory**
    - changes the permissions in a directory
- sudo chgrp **{groupname} {directory}**
    - changes group owner of directory