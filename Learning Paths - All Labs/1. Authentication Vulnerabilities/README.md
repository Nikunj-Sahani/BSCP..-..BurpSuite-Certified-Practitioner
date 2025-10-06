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

> - [Lab-1 { Username enumeration via different responses }](https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/tree/main/Stage-1.%20Apprentice%20Labs#lab-1-username-enumeration-via-different-responses)

> - [Lab-2 { Username enumeration via subtly different responses }](https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/tree/main/Stage-1.%20Apprentice%20Labs#lab-2-username-enumeration-via-subtly-different-responses)

> - [Lab-3 { Username enumeration via response timing }](https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/tree/main/Stage-1.%20Apprentice%20Labs#lab-2-username-enumeration-via-subtly-different-responses)

---

## Flawed brute-force protection
It is highly likely that a brute-force attack will involve many failed guesses before the attacker successfully compromises an account. 

- The two most common ways of preventing brute-force attacks are:
> - Locking the account that the remote user is trying to access if they make too many failed login attempts
> - Blocking the remote user's IP address if they make too many login attempts in quick succession

- This means an attacker would simply have to log in to their own account, every few attempts to prevent this limit from ever being reached to fail.
- For Example :
- After 3 incorrect credential ,log in would be blocked.
> - Means 2 incorrect login can try with brute force.
- Auto setup for brute Force
> - 2 credential for brute force and 3rd is correct for log in.
> - Means it try 2 credential and in 3rd time it got logged in , so it would not be blocked.
> - It runs the attack weather it find the original credentials.

> - [ Lab - 4.1 { Broken brute-force protection, IP block - (1st METHOD) }](https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/edit/main/Stage-2.%20Practitioner%20Labs/PRACTITIONERLAB.md#lab--41---practitioner-)

> - [ Lab - 4.2 { Broken brute-force protection, IP block - (2nd METHOD) }](https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/edit/main/Stage-2.%20Practitioner%20Labs/PRACTITIONERLAB.md#lab--42---practitioner-)

---
## Account Locking
websites try to **prevent brute-forcing** is to lock the account if certain *suspicious criteria happened,* usually a set number of failed login attempts. 
Just as with normal login errors, responses from the **server indicating that an account is locked** can also help an attacker to enumerate usernames.

#### Account Locking understand in Easy Steps
- **What it is :** Account locking temporarily (or permanently) stops a user from logging in after suspicious activity.
- **Typical trigger :** A set number of failed login attempts (e.g., 5 wrong passwords) or unusual behavior.
- **Immediate effect :** The server rejects further login attempts for that username (shows “locked” or blocks responses).
- **Why sites do it :** Prevents automated brute-force attacks that try many passwords.

**Problems it can cause**

 > - **Username enumeration :** A “locked” message reveals the username exists.
 >  - **Denial-of-service :** Attackers can purposely lock many accounts.

**Common mitigations**
- Show generic error messages (“invalid credentials”) instead of “locked”.
- Use progressive delays or CAPTCHA after failures (instead of hard lock).
- Rate-limit by IP + account, combine with MFA and logging.
- Allow safe unlock methods (email link, timed cooldown, admin review).

> - [ Lab - 5 { Username enumeration via account lock }](https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/edit/main/Stage-2.%20Practitioner%20Labs/PRACTITIONERLAB.md#lab--5---practitioner-)

---
## User Rate Limiting
In this case, making too many login requests within a short period of time causes your IP address to be blocked.

**Example :**
- After 5 wrong logins → wait 30 seconds before next try.

IP can only be unblocked in one of the following ways:
> - Automatically after a certain period of time has elapsed
> - Manually by an administrator
> - Manually by the user after successfully completing a CAPTCHA

- Simple steps:
> - **Set a limit :** e.g., max 5 login tries per minute.
> - **Track requests :** Count each user/IP’s attempts.
> - **Block or delay :** If they exceed the limit, slow them down or temporarily block access.
> - **Why it’s used :** Stops brute-force attacks, spam, and abuse.

---
## HTTP Basic Authentication
In HTTP basic authentication, the client receives an authentication token from the server, which is constructed by concatenating the username and password, and encoding it in Base64.
- This token is stored and managed by the browser, which automatically adds it to the Authorization header
- **Authorization: Basic base64(username:password)**
> - Client sends Authorization: Basic BASE64(username:password).
> - Server decodes the header, checks credentials, and allows or denies access.

- Implementations of HTTP basic authentication often *don't support brute-force protection*. 
- HTTP basic authentication is also particularly *vulnerable to session-related exploits, notably CSRF*

### Vulnerabilities in Multi-factor authentication
Two-factor authentication (2FA) based on *something you know and something you have.*
- Email or SMS-based MFA can be **intercepted**
- Attacker tricks sim swapping to transfer victim’s phone number, **intercepting SMS-based codes.**
  
### Two-factor authentication Tokens
A 2FA token is the second proof of identity (after a password) used to confirm a user’s login.
- **SMS Token** – code sent by text message.
- **Email Token** – code sent to your email.
- **TOTP (Time-based One-Time Password)** – 6-digit code from apps like Google Authenticator or Authy.

**How it works (example)**

> - You enter your **username + password.**
> - The system asks for your **token code.**
> - You enter or approve it → **server verifies → access granted.**

---
## Bypassing two-factor authentication
Some sites mark you as “logged in” right after you enter the password — **before the 2FA code is checked.**
- **How to test :**
> - After entering a valid password (but not the code), try visiting a “logged-in only” page directly — **if it loads, 2FA is bypassable.**
- **Why that’s bad :**
> - If the session is active after the password step, an **attacker can skip the 2nd factor** and open pages that should be protected.

---

