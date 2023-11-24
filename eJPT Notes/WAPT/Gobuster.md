
### Directory enumeration with `Gobuster`

- Gobuster is a command line tool like `dirb` for enumerating directories. It's written in `GoLang`. 

### How to use `Gobuster` ?

1. We can brute-force directories using the following command. We are using `dir` option for directory enumeration. 
```
gobuster dir -u httpe://<target-ip> -w <wordlist>
```
- We can use the `dirb` word list. `/usr/share/wordlists/dirb/common.txt`
- This will also tell us the status codes for each directory.

2. We can silence directories with a particular status code. In our case, we'll silence the directories with 404 and 403 status codes as these status codes generally indicate that the directory doesn't exist or it is inaccessible. 
```
gobuster dir -u httpe://<target-ip> -w <wordlist> -b 403,404
```

3. We can also display only a certain file types in our result too. 
```
gobuster dir -u httpe://<target-ip> -w <wordlist> -x .php,.xml,.txt -r
```

4. We can also enumerate sub-directories by including the main directory in the URL. `-u http://<target-ip>/<directory>`
