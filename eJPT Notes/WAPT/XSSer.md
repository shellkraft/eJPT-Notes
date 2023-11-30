
### What is XSS ?

Cross-site scripting is a type of security vulnerability that can be found in some web applications. XSS attacks enable attackers to inject client-side scripts into web pages viewed by other users.

### How to use `XSSer` for reflected `XSS` ?

1. Enter text in the input prompt in which we want to look for `XSS` vulnerability. Use `Burp` to capture the POST request.

2. Now we can use XSSer on the target and set the payload `-p` to the POST request. In our case, this web-page performs a DNS lookup.
```
xsser --url "http://<target-ip>/index.php?page=dns_lookup.php" -p "target_hots=XSS&dns-lookup-php-submit-button=Lookup+DNS"
```
- We can also use the `--auto` option to check how vulnerable the web page is.