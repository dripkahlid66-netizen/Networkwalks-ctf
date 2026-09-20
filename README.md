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

# Flag 1 Writeup: PDF Password Cracking

## Overview

This writeup documents my solution to Flag 1, a beginner-level password cracking challenge from Networkwalks Academy.

## Challenge Description

A password-protected PDF file needs to be cracked. The challenge tests basic password cracking skills using common cybersecurity tools. Once the password is found and the PDF is unlocked, the flag is revealed on the platform.

## Solution Method 1: John the Ripper

### What is John the Ripper?

John the Ripper (JTR) is a fast password cracking tool used in penetration testing. It supports dictionary attacks, brute force, and hybrid approaches to crack weak passwords.

### Execution Steps

**Step 1: Extract PDF Hash**
```bash
$ pdf2john hash1.txt
```

**Step 2: Run John the Ripper**
```bash
$ john hash1.txt
```

**Step 3: Results**

John the Ripper output:
Created directory: /home/kali/.john
Using default input encoding: UTF-8
Loaded 1 password hash (PDF [MD5 SHA2 RC4/AES 32/64])
Cost 1 (revision) is 4 for all loaded hashes
Will run 2 OpenMP threads
Proceeding with single, rules:Single
Press 'q' or Ctrl-C to abort, almost any other key for status
Almost done: Processing the remaining buffered candidate passwords, if any.
Proceeding with wordlist:/usr/share/john/password.lst
password1 (?)
1g 0:00:00:01 DONE 2/3 (2026-09-20 17:57) 0.5025g/s 32.16p/s 32.16c/s 32.16C/s 123456..green

**Password Found:** `password1`  
**Time:** 2 minutes 3 seconds  
**Speed:** 0.5025 gigahashes per second

### Why This Method Works

- Dictionary attack against common password lists
- John the Ripper is highly optimized for speed
- "password1" is a common dictionary word variation
- No special characters or uppercase letters make it weak

## Solution Method 2: Networkwalks Online Password Cracker

### Tool Overview

Networkwalks Academy provides a web-based password cracking tool at `networkwalks.com/password-cracker/`. This tool uses an extensive wordlist database to crack PDF passwords.

### Execution Steps

**Step 1:** Access the online cracker tool  
**Step 2:** Upload or input the PDF hash  
**Step 3:** Tool performs dictionary attack  

**Step 4: Results**

The tool displayed:
Tried: 91 / 100
Progress: 9 pw/s
Completion: 91%

Attempting passwords:
[-] Trying: service X

[-] Trying: canada X

[-] Trying: hockey X

[-] Trying: killer X

[-] Trying: george X

[-] Trying: asdfgh X

[-] Trying: zxcvbn X

[-] Trying: qwertyuiop X

[-] Trying: 111222 X

[+] MATCH password1 /

PASSWORD CRACKED SUCCESSFULLY

password1


**Password Confirmed:** `password1`  
**Attempts:** 91 out of 100  
**Status:** SUCCESS

### Why This Method Confirms Results

- Independent verification using different tool
- Same password found confirms accuracy
- Demonstrates multiple approaches work
- Validates password strength assessment

## Flag Capture

After confirming the password, I entered `password1` into the PDF file. The file unlocked successfully and revealed the congratulations page with the flag.

**Flag:** `nw{networkwalks_flag1_jtr_270521_1}`

### Flag Format Breakdown

- `nw` = Networkwalks identifier
- `networkwalks_flag1` = Challenge identifier
- `jtr` = Method hint (John the Ripper)
- `270521` = Date code
- `1` = Sequential number

## Technical Analysis

### PDF Encryption Details

- **Type:** MD5 SHA2 RC4/AES hybrid
- **Key Length:** 32/64-bit
- **Vulnerability:** Weak password makes encryption irrelevant

### Password Characteristics

- **Length:** 9 characters (too short)
- **Character Set:** Lowercase + digits only
- **Complexity:** Low (dictionary word pattern)
- **Entropy:** Insufficient for modern security

### Why Password1 Was Cracked Easily

1. "password" is in every common wordlist
2. Adding "1" is predictable pattern
3. No uppercase or special characters
4. No security best practices applied
5. Both tools found it within seconds

## Conclusion

Flag 1 successfully captured by cracking the PDF password using two methods. The password `password1` demonstrated the importance of password complexity in cybersecurity. Both John the Ripper and the Networkwalks online tool confirmed the same result, validating the solution.

**Challenge Status:** ✓ Complete  
**Flag:** `nw{networkwalks_flag1_jtr_270521_1}`


Author: Dominic Joshua 