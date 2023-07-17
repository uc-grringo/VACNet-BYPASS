# VACNet-BYPASS

We are trying to bypass current version of VAC anti-cheat with the lowest effort.
Bypass we are going to do is using external cheats creating an ESP possibly AIM assist as well.

# Known stuff we need to bypass

1. VAC enumprocesses & scan all openned handles (leading our external to be flag/banned)
2. VAC seems to check some memory section for unautorized changes
3. VAC scans for strings (example: client.dll, engine.dll, Valve001 and many more)

# Bypass 1.

1. Use kernel driver, this way you don't need to create handle to access memory (uc is full of usermode->driver ready to build solutions)
2. More complicated attack VAC at (steamservice.dll) and patch functions/check (this can get easilly detected)
3. Hijack process handle with needed permisions (As for now there is no known detection vector for this)

# Bypass 2.

1. Don't write to any memory regions or modify game's memory
   I've personally tested on multiple accounts and can confirm this memory changes will eventually get you banned:
   GLOW ESP, RADAR ESP, VIEW ANGLES, FORCEATTACK, FORCEJUMP
   Basically all well known features are going to flag(red trust) and eventually lead to game ban
2. Since we can't write to the game memory, you'd need overlay and make a regular esp
   As for now there are flags on creating overlay

# Bypass 3.

1. Decrypt all strings at runtime using XOR library for example
