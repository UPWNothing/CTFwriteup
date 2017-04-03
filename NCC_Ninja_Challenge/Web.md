# Web

## Web 200 \#1
  In this challenge, we have to bypass the authentication. I thought that there could be SQLi vulnerability. However, when I tried to test the SQLi vuln, I found the submit button didn't work at all. So I examined the source code. I found "Admin Only :: REDACTED" in the comment.  
  Then I turned to cookie to see if it is possbile to bypass the authentication by editing the cookie value. The value of "role" is "YWRtaW4=\0001". Apparently it is base64 encoded. I decoded it and found it is guest. So I encode "admin" and move it into role's value. Now, we are logged in as admin.   
  The flag is:  
  _flag{019ac4c09d48a483e641bb98cfe0ff2bd6e47fd4edb841334c158517e4ab916c}"_


## Web 200 \#2
  There's nothing special on the page. I checked the source code and found nothing. So I use Nikto to scan this host. And then I got an output like  
```+ OSVDB-3092: /c049ff71114f91c/secret/: This might be interesting...```  
  The flag.txt is in this directory.   
  The flag is : _flag{08caf2845ee82898a7db8e41872b0d087c5649d79d2baade47c8a07e2c3af884}_


## Web 300 \#1
  I tried to input ```[' or 1=1 --]``` to see if there's sql injection. I then got the whole table. Thus, this is an SQLI challenge. To get the admin's password, we need to use Union Injection.   
  The SQL error is not well hidden. It makes everything easier.   
  I use order by to get the column number: ```SQL Error: 1st ORDER BY term out of range - should be between 1 and 3```    
  I guess that the tablename may be "users". It is!  
  I got the hashed password using input ```John' union select username,password,3 from users-- ```  
  Now we get the username:password pair "administrator	c378985d629e99a4e86213db0cd5e70d". Crack the MD5 hash value. (Or just Google it). The password is "chocalate".  

  Login with what you got. The flag is: _flag{962c373035e19f2c6c0fb797e57e65328c77df3f137f8a337f63228b719c386d}_



