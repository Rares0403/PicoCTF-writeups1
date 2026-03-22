# Flag in Flame

**Category:** Forensics  
**Difficulty:** Easy  

---

## Description
We are given a file. The flag is hidden inside it.

---

## Solution

### Step 1 — Read the File
I opened the file and copied all its contents,
which appeared to be a Base64 encoded string.

### Step 2 — Base64 Decode
I decoded the contents using a Base64 decoder.
The result was an image file, which I saved locally.

### Step 3 — Analyze the Image
Inside the image I found a hex string:
```
7069636F4354467B666F72656E736963735F616E616C797369735F69735F616D617A696E675F65633139383466637D
```

### Step 4 — Hex Decode
I used **CyberChef** with the "From Hex" operation
to decode the hex string, which revealed the flag directly.

---

## Tools Used
- Base64 decoder
- Image viewer
- CyberChef (gchq.github.io/CyberChef)

---

## What I Learned
- Files can contain multiple layers of encoding
- Always look for hidden data inside decoded files,
  not just in the original
- CyberChef is an essential tool for CTF challenges —
  it handles Base64, Hex, and dozens of other encodings
- Hex encoding converts each character to its 
  ASCII hexadecimal value

---

**Flag:** `picoCTF{forensics_analysis_is_amazing_ec1984fc}`
