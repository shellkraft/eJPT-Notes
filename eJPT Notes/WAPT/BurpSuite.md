
### Directory Enumeration with `BurpSuite`

1. Open the web server in the browser.

2. Turn Burp proxy on from the `FoxyProxy` menu.

3. Turn intercept on, and intercept the traffic. 

4. Send the traffic to the `intruder` from the action menu.

5. In the `intruder` menu, we need to configure the positions where payloads will be inserted. In our case, we'll clear all our positions with the `clear` button.

6. Click `Add` button to add a new payload position. In our case, the payload will be `§name§`. This will use GET request to enumerate the directories. 
```
GET /§name§ HTTP/1.1
```

![image](https://github.com/B4PHOM3T/eJPT-Notes/assets/89618500/17efa7e2-2e66-4f0a-94a7-43c1bf7fd062)

6. Set the attack type to Sniper. 
	+ **Sniper Attacks:** This involves replacing a specified part of a request with payloads from a list. For example, you might replace a parameter value with a list of potential malicious values to see how the application responds.
	+ **Cluster Bomb Attacks:** This is similar to Sniper attacks, but it involves iterating through multiple payloads at once for each position being tested.
	+ **Pitchfork Attacks:** This allows you to use multiple payloads at different positions within the request, providing a more customized and targeted approach.

7. We will load our word-list in the `payload options` menu. We'll be using `/usr/share/wordlists/dirb/common.txt`.  We can also add custom words of our choice. After adding, make sure to remove any blank spaces between the words. 

8. Now we can click `Start Attack` button on the top right to start the directory busting. 

### Passive Crawling with `BurpSuite`

1. Use `FoxyProxy` to connect with `Burp` on the browser and turn intercept on.

2. When we refresh a page on our browser, Burp should capture the outbound GET request. 

3. Even if intercept is turned off, Burp will still capture the traffic as long as the Proxy is turned on in our browser. The traffic will be logged in the HTTP history in the Proxy tab. 

![image](https://github.com/B4PHOM3T/eJPT-Notes/assets/89618500/675efc70-46b1-42b7-89f9-2238d1a6881e)

![image](https://github.com/B4PHOM3T/eJPT-Notes/assets/89618500/1203bcc8-d7b5-4a2e-b689-11da4a83a636)

4. We can check the site map in our Target tab and add targets from there to our scope. The traffic of the out of scope targets won't be recorded. 

### HTTP Basic Authentication


**What is HTTP Basic Authentication ?**
Basic access authentication (Basic Auth) is a simple method for a user agent to provide a username and password to access a page.

![[default_auth.png]]

### Attacking HTTP Basic Auth with Burp Suite

**1. Locate the Basic Authentication Page**

- Identify the basic authentication page within the web app, typically found in the `basic` directory.

**2. Capture the GET Request with Burp Suite**

- Begin by inputting text in the login prompt and use Burp Suite to capture the corresponding GET request.

**3. Decode Authorization Variable**

- In the captured request header, locate the `Authorization` variable containing Base64-encoded text from the login prompt.
- Decode the text by right-clicking, selecting `Convert selection > Base64 > Base64-decode`.
- The result should be in the format `<user>:<pass>`.

**4. Send Header to Intruder**

- Transfer the decoded `<user>:<pass>` value to the Intruder tool in Burp.

**5. Configure Payloads for Brute-Force**

- Load a password word-list in the Payloads tab.
- Since we know the username (`admin`), set `admin:` as the prefix in Payload Processing:
  ```
  Add > Select Rule Type > Add Prefix
  ```
  
**6. Add Base64 Encoding Rule**

- As both user and password must be Base64 encoded, add a Payload Processing rule:
  ```
  Add > Select Rule Type > Encode > Base64-encode
  ```

**7. Initiate the Attack**

- Start the attack; Burp will systematically test payloads based on the configured rules.

**8. Analyze Status Codes**

- Monitor status codes with each attempt. Look for a 301 status code, indicating a redirect and potential valid credentials.

**9. Identify Valid Request**

- When a 301 status code is found, open the corresponding request, select the Base64 encoded payload, click Action, and send it to the Decoder.

**10. Decode Base64 Encoded Payload**

- In the Decoder, select the Base64 encoded payload, click Smart Decode.
- Further decode the result by choosing `Decode as.. > Base64`. This reveals the valid password.
