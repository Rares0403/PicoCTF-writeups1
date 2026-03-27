# SUDO MAKE ME A SANDWICH

**Category:** General Skills  
**Difficulty:** Easy  

---

## Description
We are given SSH credentials to connect to a remote server.
The flag is stored in a file we need to access with 
elevated privileges.

---

## Solution

### Step 1 — Connect to the Server
Using the provided credentials, I connected via SSH
through the picoCTF webshell:
```bash
sh -p 59028 ctf-player@green-hill.picoctf.net
```

Password: provided in challenge

### Step 2 — List Files
After connecting, I listed the files in the directory:
```bash
ls
```

Output revealed:
```
flag.txt
```

### Step 3 — Read the Flag with Sudo
The file required elevated privileges to read.
I used sudo with emacs to open it:
```bash
sudo emacs flag.txt
```

This opened the file with admin privileges,
revealing the flag directly.

---

## Tools Used
- SSH / WebShell — Remote server connection
- Linux terminal commands (ls, sudo)
- Emacs — Text editor with sudo privileges

---

## What I Learned
- **sudo** (Super User Do) allows executing commands
  with administrator privileges in Linux
- Even text editors like emacs can be used to read
  restricted files when run with sudo
- This is a real privilege escalation technique —
  if a user has sudo access to any text editor,
  they can read any file on the system
- **GTFOBins** (gtfobins.github.io) is a reference
  site that documents exactly these kinds of
  privilege escalation techniques using common tools
- Always check what sudo permissions you have with:
```bash
  sudo -l
```

---

**Flag:** `picoCTF{ju57_5ud0_17_9a782247}`
