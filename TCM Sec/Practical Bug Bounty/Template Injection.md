# Server Side Template Injection
Injecting payload to get rendered by templating engine on server.

## Lab 1
- Vulnerable to XSS

![d8fa760726b1f00805be8cf225f3e254.png](../_resources/d8fa760726b1f00805be8cf225f3e254.png)
**Functionality:** Displays input back.

**Passing server side template injection payloads from burpsuite to check for execution of statement**
![77d8c8cd15067dedefbdc141677e8e78.png](../_resources/77d8c8cd15067dedefbdc141677e8e78.png)
![a09ba33ec3161e1f2e5428c7d609fd2f.png](../_resources/a09ba33ec3161e1f2e5428c7d609fd2f.png)

*Error disclosing information of templating engine*
![d0bad9569656feb3b698a2cb7410ae13.png](../_resources/d0bad9569656feb3b698a2cb7410ae13.png)
![511d0dc4e5f1dd0bbfd56aa477785ef3.png](../_resources/511d0dc4e5f1dd0bbfd56aa477785ef3.png)

**More payloads**
- *https://book.hacktricks.xyz/pentesting-web/ssti-server-side-template-injection*
- *https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/Server%20Side%20Template%20Injection#twig*

![cca1bfd1931bbff74ee2067d84d66dda.png](../_resources/cca1bfd1931bbff74ee2067d84d66dda.png)
![44549103bf7620a1161c9655aba97c73.png](../_resources/44549103bf7620a1161c9655aba97c73.png)

## Lab 2
- Vulnerable to XSS.
- Maybe vulnerable to LFI (apache version disclosure on invalid filename)

*Finding:* Client side have template code
![30ad1b6ef123534cada96fd3bf17d19c.png](../_resources/30ad1b6ef123534cada96fd3bf17d19c.png)

**On edit, POST request is sent with url encoded of HTML which returns the rendered template which is executing payload.**
![9d3b050db500d77fe4dd57335b5b5741.png](../_resources/9d3b050db500d77fe4dd57335b5b5741.png)
![3bda501a875bb7d0aa1e484905ddcb32.png](../_resources/3bda501a875bb7d0aa1e484905ddcb32.png)

**Also throwing error on invalid payloads which displays template engine used - twig**
![ec9ce726ff78f51752a276cc8bd5232d.png](../_resources/ec9ce726ff78f51752a276cc8bd5232d.png)

**With burp repeater**
![1410c639b01a779ed17a59fd1e7bba93.png](../_resources/1410c639b01a779ed17a59fd1e7bba93.png)
**Steps:**
1. Generate card with any name
2. Click on edit and paste the SSTI payload for twig and hit save changes
![8ed6b82f0ef507075b0ece609ce6e9e3.png](../_resources/8ed6b82f0ef507075b0ece609ce6e9e3.png)
3. After that you'll see executed results but shortly it gets replaced by payload again.![e65c72277dda43149f98faf0a1bdd153.png](../_resources/e65c72277dda43149f98faf0a1bdd153.png)
4. Click on start again and resend it. You'll see the result. ![2e8c87bbc6be6d3373853a605ea879f7.png](../_resources/2e8c87bbc6be6d3373853a605ea879f7.png)