
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

![[Pasted image 20231125004837.png]]

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

![[Pasted image 20231126183209.png]]

![[Pasted image 20231126181809.png]]

4. We can check the site map in our Target tab and add targets from there to our scope. The traffic of the out of scope targets won't be recorded. 