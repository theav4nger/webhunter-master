# Recon with BurpSuite "სიყვარულით საქართველოდან"

### Download and run
* Download [Burp Suite](https://portswigger.net/burp/communitydownload)
* Run in terminal
```
java -jar burpsuite_community_v1.7.36.jar
```

### Set scope
* Scope --> Use advansed scope control --> Add --> host or IP range == target

![Scope](IMG FİLE)

### Spidering 
* Select all host in sitemap and Spider. 
* Do it again and again if new hosts are noticed.

### Recon for new Subdomains
* Collect new subdimains which is not detected by spider. in request | response body.
```
(http[s]?:\/\/)?((-)?[\w+\.]){1,20}domain\.com
```
Note: click + button and check regex && Auto-scroll to match when text changes

![ReconSubdomain](İMG FİLE)

### Extract endpoints from js file
note: regex taken from Linkfinder by GerbenJavado
```
(?:"|')(((?:[a-zA-Z]{1,10}://|//)[^"'/]{1,}\.[a-zA-Z]{2,}[^"']{0,})|((?:/|\.\./|\./)[^"'><,;| *()(%%$^/\\\[\]][^"'><,;|()]{1,})|([a-zA-Z0-9_\-/]{1,}/[a-zA-Z0-9_\-/]{1,}\.(?:[a-zA-Z]{1,4}|action)(?:[\?|/][^"|']{0,}|))|([a-zA-Z0-9_\-]{1,}\.(?:php|asp|aspx|jsp|json|action|html|js|txt|xml)(?:\?[^"|^']{0,}|)))(?:"|')
```
![Endpoints](İMG FİLE

### Internal | External IP address
```
\b(?:[0-9]{1,3}\.){3}[0-9]{1,3}\b
```
![IP](İMG FİLE)
