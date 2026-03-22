**Category:** Forensics  
**Difficulty:** Easy  

---

## Description
We are given a file. The flag is hidden somewhere inside it.

---

## Solution

### Step 1 — Metadata Analysis
I opened the file using a metadata viewer.
In the **Author** field I found an encoded string:
```
cGljb0NURntwdXp6bDNkX20zdGFkYXRhX2YwdW5kIV8zNTc4NzM5YX0=
```

### Step 2 — Base64 Decode
I decoded the string using a Base64 decoder and got the flag directly:
```
picoCTF{puzzl3d_m3tadata_f0und!_3578739a}
```

---

## Tools Used
- Metadata viewer (exiftool)
- Base64 decoder

---

## What I Learned
- Metadata fields like Author, Comment, or Copyright
  can hide encoded data
- Always check all metadata fields, not just the obvious ones
- Base64 is one of the most common encoding methods in CTF challenges

---

**Flag:** `picoCTF{puzzl3d_m3tadata_f0und!_3578739a}`
