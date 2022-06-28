# discord-bruteforce-rust
Brute force discord tokens.
C version - https://github.com/wantyapps/discord_bruteforce
## IMPORTANT
Proof of concept. Please don't actually brute-force a token
## Efficiency
With a supercomputer able to calculate 60 quintillion hashes a second, it would take you about 2.93e+59 centuries to get the has in the worst case scenario. Since these tokens need to be checked against the Discord API, you would have to multithread these calculations, perhaps across multiple machines, since validation can take 0.1-0.2 seconds, depending on the internet speed/latency.
TLDR - It's wildly inefficient.
## How it works
Refer to this diagram:
