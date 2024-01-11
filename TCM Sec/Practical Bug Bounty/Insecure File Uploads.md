Resource for insecure files: https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Upload%20Insecure%20Files/

https://appsecexplained.gitbook.io/appsecexplained/common-vulns/insecure-file-upload

# Bypassing client side file type restrictions
Can't upload from browser.
![9803ecbc7f807076fcf9ae625f749472.png](../_resources/9803ecbc7f807076fcf9ae625f749472.png)

**Changing file content in burp to upload**
*From*:
![c55eac9c475bdcf0c9fc2e54e817530b.png](../_resources/c55eac9c475bdcf0c9fc2e54e817530b.png)
*To*:
![1dd5e266aca719731e68d81a19960bab.png](../_resources/1dd5e266aca719731e68d81a19960bab.png)

and we can see the results in uploaded file section.
![cc6fec115e66322db79de5d7bc1f9a73.png](../_resources/cc6fec115e66322db79de5d7bc1f9a73.png)

Here is uploaded file content on server.
Directory can be found by FUZZING with FFUF.
![568b75bfd314fd163e5312818c4df477.png](../_resources/568b75bfd314fd163e5312818c4df477.png)

**Getting shell command execution**
![871ede1f8817523ceffc25dcb78a6dcc.png](../_resources/871ede1f8817523ceffc25dcb78a6dcc.png)
![2bdd323b66246e980dbdf15f1712881c.png](../_resources/2bdd323b66246e980dbdf15f1712881c.png)
![d9a1191560cc37ea9db22d2d5d9a4a2e.png](../_resources/d9a1191560cc37ea9db22d2d5d9a4a2e.png)

**Gaining reverse shell:**
![004dc1439240f1dc73ad123e8c318a5d.png](../_resources/004dc1439240f1dc73ad123e8c318a5d.png)
![780894eaa9dd713373806419130e0923.png](../_resources/780894eaa9dd713373806419130e0923.png)
![20af5a86c3eee50cb00ffb4563715fae.png](../_resources/20af5a86c3eee50cb00ffb4563715fae.png)

# Bypass server side restrictions
- Null bytes attack ![4af189af2a8418cd20f9b42dcb6aa510.png](../_resources/4af189af2a8418cd20f9b42dcb6aa510.png)
- Spoof file name like `t1.php` to `t.png` etc
- Change Content-Type header
- Magic bytes - First few lines of file which tells what type of file is.
	Method to check manually:
	![5961b18c72176dfbd742668194ab629f.png](../_resources/5961b18c72176dfbd742668194ab629f.png)
	 [Magic bytes of all files](https://en.wikipedia.org/wiki/List_of_file_signatures)
	 
**Embedding payload in magic byte**
![52e619088bed379f5803f358d2e97c10.png](../_resources/52e619088bed379f5803f358d2e97c10.png)


Payload:
![7697270f812f4cfe0bcadc41dc679945.png](../_resources/7697270f812f4cfe0bcadc41dc679945.png)
Result:
![29e2fdee927ca3b9eafaac4d8562407d.png](../_resources/29e2fdee927ca3b9eafaac4d8562407d.png)
*Sometimes error will occur when executing file*
***To solve that we have to adjust our payload position and sometimes remove the chars after it.*** 
**You can use line number to remove chars before or after which is causing error.**

**Let's remove all chars after php payload**
Payload:
![da8f6723d1ee68a5d92f461e2be92a0e.png](../_resources/da8f6723d1ee68a5d92f461e2be92a0e.png)

Result:
![f8132df0312ee62f56b06dc66a8fa550.png](../_resources/f8132df0312ee62f56b06dc66a8fa550.png)
**Worked!🎉🎉🎉 
If in case not works try to remove line shown in error or if error is not shown just remove chars before payload**

**Removed some chars before payload**
Payload:
![ef0a3f6a90c36b49d92993c51b70017c.png](../_resources/ef0a3f6a90c36b49d92993c51b70017c.png)
Result:
![b79cea6b3ca22fe4fa91f3852b0682a9.png](../_resources/b79cea6b3ca22fe4fa91f3852b0682a9.png)
![a548ea2530754df58131274a959ad576.png](../_resources/a548ea2530754df58131274a959ad576.png)

### If file extension is getting blocked, search for other extensions for same file type 
**Like for php**
![b9dc42098fa4d4f93fc31fe454d1dace.png](../_resources/b9dc42098fa4d4f93fc31fe454d1dace.png)
**Best practice is to use "allow list" like ['.png'] instead of adding other file extensions in "block list" .**

![0e38876371674a5ecf245b16bb85dde5.png](../_resources/0e38876371674a5ecf245b16bb85dde5.png)

## Lab 3 Challenge
### Payload 1:
![a9d2402b99817325fc62c7019af5c904.png](../_resources/a9d2402b99817325fc62c7019af5c904.png)

### Payload 2:
![0d76391653a51cc5651f4922c2df6440.png](../_resources/0d76391653a51cc5651f4922c2df6440.png)
**Not worked**
![e32585f5e3a85dd17b5a69e6f42b4e80.png](../_resources/e32585f5e3a85dd17b5a69e6f42b4e80.png)

### Payload 3:
![4eda562195e5b5d71f918af35982e9fb.png](../_resources/4eda562195e5b5d71f918af35982e9fb.png)
![e6fc787c6cec70d946e01a85159e7c8e.png](../_resources/e6fc787c6cec70d946e01a85159e7c8e.png)

### Payload 4:
![08df3d7695d2911e3889b23043ec6624.png](../_resources/08df3d7695d2911e3889b23043ec6624.png)
**Woah Worked!**
![11fc452dfdd68efb33fddfd339bc7a72.png](../_resources/11fc452dfdd68efb33fddfd339bc7a72.png)

**Let's go for reverse shell**
Payload:
![6d123dc0b09def09aba360707ad33769.png](../_resources/6d123dc0b09def09aba360707ad33769.png)

Tab opened a reverse shell:
![818412b171861df264bd469373c6c521.png](../_resources/818412b171861df264bd469373c6c521.png)

![d50eaeda51eab44c218979fdf7f3026a.png](../_resources/d50eaeda51eab44c218979fdf7f3026a.png)
