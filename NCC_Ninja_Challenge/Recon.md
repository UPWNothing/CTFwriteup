# Recon

## Recon 200 \#1
You can find robots.txt. In robotx.txt, there's an entry "Disallow: /secret.txt". Flag is in this file.   
Flag: _flag{93bfb2f736105e251ff6395945ec9abcc1ee6a58bb4f9100a9c072c19fb393d8}_  


## Recon 200 \#2
This time, we cannot get any informatin through robots.txt. However, robots.txt is not the only way to inform search engines the URLs on the website. We can get the flage through /sitemap.xml  
Flag: _flag{3853f9a65995d05f56abc2fed663ad78848309bd064e75d16ba41070390f1555}_  


## Recon 200 \#3
Still use Nikto to scan the target. One of the output is ```+ Uncommon header 'x-humans' found, with contents: Check humans.txt```. The flag can be found in /human.txt  
The flag is: _flag{b580c96a22e1083f7bbca1620d211adaca0c2ea1c5f4b7f4a4ca097b81f170cf}_  


## Recon 200 \#4
Nothing special can be found by looking around the possible directory. So I then tried to check the source code of the page. Then I found the flag in the comment.  
The flag is: _flag{61ac1c5866aea5f9386e0d60a4b34a0e31c1c61a052ada8a58ee762b5b0cec69}_  


## Recon 200 \#5
This one is pretty straightforward.   
``` + Uncommon header 'x-flag' found, with contents: flag{878b5b269aa630760614093cfe943bf354a7969e000c32da13bdc9acdbe2f49c} ```   

