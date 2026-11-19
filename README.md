# Week 3: Cryptographic Hashing & Password Strength Auditing

**Program:** Networkwalks Cybersecurity Internship Program (Batch B084K)  
**Intern:** Mst. Umme Sabiha  
**Instructor:** Waqas Karim, CCIE  
**Modules Covered:** W3-PM1 & W3-PM2  

> **⚠️ Ethical & Legal Disclaimer**  
> All labs, techniques, and proof-of-completion artifacts documented in this repository were conducted strictly within an authorized, isolated educational environment provided by Networkwalks Academy[cite: 2, 17]. The purpose of these exercises is to understand cryptographic weaknesses and improve defensive password policies[cite: 2, 17].

---

## 📋 Overview

Week 3 focused on the fundamentals of password storage security, one-way cryptographic hashing, and offline password auditing[cite: 17, 23]. By analyzing how password-protected PDF documents store authentication metadata, these modules demonstrate the speed at which weak, dictionary-based passwords can be compromised—highlighting the importance of strong password complexity and modern cryptographic standards[cite: 17, 23].

---

## 🛠️ Modules & Competencies

### 1. W3-PM1: Offline Password Auditing with John the Ripper (JTR)
* **Objective:** Evaluate the password resilience of an authorized training document (`My Locked PDF1.pdf`) using industry-standard auditing tools[cite: 2].
* **Tools Used:** John the Ripper (JTR Jumbo), Johnny (GUI for JTR), and `pdf2john` hash extraction utilities[cite: 2, 4, 6].
* **Key Concepts:**
  * Extracting `$pdf$` cryptographic hashes from encrypted documents[cite: 6, 7].
  * Configuring JTR executables within the Johnny graphical interface[cite: 4, 5].
  * Executing offline dictionary-based audits to demonstrate the vulnerability of common passwords[cite: 2, 12].

### 2. W3-PM2: Browser-Based Hash Analysis & Dictionary Auditing
* **Objective:** Perform client-side hash extraction and dictionary matching using Networkwalks' dedicated training utilities[cite: 17].
* **Tools Used:** Networkwalks Hash Calculator & Dictionary Attack Lab[cite: 17, 21].
* **Key Concepts:**
  * Distinguishing between two-way encryption and one-way hashing algorithms (MD5, SHA-1, SHA-256, SHA-512)[cite: 16, 23].
  * Analyzing PDF encryption metadata (Revision, Version, and 128-bit key length) locally in the browser[cite: 20].
  * Validating password recovery through controlled wordlist matching[cite: 21, 22].

---

## 🖥️ Technical Execution Proof

The screenshot below demonstrates successful offline hash auditing of the training PDF hash (`$pdf$4*4*128*...`) within the **Johnny GUI** frontend for John the Ripper, confirming how dictionary-based credentials (`password1`) are rapidly identified during security assessments[cite: 30]:

![Johnny GUI Password Audit Result](./Screenshot%202026-11-20%20050849.jpg)

---

## 🏆 Lab Verification & Captured Flags

To maintain responsible disclosure and respect proprietary lab materials, only the authorized flag confirmation screenshots are included below:

### 1. Lab Task 1 (`nw{cybersecurity_flag_captured_2608}`)[cite: 27]
![Lab Task 1 Flag Captured](./PDF%201%20Successfull.jpg)

### 2. Lab Task 2 (`nw{networkwalks_persistence_jtr_270521}`)[cite: 28]
![Lab Task 2 Flag Captured](./PDF%202%20Successfull.jpg)

### 3. Lab Task 3 (`nw{networkwalks_flag1_jtr_270521_1}`)[cite: 29]
![Lab Task 3 Flag Captured](./PDF%203%20Successfull.jpg)

---

## 🛡️ Defensive Recommendations

Based on the findings from Week 3's auditing exercises, organizations and users should enforce the following defensive controls:
1. **Enforce High Entropy & Length:** Require passphrases of at least 12–16+ characters combining uppercase, lowercase, numbers, and symbols to resist dictionary and brute-force attacks[cite: 23].
2. **Eliminate Common Dictionary Words:** Implement password blacklists (such as NIST SP 800-63B guidelines) to block commonly breached credentials like `password1` or `123456`[cite: 12, 23].
3. **Modern Hashing & Salting:** Ensure applications store credentials using salted, memory-hard hashing algorithms (e.g., Argon2id, bcrypt) rather than unsalted legacy hashes.
4. **Multi-Factor Authentication (MFA):** Layer authentication with hardware keys or authenticator apps so compromised passwords alone cannot grant unauthorized access.