
The Zed Attack Proxy (ZAP) is an easy to use integrated penetration testing tool for **finding vulnerabilities in web applications.**

### Enumerating Directories and Files with ZAProxy

**1. Launching ZAProxy and Configuring Manual Explore**

- Open ZAProxy and navigate to the Manual Explore tab.
  - Input the target URL.
  - Enable HUD for a user-friendly interface.
  - Choose the browser with the HUD overlay.
  - Launch the browser to open the target web page.

**2. Navigating and Capturing Information**

- Manually explore the web page, and ZAProxy will automatically capture details like response headers, adding them to the `Sites` tab.

**3. Including Login POST Request in Context**

- Right-click on the login POST request and include it in the context.
  ```
  Right Click > Include in Context > Default Context
  ```

**4. Configuring Session Properties**

- Navigate to session properties:
  - Under `Default Contexts`, select `Authentication`.
  - Choose `Form-based Authentication`.
  - Specify the target login form and username parameter.
  - Set the Regex pattern identified in the Logged-out response message to `Login`.
  - Under `Users`, enable the logged-in user.

**5. Enabling Forced User Mode**

- Activate forced user mode from the toolbar.

**6. Adding the Whole Site to Default Context**

- Include the entire site in the default context.

**7. Context Setup**

- The context is now established with the login.php page, authentication, and the root URL.

**8. Initiating Attack on the Root URL**

- Right-click on the root URL and select Attack > Spider.
  - Set the user to the one logged in.
  - Commence the scan.
  - The scan will systematically explore the entire site, adding all directories and files to the context.
### Vulnerability Scan with ZAProxy

**1. Initiating Active Scan on Root URL**

- After enumerating directories and files, begin an active scan on the root URL:
  ```
  Right Click > Attack > Active Scan
  ```

**2. Configuring the Scan**

- Set the 'User' to the logged-in user from the drop-down menu.
- Start the scan.

**3. Analyzing Vulnerabilities**

- Review the Alerts tab to examine vulnerabilities identified by ZAProxy.
  - The tab displays URLs with vulnerabilities and, if applicable, the payload causing the vulnerability (e.g., for XSS or SQLI).

**4. Interacting with HUD Overlay**

- To input commands in the browser with the HUD overlay, place it out of scope using HUD options.