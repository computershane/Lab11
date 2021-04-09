# TryHackMe
  -https://tryhackme.com/room/kenobi
  
<img src="kenobi.png"
     alt="Kenobi_Marker_icon"
     style="float: left; margin-right: 10px;" />
    
    
# Task 1 Deploy the Vulnerable Machine
  Connected to Kali and setup vpn in teminal
  
  ```sudo openvpn /home/kali/Downloads/computershane\(1\).ovpn```
  
  Attack box IP-```10.10.152.93```
  
  Host IP-```10.2.70.52```
  
  ran nmap
  
  ```nmap -A -T4 10.10.152.93```
  
  Scan the machine with nmap, how many ports are open?
  
  Answer-```7```
  
# Task 2   Enumerating Samba for shares

Using nmap we can enumerate a machine for SMB shares.

Nmap has the ability to run to automate a wide variety of networking tasks. There is a script to enumerate shares!

```nmap -p 445 --script=smb-enum-shares.nse,smb-enum-users.nse 10.10.152.93```

Using the nmap command above, how many shares have been found?

Answer-```3```

Next I connected to the share

```smbclient //10.10.152.93/anonymous```

Once you're connected, list the files on the share. What is the file can you see?

I ran dir to list the contents of the share

```dir```

Answer- ```log.txt```

Recursively downloaded share by 

```smbget -R smb://10.10.152.93/anonymous```








