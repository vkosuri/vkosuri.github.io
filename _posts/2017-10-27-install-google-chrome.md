---
layout: post
title:  "Cannot Install Google Chrome. How do I fix it?"
author: vkosuri
categories: [ browser, tutorial ]
image: https://www.google.com/chrome/static/images/chrome-logo.svg
tags: [sticky]
---

You probably need to enable the "universe" repository.

    [How do I enable the "Universe" repository?](https://askubuntu.com/a/227788/409013)

Once you enable it, update your system and you should now be able to install google-chrome-stable.
``` 
sudo apt-get update
sudo apt-get install libgconf2-4 libnss3-1d libxss1

sudo apt-get install chromium-browser
```

That simple!