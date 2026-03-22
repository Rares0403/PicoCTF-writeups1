# Hidden in Plainsight

**Category:** Forensics  
**Difficulty:** Easy  

---

## Description
We are given a JPG image file. The flag is hidden somewhere inside it.

---

## Solution

### Step 1 — Metadata Analysis
I opened the image metadata using an online tool (exiftool / metadata viewer).
In the **Comment** field I found an encoded string:
```
c3RlZ2hpZGU6Y0VGNmVuZHZjbVE9
```

### Step 2 — Base64 Decode (first layer)
I decoded the string using Base64 and got:
```
steghide:cEF6endvcmQ=
```

This told me two things:
- The tool used is **steghide** (a steganography tool)
- The password is another Base64 encoded string

### Step 3 — Base64 Decode (second layer)
I decoded `cEF6endvcmQ=` and got the password:
```
pAzzword
```

### Step 4 — Extract Hidden File
Using the webshell, I ran:
```bash
steghide --extract -p pAzzword -sf img.jpg
```

This extracted a hidden `flag.txt` file from the image.

### Step 5 — Read the Flag
```bash
cat flag.txt
```

---

## Tools Used
- Metadata viewer (exiftool)
- Base64 decoder
- Steghide
- Linux terminal / webshell

---

## What I Learned
- Images can hide data inside metadata fields
- Steganography tools like steghide can embed files inside images
- Always check multiple layers of encoding (double Base64 in this case)

---

**Flag:** `picoCTF{h1dd3n_1n_1m4g3_67479645}`
---
