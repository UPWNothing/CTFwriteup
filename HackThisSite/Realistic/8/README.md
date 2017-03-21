###HackThisSite/Realistic/8

This website contains user register/login functions. I tried to login with admin:admin, and luckily it works. The password seems store as md5 hash. There's not much else we can do with the admin account. 

Then I noticed User Info. If a existed username is submited, a username:name pair will be returned. This page to be SQL injectable.Coz if a tick(') is submited, then the error message will be returned. At mean time, I get the table name "users". Start with the most basic SQL injection: ```' or 1=1 -- ```. Then I can see the information of all the users. Search "gary hunter" in this page, and I got his username: hunter. 

Again, I tried to login with hunter:hunter. It works AGAIN! But I then realized this is not the account I'm looking for. Someone else registered hunter and entered this stupid description. So I turned back and found "GaryWilliamHunter", which should be the REAL hunter. Then I registered a new account and logged in. I checked everything carefully. The cookie is attackable. I changed the value of "accountUsername" in the cookie to "GaryWilliamHunter". After that I tried to do the money transfer to dropCash
