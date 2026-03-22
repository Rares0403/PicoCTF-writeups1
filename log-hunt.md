# Log Hunt

**Category:** General Skills  
**Difficulty:** Easy  

---

## Description
We are given a log file (.txt / note file). 
The flag is hidden somewhere inside it.

---

## Solution

### Step 1 — Open and Read the File
I opened the file and carefully read through all the lines.

### Step 2 — Identify the Pattern
Among the log entries I noticed strings that looked out of place
compared to normal log data.

### Step 3 — Organize the Strings
I extracted and organized the suspicious strings in order,
which when combined revealed the flag directly.

---

## Tools Used
- Text editor / notepad
- Manual analysis (no special tools needed)

---

## What I Learned
- Not all CTF challenges require complex tools
- Log files can hide data in plain sight between normal entries
- Careful reading and pattern recognition are fundamental skills
  in forensics and security analysis
- Real security analysts spend a lot of time reading logs —
  this challenge simulates exactly that

---

**Flag:** `picoCTF{us3_y0urlinux_cedfa5fb}`
