# File Inclusion
## Local file inclusion
### Lab 1
https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/File%20Inclusion

![3ce9a6baf08332699e3019b28dc9080a.png](../_resources/3ce9a6baf08332699e3019b28dc9080a.png)
![f4da8102b6dd5cdf9b8d916e9da1e63a.png](../_resources/f4da8102b6dd5cdf9b8d916e9da1e63a.png)

### Lab 2
Recursive filter bypass:
`..././..././..././..././etc/passwd`
removal chars is quoted.
`."../"./."../"./."../"./."../"./etc/passwd`
After removing `../` from above we get
`../../../../etc/passwd` -> valid directory file

![23048530e27b534791692bb3150db278.png](../_resources/23048530e27b534791692bb3150db278.png)

## Remote file inclusion
Fetching remote files with server.
![0f73a29776a1b9141c86a1a4f1c9fb21.png](../_resources/0f73a29776a1b9141c86a1a4f1c9fb21.png)

### Getting local files with bypassing filters etc
![c9eea37af1f764511d76f6ddbd33d3f7.png](../_resources/c9eea37af1f764511d76f6ddbd33d3f7.png)

#### Base64 decoded
![4af0829c44b0b16f3c4091128b6ce675.png](../_resources/4af0829c44b0b16f3c4091128b6ce675.png)

# Remote Inclusion challenge lab
Solved using LFI file list using ffuf
**Size: 922 payload worked**

![db7a884cf50d4247b945285b784c4f24.png](../_resources/db7a884cf50d4247b945285b784c4f24.png)
![e48469532ab12a03354dd484be407e94.png](../_resources/e48469532ab12a03354dd484be407e94.png)
![ff96f5800c259f723809875d51d1494e.png](../_resources/ff96f5800c259f723809875d51d1494e.png)

# SQL Injection
Basics:
![66082ebf9b0766322a0c711fc64e0ccc.png](../_resources/66082ebf9b0766322a0c711fc64e0ccc.png)

Starting mysql:
![4a4f811e51b07d19324e6b14f68b9ba5.png](../_resources/4a4f811e51b07d19324e6b14f68b9ba5.png)