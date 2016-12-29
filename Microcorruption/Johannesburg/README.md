#Johannesburg

In this challenge, a stack canary is used to protect againt stack overflow. However, unlike other canaries, which have random values, the canary in this chanllenge has a hard coded value, which is shown below. 

4578:  f190 d000 1100 cmp.b	#0xd0, 0x11(sp)

So we need to make the 18th byte to be d0, and add a return address after that. The canary can be bypass then.  

The key is 41414141414141414141414141414141410d6645
