# Spidering with Gospider
[Gospider](https://github.com/jaeles-project/gospider)

### Collect Endpoints

URL'leri toplayın ve dosyaya kaydedin:
 
```
gospider -s http://HOST -d 16 -a -w -c 50 | grep -oP '(http|https)://[^/"].*' | cut -d "]" -f1 | tee OUTPUT_FILE
```

