# Corrupted File

**Category:** Forensics  
**Difficulty:** Easy/Medium  

---

## Description
We are given a corrupted file. The goal is to repair it
and reveal the hidden flag.

---

## Solution

### Step 1 — Open the File in a Hex Editor
I uploaded the corrupted file to **hexed.it**, 
an online hex editor.

### Step 2 — Identify the Problem
I researched the correct magic bytes (file signature) 
for a JPEG file.
A valid JPEG file must start with the magic bytes:
```
FF D8 FF
```

The corrupted file had incorrect bytes at the beginning,
which prevented it from being recognized as an image.

### Step 3 — Fix the Magic Bytes
Using hexed.it, I manually modified the first 3 bytes
to the correct JPEG signature:
```
FF D8 FF
```

### Step 4 — Export and Save
I exported the repaired file and saved it as `file.jpeg`.

### Step 5 — Open the Image
The file was now recognized as a valid JPEG image.
Opening it revealed a photo with the flag written in red.

---

## Tools Used
- hexed.it (online hex editor)
- Magic bytes / file signature reference

---

## What I Learned
- Every file format has a unique signature called **magic bytes**
  at the beginning of the file
- JPEG magic bytes: `FF D8 FF`
- PNG magic bytes: `89 50 4E 47`
- PDF magic bytes: `25 50 44 46`
- Corrupted files can often be repaired by fixing magic bytes
- Hex editors are essential tools in digital forensics

---

**Flag:** `picoCTF{r3st0r1ng_th3_by73s_1512b52a}`
