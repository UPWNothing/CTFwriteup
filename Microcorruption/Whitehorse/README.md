At first glance, it seems to be an overflow vulnerability. So I tried to overwrite the return address and make it retn to 0x451C. However, it appears that it just output the "Access granted" without unlocking the lock. 
Then I read the Lock Manual to find out how the embedded system unlock it. INT 0x7F is the interface with deadbolt to trigger an unlock. So we can simply smash the stack as before, and change the return address to 0x4532 (->INT()).Then the return address value for INT() is required before argument 0x7f. 
The key is 41414141414141414141414141414141324560447f
