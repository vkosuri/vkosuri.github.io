---
layout: post
title:  "Cannot Install Google Chrome. How do I fix it?"
author: vkosuri
categories: [ tips ]
image: assets/images/post02.jpeg
tags: [tips]
---
Install Google chrome on Ubuntu 14 LTS, I tried many methods to install google chrome on my developer machine, somehow I couldn't succeeded.
The below procedure help me to overcome this issue.

You probably need to enable the "universe" repository.

[How do I enable the "Universe" repository?](https://askubuntu.com/a/227788/409013)

Once you enable it, update your system and you should now be able to install google-chrome-stable.

``` 
sudo apt-get update
sudo apt-get install libgconf2-4 libnss3-1d libxss1

sudo apt-get install chromium-browser
```

That simple!