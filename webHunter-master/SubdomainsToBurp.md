# Subdomains to Burp Suite
Alt yöneticileri dosyadan Burp suite by [@tvmpt](https://twitter.com/tvmpt)

```cat <file-name> | parallel -j 200 curl -L -o /dev/null {} -x 127.0.0.1:8080 -k -s```
