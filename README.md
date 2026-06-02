# linux-notes
#Day 1
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

#Day 2
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

- #Day 3
  

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

**Practice:**
```bash
sudo adduser testuser
id testuser
groups testuser
sudo passwd testuser
sudo usermod -s /bin/bash testuser
sudo userdel testuser

#End of Day 3. 2026 June 2
