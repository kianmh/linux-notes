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
     'cp -a' copy by save information
  -'mv' - move & rename files
  -'rm' remove files
       'rm -r' remove folders
       'rm -rf'  

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
- 
