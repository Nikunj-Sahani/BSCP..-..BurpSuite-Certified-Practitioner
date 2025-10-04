<h2 align="center">👨🏻‍💻Authentication vulnerabilities - Listing of Labs🆔</h2>

> - [Lab - 2 { Username enumeration via subtly different responses }](https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Stage-2.%20Practitioner%20Labs/PractitionerLab.md#lab--2---practitioner-)

> - [Lab - 3 { Username enumeration via response timing }](https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Stage-2.%20Practitioner%20Labs/PractitionerLab.md#lab--3---practitioner-)

> - [ Lab - 4.1 { Broken brute-force protection, IP block - (1st METHOD) }](https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/edit/main/Stage-2.%20Practitioner%20Labs/PRACTITIONERLAB.md#lab--41---practitioner-)

> - [ Lab - 4.2 { Broken brute-force protection, IP block - (2nd METHOD) }](https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/edit/main/Stage-2.%20Practitioner%20Labs/PRACTITIONERLAB.md#lab--42---practitioner-)


---

<h1 align="center">👨🏻‍💻Authentication vulnerabilities🆔</h1>

---

# Lab : 2 : { Practitioner }
# Username enumeration via subtly different responses
* To solve the lab, enumerate a valid username, brute-force this user's password, then access their account page.
* It uses some methodologies to find real username and password.

---
### This lab is subtly vulnerable to username enumeration and password brute-force attacks. 
 - It has an account with a predictable username and password.

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/Lab-2.png" alt="Sample Image"></div>

---
### I use dummy credentials and then perform username enumeration with Burp Suite.
 - Username : abcd
 - Password - 1234
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L2-2.png" alt="Sample Image"></div>

---
### Username Finding - Capture request in burp 
- Then find the original request
- **Request is confirm by your credential entered**
- Send to intruder.
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L2-3.png" alt="Sample Image"></div>

---
### Position & Payload Section
- Clear all payload then Select payload on **$abcd$** as username
> - Copy the Username from the list given in Lab (Candidate username)
> - [Username List from Lab](Stage-1.%20Apprentice%20Labs/Payload%20%26%20Scripts/Username%20List.txt)

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L2-4.png" alt="Sample Image"></div>

---
### Intruder -> Options 
- Grep - Extract
- Add > **Fetch response**
- Find the **Invalid username and Username** and select to highlight it.
- Then click **Ok**
  
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L2-5.png" alt="Sample Image"></div>

---
### Attack Started for Username
- In this you can't find right username by Status code.
- In this, you get a **another section after adding (Grep-Extract)**
- **One parameter is different** from other that is correct username.
  > - **Username :** alterwind 
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L2-6.png" alt="Sample Image"></div>

---
### Password Finding - Capture request in burp 
> - Now enter orignial username and wrong password
> - **Username :** alterwind
> - **Password :** 1234

- Now Clear all payload then Select payload on **$1234$** as password
> - Copy the Password from the list given in Lab (Candidate password)
> - [Password List from Lab](Stage-1.%20Apprentice%20Labs/Payload%20%26%20Scripts/Password%20List.txt)

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L2-7.png" alt="Sample Image"></div>

---
### Attack Started for Password
- In this you can find right **Password** by Status code.
> - Note - If the username is correct in Brute-force Attack, the status code is always **302** (that is password).
> - **Password :** dragon

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L2-8.png" alt="Sample Image"></div>

---
### 🎇 LAB Solved 🥳
> - **Username -** alterwind
> - **Password -** dragon

- After Submit Credential , i got logged in Successfully.

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L2-final.png" alt="Sample Image"></div>

> - We got a message after Solving the Lab
- **Congratulations, You solved the Lab.**

---
---

# Lab : 3 : { Practitioner }
# Username enumeration via Response Timing
- This lab is vulnerable to username enumeration using its response times. 

---
### To solve the lab, enumerate a valid username, brute-force this user's password, then access their account page.
> - Your credentials: for dummy login 
> - **Useranme :** wiener
> - **Password :** peter

- The lab also implements a form of IP-based brute-force protection. However, this can be easily bypassed by manipulating HTTP request headers.

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/Lab-3.png" alt="Sample Image"></div>

---
### Access the Lab for Testing
- Enter the credential and click to login
- **Capture the request** in Burp as below
- Send the original request to **Repeater** Tab
  
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L3-2.png" alt="Sample Image"></div>

---
### Check Repeater Tab (Wrong Credential)
> - Understand How it works
- When Username is incorrect and password is long **(Response time has same like all response)**
- Here credential is wrong (test)
- Focus on Response Time (193 milis)
  
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L3-3.png" alt="Sample Image"></div>

---
### Check Repeater Tab (Correct Username)
> - Check response timing when username is correct
- When Username is correct and password is long **(Response time is increased)**
- Focus on **Response Time (1651 milis)**
> - Means username is correct then it checks the password otherwise not checked.
- Now for username enumeration, go with IP-based brute-force
- Add { **X-Forwarded-For : 1** } in request for ip based enumeration
- Send the request from Repeater to Intruder
  
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L3-4.png" alt="Sample Image"></div>

---
### Intruder section for Attack (Position)
- Attack type- **Pitchfork**
> - In Pitchfork Attack - **2 Payload is mandatory**
- First Payload position - X-Forwared-For : **1**
- Second Payload position - Username : **wiener**
  
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L3-5.png" alt="Sample Image"></div>

---
### Intruder section for Attack (Payload)
- Payload Sets - 1
- **Number** (For X-forwarded)
- And choose number According to You
- I used here : 2 - **101 by step 1**

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L3-6.png" alt="Sample Image"></div>

---
### Intruder section for Attack (Payload)
- Payload Sets - 2
- Simple List (For username)
> - Copy the Username from the list given in Lab (Candidate username)
> - [Username List from Lab](Stage-1.%20Apprentice%20Labs/Payload%20%26%20Scripts/Username%20List.txt)

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L3-7.png" alt="Sample Image"></div>

---
### Attack initiated for Username
- In this you can't find right username by Status code.
- You can see at top Bar **Columns Section**
- In Columns Section *(Select Response Recieved)*
> - **Higher Response Time** is correct username.
> - **Username :** access

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L3-8.png" alt="Sample Image"></div>

---
### Attack initiated for Password
- Steps are same as username Finding
- Just change the username **wiener to access(Original)**
> - Then select payload position to **X-Forwarded and Password.**
> - Payload Sets 1 : **102 - 201** by step 1
> - Payloas Sets 2 : Password List
> - Copy the Username from the list given in Lab (Candidate username)
> - [Password List from Lab](Stage-1.%20Apprentice%20Labs/Payload%20%26%20Scripts/Password%20List.txt)
- Start the Attack
- In this you can find right username by **Status code only 302.**
> - **Password :** nicole

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L3-9.png" alt="Sample Image"></div>

---
### 🎇 LAB Solved 🥳
> - **Username -** access
> - **Password -** nicole
- After Submit Credential , i got logged in Successfully.
  
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L3-final.png" alt="Sample Image"></div>

> - We got a message after Solving the Lab
- **Congratulations, You solved the Lab.**

---
---

# Lab : 4.1 : { Practitioner }
# Broken brute-force protection, IP block (1st METHOD)
- This lab is vulnerable due to a logic flaw in its password brute-force protection. 

---
### To solve the lab, brute-force the victim's password, then log in and access their account page.
- Advanced users may want to solve this lab by using a macro or the Turbo Intruder extension. However, it is possible to solve the lab without using these advanced features.
> - Here we have username , find the password only.
> - Username : carlos
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/Lab-4a.png" alt="Sample Image"></div>

---
### Login Interface of Web
- Here i will login with given credential in the lab.
> - Username : **wiener**
> - Password : **peter**
> - Click Ok for loggin and capture the loggin details in Burp.

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L4-2b.png" alt="Sample Image"></div>

---
### Capture the Request in Burp Suite
- Find the original request in Burp
- Focus on Username and Password for Original Request
- Then Send the Original request in **Intruder Tab.**
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L4-3c.png" alt="Sample Image"></div>

---
### Intruder Tab - Username
Here We select both username and password payload in one request.
- Select Attack type : **PitchFork**
- Select payload position to *username*
- In Payload Section - **Payload 1 for wiener**
> - Simple List - **Our own Username payload that i made.**
> - Copy from here and paste it to your simple list.
> - [ Macro Username List ](https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Payload%20%26%20Scripts/Macro_user.txt)

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L4-4d.png" alt="Sample Image"></div>

---
### Intruder Tab - Password
- Select Attack type : **PitchFork**
- Select payload position to *password*
- In Payload Section - **Payload 2 for peter**
> - Simple List - **Our own Password payload that i made.**
> - Copy from here and paste it to your simple list.
> - [ Macro Password List ](https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Payload%20%26%20Scripts/Macro_pass.txt)

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L4-5e.png" alt="Sample Image"></div>

---
### Intruder Tab - Resource Pool
- If You did't get option of *Resource pool in Your burp* then **skip this 1st method and go for 2nd method.**
- Create new resource pool
- Click for check mark ✅
> - **Maximum concurrent request : 1**
> - Done - Now Start the Attack

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L4-6f.png" alt="Sample Image"></div>

---
### Attack Initiated 
- You got a status code of 302 (Real Password).
> - Password : **123321**

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L4-7g.png" alt="Sample Image"></div>

---
### 🎇 LAB Solved 🥳
- Credential for Login
> - Username : **carlos**
> - Password : **123321**
- After submitting , we got logged in successfully.
  
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L4-final.png" alt="Sample Image"></div>

> - We got a message after Solving the Lab
- **Congratulations, You solved the Lab.**

---
---

# Lab : 4.2 : { Practitioner }
# Broken brute-force protection, IP block (2nd METHOD)
- This lab is vulnerable due to a logic flaw in its password brute-force protection. 

---
### To solve the lab, brute-force the victim's password, then log in and access their account page.
- Advanced users may want to solve this lab by using a macro or the Turbo Intruder extension. However, it is possible to solve the lab without using these advanced features.
> - Here we have username , find the password only.
> - Username : carlos
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/Lab-4-a.png" alt="Sample Image"></div>

---
### Capture the Request in Burp Suite
- Here i will login with given credential.
> - Username : **wiener**
> - Password : **peter**
> - Click Ok for login and capture the login details in Burp.
> - Then Send the Original request in **Intruder Tab.**
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L4-2-b.png" alt="Sample Image"></div>

---
### Send in Intruder Tab
- In intruder tab , Go on Position.
> - **Change the username wiener to carlos.**
- Select payload position to password $1234$.
- Then Go on Payload in Intruder tab.
  
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L4-3-c.png" alt="Sample Image"></div>

---
### Intruder Tab - Payload
- Payload of Simple list
> - Copy the Password from the list given in Lab (Candidate password)
> - [Password List from Lab](Stage-1.%20Apprentice%20Labs/Payload%20%26%20Scripts/Password%20List.txt)

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L4-4-d.png" alt="Sample Image"></div>

---
### Project Options - Tab in Burp
- In Project option ➡️ Go to Session
- **Session Handling rules** at first ➡️ Click on **Add**
> - Open a tab ➡️ **Session Handling Rule editor**
> - Tab ➡️ Details 
> - **Rule Actions ➡️ Add**  ➡️ **Run a Macro**

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L4-5-e.png" alt="Sample Image"></div>

---
### Macro Editor - Details Tab
- Find the original Logged in request.
> - wiener & peter log details
- Then click ➡️ Ok ➡️ Ok
  
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L4-6-f.png" alt="Sample Image"></div>

---
### Session Handling Rule Editor - Details Tab
- After Editing
- You got a Macro rules in **Rule Actions**
> - **✅ run macro : Macro 1**

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L4-7-g.png" alt="Sample Image"></div>

---
### Session Handling Rule Editor - Scope Tab
- ➡️ URL Scope
- Tick it ✅ Include All URLs
- Click Ok to add Rules
  
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L4-8-h.png" alt="Sample Image"></div>

---
### Sessions ➡️ Session Handling Rule
- After all done it Back to session.
- Now You can see here **It add a New Rule.**
> - **✅ Rule 1** : target , Spider , Scanner , Intruder , Repeater.....
> - Now All Done
- **Go to Intruder tab & Start the Attack**
  
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L4-9-i.png" alt="Sample Image"></div>

---
### Attack Initiated 
- You got a status code of 302 (Real Password).
> - Password : **pass**

<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L4-10-j.png" alt="Sample Image"></div>

---
### 🎇 LAB Solved 🥳
- Credential for Login
> - Username : **carlos**
> - Password : **pass**
- After submitting , we got logged in successfully.
  
<div style="text-align: right;"><img src="https://github.com/Nikunj-Sahani/BSCP..-..BurpSuite-Certified-Practitioner/blob/main/Images/1.%20Authentication/L4-finall.png" alt="Sample Image"></div>

> - We got a message after Solving the Lab
- **Congratulations, You solved the Lab.**

