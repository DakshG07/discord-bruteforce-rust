# discord-bruteforce-rust
Brute force discord tokens.
C version - https://github.com/wantyapps/discord_bruteforce
## IMPORTANT
Proof of concept. Please don't actually brute-force a token
## Efficiency
With a supercomputer able to calculate 60 quintillion hashes a second, it would take you about 2.13e+62 centuries to get the has in the worst case scenario. Since these tokens need to be checked against the Discord API, you would have to multithread these calculations, perhaps across multiple machines, since validation can take 0.1-0.2 seconds, depending on the internet speed/latency.

TLDR - It's wildly inefficient, but still more effective(in theory) than guessing emails and passwords(with infinite combinations).


*Check out [this](https://www.desmos.com/calculator/n0hk8jqnup) desmos to play around with some results. The graph is rather uninteresting, but it should give you a sense of the scale of this.*

## How it works
Refer to this diagram:
![Diagram](https://user-images.githubusercontent.com/34555296/120932740-4ca47480-c6f7-11eb-9270-6fb3fbbd856c.png)
*Diagram by Flam3rboy, taken from [this](https://github.com/hxr404/Discord-Console-hacks) repository.*
The user ID of the person you wish to attack is converted to Base64, then we append the current unix time in Base64. We then generate a random hash of 27 characters which is appended to the token. We then attempt to send a message through a POST request, and if the result returns `200`, we have successfully brute forced the token!
### Credit
Credit to [wantyapps](https://github.com/wantyapps/) for the C version.
Credit to [Dukk](https://github.com/DakshG07) for the idea and Rust version.
