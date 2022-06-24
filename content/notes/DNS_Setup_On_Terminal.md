---
title: How to configue DNS Settings on Linux
date: 2022-06-02 12:00:00
tags:
    - Linux
categories:
- notes
keywords:
    - Linux
    - DNS
    - bash
---


# Manually Setting DNS Servers
1.1.1.1, 1.0.0.1

In the terminal you want to edit: `/etc/resolvconf.conf`

so in the terminal write:
```bash
sudo nvim /etc/resolvconf.conf
```

Then you will get something like this:
```bash
Configuration for resolvconf(8)  
# See resolvconf.conf(5) for details  
  
resolv_conf=/etc/resolv.conf  
# If you run a local name server, you should uncomment the below line and  
# configure your subscribers configuration files below.  
#name_servers=127.0.0.1  
  
# CloudFlare DNS  
# name_servers="1.1.1.1 1.0.0.1"
```

You want to **un-comment** the `name_servers` line and that's the file editing done!

Now lets update the environment with the command:
```bash
sudo resolvconf -u
```

The official docs from Manjaro on this can be found here:

[Manually Setting DNS Servers](https://wiki.manjaro.org/index.php/Networking)
