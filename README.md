# Networkwalks Academy CTF Writeups

Welcome to my Networkwalks Academy Capture The Flag (CTF) solutions repository. This repository documents my approach, methodology, and solutions for each challenge completed.


## Completed Challenges

### Flag 1: PDF Password Cracking ✓

**Status:** Completed  
**Flag:** `nw{networkwalks_flag1_jtr_270521_1}`  
**Methods:** John the Ripper, Networkwalks Online Cracker  
**Difficulty:** Beginner


## About Me

I'm documenting my journey through Networkwalks Academy CTF challenges. Each writeup includes detailed explanations, tools used, and visual evidence through screenshots.

# Flag 1: PDF Password Cracking

## Challenge Summary

**Objective:** Crack the password of an encrypted PDF file and capture the flag.

**Password:** `password1`  
**Flag:** `nw{networkwalks_flag1_jtr_270521_1}`  
**Status:** ✓ Captured

## Challenge Details

The challenge provides a password-protected PDF file (`My-Locked-PDF1.pdf`). The goal is to crack the password using security tools and retrieve the flag displayed after successfully unlocking the file.

**Encryption Type:** PDF MD5 SHA2 RC4/AES 32/64

## Solution Approach

I used two complementary methods to solve this challenge:

### Method 1: John the Ripper (Linux)
- Extracted the PDF hash
- Used John the Ripper to perform a dictionary attack
- Password cracked in 2 minutes 3 seconds
- Cracking speed: 0.5025g/s

### Method 2: Networkwalks Online Password Cracker
- Uploaded PDF to online cracking tool
- Tool performed dictionary attack across 100 password attempts
- Password matched on attempt 91
- Result: PASSWORD CRACKED SUCCESSFULLY

## Flag Captured

After confirming the password through both methods, I unlocked the PDF with `password1`. The Networkwalks platform displayed the congratulations page confirming:

**Flag:** `nw{networkwalks_flag1_jtr_270521_1}`

## Evidence

Screenshots documenting the complete solution process are included in the `screenshots/` folder:

1. **jtr_linux.png** - John the Ripper cracking process showing password found
2. <img width="1504" height="1366" alt="Screenshot 2026-09-20 182155" src="https://github.com/user-attachments/assets/3080cf71-0de3-4079-9997-d94d6d30852d" />

3. **flag_linux_confirmed.png** - Flag confirmation page after unlocking with Linux method 
5. <img width="2560" height="1344" alt="Screenshot 2026-09-20 181542" src="https://github.com/user-attachments/assets/8d4afee1-5c09-4f99-9d76-0ac0e13f72cc" />

6. **password_cracker_networkwalks.png** - Online password cracker showing successful crack
7. <img width="2560" height="1344" alt="Screenshot 2026-09-20 181425" src="https://github.com/user-attachments/assets/6176d54a-d59a-4436-bffd-df3663ca971a" />

8. **flag_captured.png** - Final flag confirmation from Networkwalks platform
9. <img width="2560" height="1344" alt="Screenshot 2026-09-20 180617" src="https://github.com/user-attachments/assets/9dbf4bd2-13a7-4a8e-a4fc-4ad1d8771a04" />

