# bitdrain
remote p2p bandwidth/cpu overage financial attack against bitcoin, dogecoin, etc.

github issue https://github.com/dogecoin/dogecoin/issues/3243

by using `drain-doge.py`, `drain-btc.py` and `drain-ltc.py` we can force dogecoin/bitcoin/litecoin/fork nodes to upload unlimited data to an attacking machine - which caps out, throttles and in many cases charges overuse fees on upstream - making this a financial attack against bitcoin and its forks. certain protocol messages aren't rate limited and can be used to remotely overwhelm a server's upstream in a financially damaging way.

# asciinema
[![asciicast](https://asciinema.org/a/577193.svg)](https://asciinema.org/a/577193)

# dogecoin issue report

there is a remote attack that can be carried out in perpetuity against vulnerable nodes in a way that a single attacking machine can force `dogecoind` to upload > 130MB/s to the attacking machine in a sustained way.

doge nodes on isps or cloud providers that charge for or throttle upstream after a cap has been reached are, unless hardened against this attack at a server level, vulnerable to the attack.

i did some testing and ran my digitalocean bandwidth costs to > $175 relatively quickly.

![image](https://user-images.githubusercontent.com/38997186/229753562-079d844f-8b82-4d23-9fd8-56fc6bcca3d7.png)

making this a financial attack against vulnerable nodes - but not an attack capable of taking the network offline.

the attack is carried out by an [evil multithreaded script](https://github.com/visualbasic6/drain) that pretends to be several valid nodes. this is accomplished by operating in the network at a low p2p protocol level. after performing a complete handshake with the target node, resulting in a healthy peer connection, the script begins to request protocol message content in a loop. at this point a single attacking machine can trigger, again, `dogecoind` into sending > 130MB/s worth of data. additionally - with code alterations it is likely that the evil script could target multiple dogecoin nodes simultaneously, from one machine, assuming that certain conditions are met on the attacker's end.

i can't find a bug bounty program so i'm just posting it here. it's not really the exploit of the century so i'm not concerned with evil actors carrying out bandwidth attacks against their enemies. that said - still - [get that fixed](https://youtube.com/watch?v=BU3tDES29sY&t=143s).

bitcoin and litecoin are also vulnerable to the attack.

but blockstream (skids) and their approved programmers (skids) are ants at a picnic when it comes to irresponsible public disclosure. i'd like to think that, at least here in the doge community, we like to have a bit of fun and [do a little trolling](https://youtu.be/PobQzVsj7GE?t=4).

thank you for your immediate attention to this matter.

[pad](https://twitter.com/123456)
