<h2 align="center">👨🏻‍💻Authentication vulnerabilities - Listing of Labs🆔</h2>

> - [Lab-1 { Username enumeration via different responses }](https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/tree/main/Stage-1.%20Apprentice%20Labs#lab-1-username-enumeration-via-different-responses)

> - [Lab-2 { Username enumeration via subtly different responses }](https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/tree/main/Stage-1.%20Apprentice%20Labs#lab-2-username-enumeration-via-subtly-different-responses)

> - [Lab-3 {Username enumeration via response timing }](https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/tree/main/Stage-1.%20Apprentice%20Labs#lab-2-username-enumeration-via-subtly-different-responses)



---

<h1 align="center">👨🏻‍💻Authentication vulnerabilities🆔</h1>

---

# Lab : 1 : 
# Username enumeration via different responses
* To solve the lab, *enumerate a valid username, brute-force this user's password,* then access their account page.
* It is a simple brute force attack where you can find username and password easily.
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
> - You can copy username List from given link below.
> - [Username List from Lab](Stage-1.%20Apprentice%20Labs/Payload%20%26%20Scripts/Username%20List.txt)

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Stage-1.%20Apprentice%20Labs/Photos/L1-5.png?raw=true" alt="Sample Image" width="700" height="600"></div>

---
#### After Attack, we got a credential.
- You can find the username by Length or status (Correct username has diffrent status code).
- username : pi
  
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Stage-1.%20Apprentice%20Labs/Photos/L1-6.png?raw=true" alt="Sample Image" width="700" height="600"></div>

---
#### Password Attack - Do Same process as username enumeration brute force
- Now enter original username and wrong password
- Capture request in Burp
- Original request Send to Intruder
- Payload to password and add Payload list
> - You can copy Password List from given link below.
> - [Password List from Lab](Stage-1.%20Apprentice%20Labs/Payload%20%26%20Scripts/Password%20List.txt)
- And Attack, then got real password.
- Passowrd - letmein
- 
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Stage-1.%20Apprentice%20Labs/Photos/L1-7.png?raw=true" alt="Sample Image" width="700" height="600"></div>

---
### I found real password through Brute-Force Attack
> - **Username -** pi
> - **Password -** letmein

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Stage-1.%20Apprentice%20Labs/Photos/L1-final.png?raw=true" alt="Sample Image" width="700" height="600"></div>

## After Submit Credential , i got logged in Successfully.
> - We Got a message after Solving the Lab
- **Congratulations, You solved the Lab.**

---
---

# Lab : 2 : 
# Username enumeration via subtly different responses
* To solve the lab, enumerate a valid username, brute-force this user's password, then access their account page.
* It uses some methodologies to find real username and password.

---
#### This lab is subtly vulnerable to username enumeration and password brute-force attacks. 
 - It has an account with a predictable username and password.

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Stage-1.%20Apprentice%20Labs/Photos/Lab-2.png?raw=true" alt="Sample Image" width="700" height="600"></div>

---
#### I use dummy credentials and then perform username enumeration with Burp Suite.
 - Username : abcd
 - Password - 1234
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Stage-1.%20Apprentice%20Labs/Photos/L2-2.png?raw=true" alt="Sample Image" width="700" height="600"></div>

---
#### Username Finding - Capture request in burp 
- Then find the original request
- **Request is confirm by your credential entered**
- Send to intruder.
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Stage-1.%20Apprentice%20Labs/Photos/L2-3.png?raw=true" alt="Sample Image" width="700" height="600"></div>

---
#### Position & Payload Section
- Clear all payload then Select payload on **$abcd$** as username
> - Copy the Username from the list given in Lab (Candidate username)
> - [Username List from Lab](Stage-1.%20Apprentice%20Labs/Payload%20%26%20Scripts/Username%20List.txt)

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Stage-1.%20Apprentice%20Labs/Photos/L2-4.png?raw=true" alt="Sample Image" width="700" height="600"></div>

---
#### Intruder -> Options 
- Grep - Extract
- Add > **Fetch response**
- Find the **Invalid username and Username** and select to highlight it.
- Then click **Ok**
  
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Stage-1.%20Apprentice%20Labs/Photos/L2-5.png?raw=true" alt="Sample Image" width="700" height="600"></div>

---
#### Attack Started for Username
- In this you can't find right username by Status code.
- In this, you get a **another section after adding (Grep-Extract)**
- **One parameter is different** from other that is correct username.
  > - **Username :** alterwind 
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Stage-1.%20Apprentice%20Labs/Photos/L2-6.png?raw=true" alt="Sample Image" width="700" height="600"></div>

---
#### Password Finding - Capture request in burp 
> - Now enter orignial username and wrong password
> - **Username :** alterwind
> - **Password :** 1234

- Now Clear all payload then Select payload on **$1234$** as password
> - Copy the Username from the list given in Lab (Candidate username)
> - [Password List from Lab](Stage-1.%20Apprentice%20Labs/Payload%20%26%20Scripts/Password%20List.txt)

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Stage-1.%20Apprentice%20Labs/Photos/L2-7.png?raw=true" alt="Sample Image" width="700" height="600"></div>

---
#### Attack Started for Password
- In this you can find right **Password** by Status code.
> - Note - If the username is correct in Brute-force Attack, the status code is always **302** (that is password).
> - **Password :** dragon

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Stage-1.%20Apprentice%20Labs/Photos/L2-8.png?raw=true" alt="Sample Image" width="700" height="600"></div>

---
#### Logged in Successfully
> - **Username -** alterwind
> - **Password -** dragon

- After Submit Credential , i got logged in Successfully.

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Stage-1.%20Apprentice%20Labs/Photos/L2-final.png?raw=true" alt="Sample Image" width="700" height="600"></div>

> - We Got a message after Solving the Lab
- **Congratulations, You solved the Lab.**

---
---


# Lab : 3 : 
# Username enumeration via subtly different responses
