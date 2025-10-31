<h2 align="center">👨🏻‍💻Authentication vulnerabilities - Listing of Labs🆔</h2>

> - [Lab-1 { Username enumeration via different responses }](https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Stage-1.%20Apprentice%20Labs/ApprenticeLab.md#lab--1---apprentice-)

> - [Lab-6 { 2FA Simple Bypass }](https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Stage-1.%20Apprentice%20Labs/ApprenticeLab.md#lab--6---apprentice-)

---

<h1 align="center">👨🏻‍💻Authentication vulnerabilities🆔</h1>

---

# Lab : 1 : { Apprentice }
# Username enumeration via different responses
* To solve the lab, *enumerate a valid username, brute-force this user's password,* then access their account page.
* It is a simple brute force attack where you can find username and password easily.
> - [ Portswigger Lab { Username enumeration via different responses }](https://portswigger.net/web-security/authentication/password-based/lab-username-enumeration-via-different-responses)

---
### This lab is vulnerable to username enumeration and password brute-force attacks. It has an account with a predictable username and password.

<div style="text-align: center;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/Lab-1.png" alt="Sample Image" width="700" height="600"></div>

---
### This is our Interface of our Web-Lab where we have to test.

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L1-2.png" alt="Sample Image" width="700" height="600"></div>

---
### I use dummy credentials and then perform username enumeration with Burp Suite.
 - Username : 1234
 - Password - 1234
   
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L1-3.png" alt="Sample Image" width="700" height="600"></div>

---
### Username Enumeration
   * First enter dummy crediential and capture request in burp, 
   * Then find the original request and send to intruder.

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L1-4.png" alt="Sample Image" width="700" height="600"></div>

---
### In Intruder , Add payload to username then go to paylaod section , add username list given in the Lab.
- Add Payload - &1234& (Username)
- Add username list in Payload section
> - You can copy username List from given link below.
> - [Username List from Lab](https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Payload%20%26%20Scripts/Username%20List.txt)

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L1-5.png" alt="Sample Image" width="700" height="600"></div>

---
### After Attack, we got a credential.
- You can find the username by Length or status (Correct username has diffrent status code).
- username : pi
  
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L1-6.png" alt="Sample Image" width="700" height="600"></div>

---
### Password Attack - Do Same process as username enumeration brute force
- Now enter original username and wrong password
- Capture request in Burp
- Original request Send to Intruder
- Payload to password and add Payload list
> - You can copy Password List from given link below.
> - [Password List from Lab](https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Payload%20%26%20Scripts/Password%20List.txt)
- And Attack, then got real password.
- Passowrd - letmein
  
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L1-7.png" alt="Sample Image" width="700" height="600"></div>

---
### I found real password through Brute-Force Attack
> - **Username -** pi
> - **Password -** letmein

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L1-final.png" alt="Sample Image" width="700" height="600"></div>

## After Submit Credential , i got logged in Successfully.
> - We Got a message after Solving the Lab
- **Congratulations, You solved the Lab.**

---
---

# Lab : 6 : { Apprentice }
# 2FA Simple Bypass
* This lab's two-factor authentication can be bypassed.
* You have already obtained a *valid username and password*, but do not have access to the user's 2FA verification code.
  
> - [ Portswigger Lab { 2FA simple bypass }](https://portswigger.net/web-security/authentication/multi-factor/lab-2fa-simple-bypass)

---
### To solve the lab, access Carlos's account page.

- Your credentials - **wiener : peter**
- Victim's credentials - *carlos : montoya*

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/Lab-6.png" alt="Sample Image"></div>

---
### This is our Interface of our Web-Lab where we have to test.
Here 2 options are there

- Home
- My Account

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L6-2.png" alt="Sample Image"></div>

---

### I use login credentials and then perform test with Burp Suite.
 - Username : *wiener*
 - Password - *peter*
   
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L6-3.png" alt="Sample Image"></div>

---
### Mail Server - For OTP

- Open the Mail server
- Got the OTP 
   
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L6-4.png" alt="Sample Image"></div>

---
### Check request in Burp
After getting OTP, enter the original OTP and enter.

- Check request in Burp
- After Login , Read the parameter - **/my-account?=wiener HTTP/1.1**
> - **Copy the parameter to use later.**
   
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L6-5.png" alt="Sample Image"></div>

---
### Login Page
 I use login victim credentials and then perform test with Burp Suite.
 - Username : *carlos*
 - Password - *montoya*
> - Enter credential & Enter

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L6-6.png" alt="Sample Image"></div>

---
### Enter Wrong OTP
-Before clicking Ok 
- On the intercept of Burp

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L6-7.png" alt="Sample Image"></div>

---
### Request captured in Burp Suite

- Find OTP request and *change the parameter*
- *GET Normal paramater*
- Change to the Parameter you copied before
> - **GET /my-account?=carlos HTTP/1.1**

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L6-8.png" alt="Sample Image"></div>

---
### Lab Solved
After request forwarding  , I got logged in **Successfully in Carlos Account.**

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L6-9.png" alt="Sample Image"></div>

> - We Got a message after Solving the Lab
- **Congratulations, You solved the Lab.**

---
---
