<h2 align="center">👨🏻‍💻Authentication vulnerabilities - Listing of Labs🆔</h2>

> - [Lab-1 { Username enumeration via different responses }](https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/tree/main/Stage-1.%20Apprentice%20Labs#lab-1-username-enumeration-via-different-responses)


---

<h1 align="center">👨🏻‍💻Authentication vulnerabilities🆔</h1>

---

# Lab : 1 : { Apprentice }
# Username enumeration via different responses
* To solve the lab, *enumerate a valid username, brute-force this user's password,* then access their account page.
* It is a simple brute force attack where you can find username and password easily.
---
#### This lab is vulnerable to username enumeration and password brute-force attacks. It has an account with a predictable username and password.

<div style="text-align: center;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/Lab-1.png" alt="Sample Image" width="700" height="600"></div>

---
#### This is our Interface of our Web-Lab where we have to test.

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L1-2.png" alt="Sample Image" width="700" height="600"></div>

---
#### I use dummy credentials and then perform username enumeration with Burp Suite.
 - Username : 1234
 - Password - 1234
   
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L1-3.png" alt="Sample Image" width="700" height="600"></div>

---
#### Username Enumeration
   * First enter dummy crediential and capture request in burp, 
   * Then find the original request and send to intruder.

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L1-4.png" alt="Sample Image" width="700" height="600"></div>

---
#### In Intruder , Add payload to username then go to paylaod section , add username list given in the Lab.
- Add Payload - &1234& (Username)
- Add username list in Payload section
> - You can copy username List from given link below.
> - [Username List from Lab](https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Payload%20%26%20Scripts/Username%20List.txt)

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L1-5.png" alt="Sample Image" width="700" height="600"></div>

---
#### After Attack, we got a credential.
- You can find the username by Length or status (Correct username has diffrent status code).
- username : pi
  
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L1-6.png" alt="Sample Image" width="700" height="600"></div>

---
#### Password Attack - Do Same process as username enumeration brute force
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
