Bash Scripting
# IP Sweeper script
![805dede6aec186aa6b1c8dc6e9930149.png](../_resources/805dede6aec186aa6b1c8dc6e9930149.png)
![1b78694629f77db33b55724b0de52652.png](../_resources/1b78694629f77db33b55724b0de52652.png)
![d6bc973a20de9099fe28fc5a30146856.png](../_resources/d6bc973a20de9099fe28fc5a30146856.png)

```
#!/bin/bash

if [ "$1" == "" ]
then
echo "You forgot the IP address"
echo "Syntax: ./ipsweep.sh 192.168.0"
else

for ip in `seq 1 254`; do
ping $1.$ip -c 1 | grep "64 bytes" | cut -d " " -f 4 | tr -d ":" &
done
fi
```