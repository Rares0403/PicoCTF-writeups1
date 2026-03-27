# Old Session

**Category:** Web Exploitation  
**Difficulty:** Easy/Medium  

---

## Description
We are given a website where we need to find a way 
to access admin functionality.

---

## Solution

### Step 1 — Create Account and Login
I created an account on the provided website and logged in
with my credentials.

### Step 2 — Find the Hint
Reading through the page comments in the source code,
I found a hint pointing to the endpoint:
```
/session
```

### Step 3 — Access the Session Endpoint
I appended `/session` to the website URL:
```
http://[website-url]/session
```

This revealed session data including an admin session value.

### Step 4 — Copy the Admin Session Value
I identified and copied the admin session token 
from the exposed endpoint.

### Step 5 — Modify My Session Cookie
I opened the browser DevTools (F12) → Application tab
→ Cookies → found my current session cookie.

I replaced my session value with the admin session 
value copied in the previous step.

### Step 6 — Refresh and Get the Flag
After refreshing the page with the modified cookie,
the server recognized me as admin and revealed the flag.

---

## Tools Used
- Browser DevTools (F12) — Cookie manipulation
- Page source inspection — Finding hidden hints
- Manual URL manipulation

---

## What I Learned
- Web applications often expose sensitive endpoints
  that reveal session data
- Session cookies can be manipulated directly 
  in the browser without any special tools
- This vulnerability is called **Session Hijacking** —
  a real and common attack in web security
- Proper session management should never expose 
  admin tokens in public endpoints
- Always check page source code and comments 
  for hidden hints

---

**Flag:** `picoCTF{s3t_s3ss10n_3xp1rat10n5_53a328ed}`
