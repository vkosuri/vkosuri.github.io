---
layout: post
title:  "Know linux task scheduler and automate"
author: vkosuri
categories: [ linux ]
image: https://cdn.pixabay.com/photo/2017/10/24/20/12/hands-2886016_960_720.png
tags: [featured]
toc: true
---
The most popular task scheduler for Linux flavours are support ``crontab``. You can automate regular boring tasks using powerful Linux shell scripts.

More information found here crontab man page [http://man7.org/linux/man-pages/man5/crontab.5.html](http://man7.org/linux/man-pages/man5/crontab.5.html)

> To view a cron job

```  bash
crontab -l
```

> To edit a cron job

```  bash
crontab -e
```

> To view a cron job on specific user

```  bash
sudo crontab -l -u
```

> To edit a cron job on specific user

```  bash
sudo crontab -e -u
```
An example cron job delete files in a specified location more than one month

``` bash
5 4 * * * find /home/malli/Results/Logs/* -type f -name '*.log' -mtime +1 -exec rm -f {} \
```
This cron job will run every day morning 4 hours 5 minutes

> Crontab Format:

``MIN HOUR DOM MON DOW CMD``
*Format Meanings and Allowed Value:*
<pre>
MIN     Minute field    0 to 59
HOUR    Hour field      0 to 23
DOM     Day of Month    1-31
MON     Month field     1-12
DOW     Day Of Week     0-6
CMD     Command     Any command to be executed.
</pre>

> Restart cron with latest data

```  bash
service crond restart
```
