## Patching:

- Step 1: The source code will be available under the public folder within the htdocs folder within the xampp folder. The applications’ vulnerability will be in the contact.php file.

- Step 2: Uncomment the vulnerable code and save the contact.php file. The payload will be available after the GET method(1st line) in the request.(through the script tags). When send it, it will be available in the response. Right click the Response, click show Response in Browser, copy the URL and paste it in the Burp Suite Chromium Browser. Then see the alert pop up. Able to see, in the response , inside the form tags, the quote will be escaped to come to the script tags which will inject the JavaScript code. Then the XSS issue will arise after the http smuggling.

- Step 3: To patch, comment the vulnerable piece of code and uncomment the patched code, then save it and send the request again. You will see the payload is encoded in the form tags. When  I right click, show response in browser, you will see that the pop up does not appear anymore. So escaping from the quote is not possible.

```
GET /public/contact.php?test=12"><script>alert(1)</script> HTTP/1.1
Host: localhost
Cache-Control: max-age=0
sec-ch-ua: "Not;A=Brand";v="99", "Chromium";v="106"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/106.0.5249.62 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: none
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9
Connection: close
```