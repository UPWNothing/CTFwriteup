###HackThisSite/Realistic/7

There are three links named as "Patiotism", "Long Live Bush" and "Nuke the bastards!" on the main page. If you click the link, you will find that it is redirected to showimages.php. The txt file is called in this page by ```showimages.php?file=bush.txt```.

Click one of those pictures, we realize all the images are located in the /images directory. When trying to enter this directory, I am happy to find this directory is not blocked. There are several .jpg files and /admin in the directory. The /admin require authenticated to log in. There must be some clues in the web application. 

Then go back to showimages.php. Try to replace the value of 'file' parameter with images/.htaccess. Nope! Then try images/admin/.htaccess. Got it! Four images cannot be displayed. Check the source code. The AuthUserFile is lying under ```/www/hatkthissite.org/www/missions/realistic/7/images/admin/.htpasswd```. Have another try to open the .htpasswd file through showimages.php. 

Then we get the username and encrypted password pair:

```
administrator:$1$AAODv...$gXPqGkIO3Cu6dnclE/sok1
```

Use John the Pipper to crack it!
```
echo "administrator:$1$AAODv...$gXPqGkIO3Cu6dnclE/sok1" >> passwd
john passwd
john --show passwd
```

The password for _administrator_ is _shadow_.
Log in to /images/admin to finish this challenge.
