# drain.py
remote p2p bandwidth/cpu overage attack against bitcoin, dogecoin, etc.

github issue https://github.com/dogecoin/dogecoin/issues/3243

we can force dogecoin/bitcoin/etc. nodes to upload unlimited data to an attacking machine - which caps out, throttles and in many cases charges overuse fees on upstream - making this a financial attack against bitcoin and its forks. certain protocol messages aren't rate limited by "feefilter" or other mechanisms and can be used to remotely overwhelm nodes.

# asciinema
[![asciicast](https://asciinema.org/a/577193.svg)](https://asciinema.org/a/577193)
