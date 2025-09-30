<h2 align="center">👨🏻‍💻Authentication vulnerabilities - Listing of Labs🆔</h2>

> - [Lab-2 { Username enumeration via subtly different responses }](https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Stage-2.%20Practitioner%20Labs/PractitionerLab.md#lab--2---practitioner-)

> - [Lab-3 {Username enumeration via response timing }](https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Stage-2.%20Practitioner%20Labs/PractitionerLab.md#lab--3---practitioner-)


---

<h1 align="center">👨🏻‍💻Authentication vulnerabilities🆔</h1>

---

# Lab : 2 : { Practitioner }
# Username enumeration via subtly different responses
* To solve the lab, enumerate a valid username, brute-force this user's password, then access their account page.
* It uses some methodologies to find real username and password.

---
#### This lab is subtly vulnerable to username enumeration and password brute-force attacks. 
 - It has an account with a predictable username and password.

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/Lab-2.png" alt="Sample Image" width="700" height="600"></div>

---
#### I use dummy credentials and then perform username enumeration with Burp Suite.
 - Username : abcd
 - Password - 1234
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L2-2.png" alt="Sample Image" width="700" height="600"></div>

---
#### Username Finding - Capture request in burp 
- Then find the original request
- **Request is confirm by your credential entered**
- Send to intruder.
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L2-3.png" alt="Sample Image" width="700" height="600"></div>

---
#### Position & Payload Section
- Clear all payload then Select payload on **$abcd$** as username
> - Copy the Username from the list given in Lab (Candidate username)
> - [Username List from Lab](Stage-1.%20Apprentice%20Labs/Payload%20%26%20Scripts/Username%20List.txt)

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L2-4.png" alt="Sample Image" width="700" height="600"></div>

---
#### Intruder -> Options 
- Grep - Extract
- Add > **Fetch response**
- Find the **Invalid username and Username** and select to highlight it.
- Then click **Ok**
  
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L2-5.png" alt="Sample Image" width="700" height="600"></div>

---
#### Attack Started for Username
- In this you can't find right username by Status code.
- In this, you get a **another section after adding (Grep-Extract)**
- **One parameter is different** from other that is correct username.
  > - **Username :** alterwind 
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L2-6.png" alt="Sample Image" width="700" height="600"></div>

---
#### Password Finding - Capture request in burp 
> - Now enter orignial username and wrong password
> - **Username :** alterwind
> - **Password :** 1234

- Now Clear all payload then Select payload on **$1234$** as password
> - Copy the Username from the list given in Lab (Candidate username)
> - [Password List from Lab](Stage-1.%20Apprentice%20Labs/Payload%20%26%20Scripts/Password%20List.txt)

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L2-7.png" alt="Sample Image" width="700" height="600"></div>

---
#### Attack Started for Password
- In this you can find right **Password** by Status code.
> - Note - If the username is correct in Brute-force Attack, the status code is always **302** (that is password).
> - **Password :** dragon

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L2-8.png" alt="Sample Image" width="700" height="600"></div>

---
#### Logged in Successfully
> - **Username -** alterwind
> - **Password -** dragon

- After Submit Credential , i got logged in Successfully.

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L2-final.png" alt="Sample Image" width="700" height="600"></div>

> - We Got a message after Solving the Lab
- **Congratulations, You solved the Lab.**

---
---

# Lab : 3 : { Practitioner }
# Username enumeration via Response Timing
- This lab is vulnerable to username enumeration using its response times. 

---
#### To solve the lab, enumerate a valid username, brute-force this user's password, then access their account page.
> - Your credentials: for dummy login 
> - **Useranme :** wiener
> - **Password :** peter

- The lab also implements a form of IP-based brute-force protection. However, this can be easily bypassed by manipulating HTTP request headers.

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/Lab-3.png" alt="Sample Image" width="700" height="600"></div>

---
#### Access the Lab for Testing
- Enter the credential and click to login
- **Capture the request** in Burp as below
- Send the original request to **Repeater** Tab
  
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L3-2.png" alt="Sample Image" width="700" height="600"></div>

---
#### Check Repeater Tab (Wrong Credential)
> - Understand How it works
- When Username is incorrect and password is long (Response time has same like all response)
- Here credential is wrong (test)
- Focus on Response Time (193 milis)
  
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L3-3.png" alt="Sample Image" width="700" height="600"></div>

---
#### Check Repeater Tab (Correct Username)
> - Check response timing when username is correct
- When Username is correct and password is long (Response time is increased)
- Focus on Response Time (1651 milis)
> - Means username is correct then it checks the password otherwise not checked.
- Now for username enumeration, go with IP-based brute-force
- Add { X-Forwarded-For : 1 } in request for ip based enumeration
- Send the request from Repeater to Intruder
  
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L3-4.png" alt="Sample Image" width="700" height="600"></div>

---
#### Intruder section for Attack
- 
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L3-5.png" alt="Sample Image" width="700" height="600"></div>
