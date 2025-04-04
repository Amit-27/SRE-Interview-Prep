### Day 1 hands-on Linux Challenge

##Logs Output

vboxuser@Linux:~$ echo -e "INFO: System boot\nERROR: Disk not found\nWARNING: High memory usage\nINFO: Network up\nERROR: Failed to mount volume" > system.log
vboxuser@Linux:~$ 
vboxuser@Linux:~$ ls -l system.log
-rw-rw-r-- 1 vboxuser vboxuser 114 Apr  4 11:44 system.log
vboxuser@Linux:~$ 
vboxuser@Linux:~$ chmod 600 system.log
vboxuser@Linux:~$ 
vboxuser@Linux:~$ ls -l system.log
-rw------- 1 vboxuser vboxuser 114 Apr  4 11:44 system.log
vboxuser@Linux:~$ 
vboxuser@Linux:~$ grep "ERROR" system.log
ERROR: Disk not found
ERROR: Failed to mount volume
vboxuser@Linux:~$ 
vboxuser@Linux:~$ 
vboxuser@Linux:~$ grep -c "INFO" system.log
2
vboxuser@Linux:~$ 
vboxuser@Linux:~$ sed 's/ERROR/CRITICAL/g' system.log
INFO: System boot
CRITICAL: Disk not found
WARNING: High memory usage
INFO: Network up
CRITICAL: Failed to mount volume
vboxuser@Linux:~$ 
vboxuser@Linux:~$ 
vboxuser@Linux:~$ awk -F": " '{print $2}' system.log
System boot
Disk not found
High memory usage
Network up
Failed to mount volume
vboxuser@Linux:~$ 
vboxuser@Linux:~$
