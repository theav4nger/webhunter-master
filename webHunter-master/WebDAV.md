# WebDAV 

WebDAV modülünün doğru şekilde yapılandırıldığını doğrulayın.


```
CONTENT_TYPE = Headers([('content-type', 'application/xml; charset="utf-8"')])
```

### Test SEARCH method

```
<?xml version='1.0'?>
  <g:searchrequest xmlns:g='DAV:'>
  <g:sql>Select 'DAV:displayname' from scope()</g:sql>
</g:searchrequest>
```

#### Detect
```
xmlns:a="DAV:"

```


Yanıt 200, 300 ise dizin adı ve yolu ile HTTP ARAMA yöntemi ile dizin listesi bulundu



### Test PROPFIND method

```
<?xml version='1.0'?>
  <a:propfind xmlns:a='DAV:'>
  <a:prop>
  <a:displayname:/>
  </a:prop>
"</a:propfind>
```

###  Tests PUT method.


```
headers = Headers([('content-type', 'text/plain')])

```

Dosya yüklenirse kaynakta HTTP PUT yöntemiyle dosya yüklemesi bulundu

DAV yanlış yapılandırılmış görünüyor. Web sunucusu 500 hata koduyla yanıt verdi. Çoğu durumda bu, DAV uzantısının bir şekilde başarısız olduğu anlamına gelir.

403 DAV doğru şekilde yapılandırılmış ve PUT yöntemini kullanmanıza izin veriyor gibi görünüyorsa, ancak dizin web sunucusunun ona yazmasına izin verecek doğru izinlere sahip değilse

Bu teknik, WebDAV yapılandırma hatalarını bulur. Bu hatalar genellikle bir web uygulaması hataları yerine sunucu yapılandırma hatalarıdır. Bu tür güvenlik açıklarını kontrol etmek için, WebDAV'ın etkin olduğu bir dizine bir dosya PUT yapmayı deneyin, eğer dosya başarıyla yüklenirse, bir hata bulduk
