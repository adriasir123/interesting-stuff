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
cat /home/atlas/.etchosts >> /etc/hosts
```

Make the script executable:

```
sudo chmod +x /root/update_hosts.sh
```

Now we run it to update our hosts file:

```
sudo /root/update_hosts.sh
```

After this step, our hosts file will be in place. 

Next? We can add a cron job to update this file automatically:

```
crontab -e
```

We are going to insert the following:

```
59 23 * * * /root/update_hosts.sh
```

This job runs every day at 23:59.

Remember, if we need to add something to the hosts file we now want to add it to ~/.etchosts and then run the script to update /etc/hosts.

# Human-readable Cron jobs

Use this: https://crontab.guru/

# Cleaning your laptop

https://www.youtube.com/watch?v=M_kr3FmsSUE

**Important note about the video above**: *read the comments*, not everything in the video should be done *exactly* as he says.

# Hide Firefox top tabs

If you are using Tree Style Tabs, you might want to hide the top tabs, do it this way: <https://medium.com/@Aenon/firefox-hide-native-tabs-and-titlebar-f0b00bdbb88b>

# Make your Nvidia work in Debian 11

<https://linuxhint.com/install-nvidia-drivers-debian-11/>
<https://www.server-world.info/en/note?os=Debian_11&p=nvidia&f=1>
