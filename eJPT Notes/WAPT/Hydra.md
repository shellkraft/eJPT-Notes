
### Attacking HTTP Login Form with Hydra

**1. Brute-Force Approach for Web-App Login**

- The goal is to brute-force the login page of a web application to uncover both the username and password.

**2. Configuration Requirements for the Attack**

- To execute the attack successfully, gather the necessary information by examining the target login page's source code or inspecting the request header using tools like Burp.
  - Identify the HTTP method employed by the login form.
  - Determine the login form's destination.
  - Identify the variable names for username and password.
  - Note the security level and login button type (submit).
  - Recognise the message displayed for invalid credentials.

**3. Initiate the Brute-Force Attack**

- With the required values in hand, launch the attack using Hydra:
```bash
hydra -L <user-file> -P <pass-file> <target-ip> http-post "/login.php:login=^USER^&password=^PASS^&security_level=0&form=submit:<invalid-credential-message>"
```
  
  - Customise the parameters in the `http-post` section based on the identified values from step 2.
