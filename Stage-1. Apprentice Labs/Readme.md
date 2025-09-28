<h1 align="center">👨🏻‍💻Authentication vulnerabilities🆔</h1>

---

# Lab :: Username enumeration via different responses
* To solve the lab, *enumerate a valid username, brute-force this user's password,* then access their account page.

---
#### This lab is vulnerable to username enumeration and password brute-force attacks. It has an account with a predictable username and password.

<div style="text-align: center;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Stage-1.%20Apprentice%20Labs/Photos/Lab-1.png?raw=true" alt="Sample Image" width="700" height="600"></div>

---
#### This is our Interface of our Web-Lab where we have to test.

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Stage-1.%20Apprentice%20Labs/Photos/L1-2.png?raw=true" alt="Sample Image" width="700" height="600"></div>

---
#### I use dummy credentials and then perform username enumeration with Burp Suite.
 - Username : 1234
 - Password - 1234
   
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Stage-1.%20Apprentice%20Labs/Photos/L1-3.png?raw=true" alt="Sample Image" width="700" height="600"></div>

---
#### Username Enumeration
   * First enter dummy crediential and capture request in burp, 
   * Then find the original request and send to intruder.

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Stage-1.%20Apprentice%20Labs/Photos/L1-4.png?raw=true" alt="Sample Image" width="700" height="600"></div>

---
#### In Intruder , Add payload to username then go to paylaod section , add username list given in the Lab.
- Add Payload - &1234& (Username)
- Add username list in Payload section
> - Username List
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Stage-1.%20Apprentice%20Labs/Photos/L1-5.png?raw=true" alt="Sample Image" width="700" height="600"></div>

---

#### After Attack, we got a credential , 
- username : pi
  
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Stage-1.%20Apprentice%20Labs/Photos/L1-6.png?raw=true" alt="Sample Image" width="700" height="600"></div>

---
#### Password Attack - Do Same process as username enumeration brute force
- Now enter original username and wrong password
- Capture request in Burp
- Original request Send to Intruder
- Payload to password and add Payload list
> - Password List
> - 
- And Attack, then got real password.
- Passowrd - letmein
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Stage-1.%20Apprentice%20Labs/Photos/L1-7.png?raw=true" alt="Sample Image" width="700" height="600"></div>

---
### I found real password through Brute-Force Attack
> - **Username -** pi
> - **Password -** letmein

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Stage-1.%20Apprentice%20Labs/Photos/L1-final.png?raw=true" alt="Sample Image" width="700" height="600"></div>

