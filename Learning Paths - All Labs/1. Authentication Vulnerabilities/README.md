<h1 align="center">🔐 Authentication 🔐 (AuthN)</h1>

---

## 📖 What is Authentication?
Authentication is the process of **verifying the identity of a user or client**.  

### 🧩 Types of Authentication

1. **Something You Know** *(Knowledge Factor)*  
   - User have some Information (Example: Password, PIN, or answer to a security question.)  

2. **Something You Have** *(Possession Factor)*  
   - User have Physical object (Example: Mobile phone, smart card, or security token.)  

3. **Something You Are (or Do)** *(Inherence Factor)*  
   - User Authentication (Example: Biometrics (fingerprint, face scan, iris) or behavior patterns.)

<h1 align="center">🔓 Authorization 🔓 (AuthZ)</h1>

---

## 📖 What is Authorization?
Authorization is the process of allowing someone to access or **modify a resource.**

### Two Levels of Authorization
- Level 1 - Allow access to information only. 
- Level 2 - Allow access to information and to make certain account changes.

## Difference between Authentication and Authorization

---
 - **Authentication = Who are you?**  - It confirms your identity
 - **Authorization = What are you allowed to do?**  - It defines your access rights.
 - 🛡️ Both work together for Secure Access Control 🔐


### For Example::
> - Authentication determines someone access a website with the username **Carlos123.**
> - Once **Carlos123** is authenticated, their permissions determine what they are **Authorized** to do. For example, perform deleting another user's account.

## How Authentication vulnerabilities arises?

---

- The authentication mechanisms are **weak** because they fail to protect against **brute-force attacks.**
- **Logic flaws or poor coding** to be bypassed entirely by an attacker. This is sometimes called **"broken authentication"**

<h1 align="center">⚠️ Vulnerabilities Explanation ⚠️</h1>

---

## Vulnerabilities in password-based login
- Password-based logins are vulnerable because **weak, reused, or stolen passwords** can be easily guessed, cracked, or phished and Mainly **Brute-Forced.**

## Brute-force attacks
- A brute-force attack is when an attacker **tries all possible password or key combinations** until the correct one is found.

## Brute-forcing usernames
- Brute-forcing usernames is systematically trying many **Name/Email guesses to discover which accounts exist.**

## Brute-forcing passwords
- Automated process of trying many **possible password guesses** until the correct one is found.

## Username Enumeration by Brute-Force
While attempting to brute-force a login page, you should pay particular attention to any differences in:

- **Status codes :** During a brute-force, most HTTP responses are the same; a different status code signals a valid username.
- **Error messages :** if both username and password are wrong then may be only the password is wrong.
- **Response times :** If most responses take similar time, but a slower or faster one may indicate a correct username.


