# Block Ads and more with your Hosts file

Sources:  
https://www.putorius.net/block-unwanted-advertisements-on.html  
https://winhelp2002.mvps.org/hosts.htm  
https://winhelp2002.mvps.org/hosts.txt

We have to copy our last hosts file:

```
cp /etc/hosts ~/.etchosts
```

Now we create the script to update the hosts file:

```
sudo nano /root/update_hosts.sh
```

Its contents...

```
#!/bin/bash
cd /tmp
wget http://winhelp2002.mvps.org/hosts.txt
rm /etc/hosts
mv hosts.txt /etc/hosts
cat ~/.etchosts >> /etc/hosts
```

Make the script executable:

```
sudo chmod +x /root/update_hosts.sh
```

Now we run it to update our hosts file:

```

```


