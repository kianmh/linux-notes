# linux-notes
>>>Day 1
Commands learned: 
- 'pwd' - show currect directory
- 'ls' - list files
      * ls -l
      * ls -a
      * ls -la
- 'cd' - change directory
- 'mkdir' -create directory
- 'touch' create files
- 'cp' copy files
     'cp -r'  copy folders
     'cp -a' copy files/directories and preserve attributes
  -'mv' - move & rename files
  -'rm' remove files
       'rm -r' remove folders
       'rm -rf'  force remove directories/files recursively (dangerous)

  ** Today I learned**:
  - Linux paths start from '/'
  - I can navigate folders using terminal witthout GUI
  - 'mkdir -p' helps create nested folders

   End of Day 1. 2026 May 31

>>>Day 2
- Permissions
- Access : Usern / Group / Other
- permissions : r (read permission) w (edite & delete permission) x (Execut permission)
- ls -l :  - rw- r-- r--
-        : first charecter>> file type  : '-' = normal files , 'd'= directory  , 'l'= link
-    first (rwx)= user permission
-    second (rwx) = group permision
-    third (rwx) = other permission

- Change 'rwx' to numbers ;
-    r =4 , w=2 , x=1
-    Ex. rwx = 4+2+1 = 7 , rwx= 777 
- End of Day2. 2026 June 1

- >>>Day 3
  

**Topic: User Management**

**Commands learned:**
- `useradd` - create a new user
- `adduser` - create a new user interactively
- `passwd` - set or change user password
- `usermod` - modify user account
- `userdel` - delete a user
- `id` - show user ID and group IDs
- `groups` - show user groups

**Today I learned:**
- Linux can have multiple users on the same system.
- Each user has a UID (User ID).
- A user can belong to one or more groups.
- `passwd` is used to set or change a user's password.
- `id` and `groups` help check user identity and permissions.
- Practice:
```bash
sudo adduser testuser
id testuser
groups testuser
sudo passwd testuser
sudo usermod -s /bin/bash testuser
sudo userdel testuser

End of day 3. 2026 june 2

#Day 4

**Topic:** Group Management

**Commands learned:**
- `groupadd` - create a new group
- `groupdel` - delete a group
- `usermod -aG` - add user to a secondary group
- `groups` - show user groups
- `chgrp` - change group ownership
- `chmod` - change permissions

**Today I learned:**
- Groups help manage permissions for multiple users.
- `sudo` is required for creating users and groups.
- `usermod -aG` adds a user to a group safely.
- `/srv/project` and `~/srv/project` are different paths.
- `chmod 770` gives full access to owner and group, but no access to others.
- Practice:
bash
-sudo groupadd devops
-sudo adduser testdev
-sudo usermod -aG devops testdev
-groups testdev
-sudo mkdir /srv/devops-project
-sudo chgrp devops /srv/devops-project
-sudo chmod 770 /srv/devops-project
-ls -ld /srv/devops-project

End of Day 4. 2026 june 6


# Day 5

**Topic:** Linux User Account Files

**Commands learned:**
- `grep username /etc/passwd` - find user account info
- `grep groupname /etc/group` - find group info
- `id username` - show UID, GID and groups
- `sudo grep username /etc/shadow` - check password hash entry
- `ls -l /etc/passwd` - check file permissions
- `ls -l /etc/shadow` - check secure password file permissions

**Important files:**
- `/etc/passwd` - stores basic user account information
- `/etc/shadow` - stores encrypted password hashes and password aging info
- `/etc/group` - stores group information and members
- `/etc/gshadow` - secure group information file

**Today I learned:**
- Linux stores user and group information in system files under `/etc`.
- `/etc/passwd` contains username, UID, GID, home directory and shell.
- `/etc/shadow` contains password hashes and is protected for security.
- `/etc/group` shows groups and their members.
- Commands like `adduser`, `passwd`, `groupadd`, and `usermod` update these files behind the scenes.

**Practice:**
```bash
grep kian /etc/passwd
grep testdev /etc/passwd
grep devops /etc/group
id kian
id testdev
sudo grep kian /etc/shadow
ls -l /etc/passwd
ls -l /etc/shadow


End of Day 5. 2026 june 7



# Day 6

**Topic:** File Security & Permissions

**Commands learned:**
- `ls -l` - check file ownership and permissions
- `chmod` - change file permissions
- `chown` - change file owner
- `chgrp` - change group owner
- `chmod +x` - make file executable
- `chmod 755` - numeric permission mode
- `chmod 700` - restrict access to owner only

**Permission model:**
- `r` = 4
- `w` = 2
- `x` = 1
- 755 → rwx r-x r-x
- 700 → rwx --- ---

**Today I learned:**
- Every file has an owner and a group.
- Linux permissions are divided into user, group, and others.
- Numeric permissions are commonly used in DevOps environments.
- Most “Permission denied” errors are caused by incorrect ownership or missing execute permission.
- Sticky bit (`t`) protects shared directories like `/tmp`.

**Practice:**
```bash
mkdir secure-project
touch secure-project/data.txt
chmod 700 secure-project
touch test.sh
echo "echo Hello DevOps" > test.sh
chmod +x test.sh
./test.sh
ls -l

End of Day 6. 2026 june 8

# Day 7

**Topic:** Special Permissions in Linux

**Concepts learned:**
- `SUID` (Set User ID)
- `SGID` (Set Group ID)
- `Sticky Bit`

**Key points:**
- `SUID` allows an executable file to run with the permissions of its owner.
- `SGID` on a file allows it to run with the permissions of its group.
- `SGID` on a directory makes new files inherit the directory’s group.
- `Sticky Bit` on a shared directory prevents users from deleting each other’s files.

**Important numeric values:**
- `4` = SUID
- `2` = SGID
- `1` = Sticky Bit

**Examples:**
```bash
chmod 4755 file
chmod 2775 /srv/dev-project
chmod 1777 /shared-temp

End of Day 7. 2026 june 9


# Day 8 : practice
Topic: Linux Users, Groups, and Project Permissions Lab

Concepts learned:

    Creating users and groups
    Managing group membership
    File ownership (chown, chgrp)
    File and directory permissions (chmod)
    SGID for shared project directories
    Access Control Lists (ACL)
    Sticky Bit for shared directories

Key points:

    Users and groups are managed through /etc/passwd, /etc/shadow, /etc/group, and /etc/gshadow.
    usermod -aG is used to add a user to a secondary group.
    chown changes the owner and group of a file or directory.
    chmod changes file permissions using numeric or symbolic modes.
    SGID on a directory ensures that new files inherit the directory’s group.
    ACL allows granting permissions to specific users without changing global permissions.
    Sticky Bit prevents users from deleting files owned by other users in shared directories.

Project directory structure:
   /srv/new_project
   app
   logs
   tmp
   docs
   scripts

Important commands practiced:

groupadd devops
groupadd qa

adduser dev1
adduser dev2
adduser tester1

usermod -aG devops dev1
usermod -aG devops dev2
usermod -aG qa tester1

mkdir -p /srv/new_project/{app,logs,tmp,docs,scripts}

chown -R root:devops /srv/new_project
chmod -R 770 /srv/new_project

find /srv/new_project -type d -exec chmod 2770 {} \;

setfacl -m u:tester1:x /srv/new_project
setfacl -m u:tester1:rx /srv/new_project/docs

chmod 1777 /srv/new_project/tmp

Example checks:

id dev1
groups dev2
ls -ld /srv/new_project
ls -l /srv/new_project/app/main.py
getfacl /srv/new_project/docs


End of Day 8. 2026 June 10

Day 9

Topic: Special Permissions and Permission Debugging in Linux

Concepts learned:

    Investigating SUID binaries
    Searching for special permissions
    Parent directory permission problems
    Ownership management (chown, chgrp)
    Numeric vs symbolic permissions
    Script execution permissions
    Debugging common permission errors

Key points:

    SUID allows a program to run with the privileges of the file owner.
    SGID ensures group inheritance inside shared directories.
    Sticky Bit protects files in shared writable directories.
    Directory access requires execute (x) permission.
    Users must have execute permission on all parent directories to reach a path.
    Only the file owner or root can change file permissions using chmod.
    Incorrect ownership or directory permissions are common causes of Permission denied.

Ex.
ls -l /usr/bin/passwd

find /usr/bin -perm -4000 -type f
sudo find / -perm -2000
sudo find / -perm -1000 -type d

Ownership Ex.
chown root:devops config.yml
chgrp devops config.yml
chown dev1 config.yml




Permission Ex.
chmod 750 deploy.sh
chmod g+w file
chmod u+x script.sh
chmod o-rwx secret.txt

Script execution ex:

                                                                    
chmod +x /srv/new_project/scripts/deploy.sh
/srv/new_project/scripts/deploy.sh

Debugging Ex.

                                                                    
chmod 660 /srv/new_project/scripts
chmod 2770 /srv/new_project/scripts

chown root:qa /srv/new_project/app
chown root:devops /srv/new_project/app

Common troubleshooting tools:

                                                                    
ls -l
ls -ld
id
groups
getfacl
find

End of Day 9. 2026 June  26







