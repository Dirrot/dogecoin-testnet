Dogecoin Testnet
================

Informations, usage and code snippets of dogecoin -testnet mode for developers, who needs a stable playground for their applications.

**Note: If you develop some software around the Dogecoin, you should better use the implemented testnet to prevent loosing your real dogecoins.**

##### Table of Contents
* [What is the testnet?](#description)  
* [What do you need to use the testnet?](#usage)  
* [Ports, ports, ports](#ports) 
* [Getting some testdoge](#getting)   
  * [via mining](#mining)  
  * [via faucets](#faucets)
* [Block Explorer](#blockexplorer)
* [Well done!](#done)


<a name="description"/>
## What is the testnet?

The `Dogecoin testnet` is an alternative Dogecoin network with a separate blockchain. Since it uses a different blockchain, the testnet doesn't operate with the real dogecoin, but rather with what we call _testdoge_. These testdoge have `no monetary worth`. This allows developers to test their Dogecoin applications on the testnet `without risking to lose the real Dogecoin` or having to pay transactions fees.

<a name="usage"/>
## What do you need to use the testnet?

Well, this ist totally simple, if you have installed the `dogecoin wallet (dogecoin-qt/dogecoind)`. You can just add an arguement to the command via commandline. Like this:

```bash
dogecoin-qt -testnet 
or
dogecoind -testnet
```

Or you can set the specific settings through a setting file, called `dogecoin.conf`.

**dogecoin.conf setting file**
> You find the config file in your home directory.
> ```
> linux   -> ~/.dogecoin/dogecoin.conf
> windows -> ~/AppData/Roaming/DogeCoin/dogecoin.conf
> ```

For this guide we use the dogecoin.conf file for our settings. This is definitly the best way, instead of continously typing the hole commandline arguments into the console.

If this config file doesn't exists, we going to create it. And if it exists, just alter it.

Just add the following lines to the dogecoin.conf:
```bash
daemon = 1
server = 1
testnet = 1
rpcport = 44555
addnode = suchdig.com
addnode = testdoge.lionsserves.de
# we can totally add more nodes.
# if one node goes down. the testnet could be run with other nodes.
# just think about it, as a kind of failsafe node.
```

> If you like your node to be added here. Let me know.

<a name="ports"/>
## Ports, ports, ports

Let's talk about the ports! As you realized yourself, the testnet mode uses different ports. Here's an overview:

Ports/Description | Dogecoin-qt/dogecoind |Dogecoin Testnet      |
------|-----------------------|----------------------|
rpc   | 22555                 | 44555                |
p2p   | 22556                 | 44556                |


<a name="getting"/>
## Get some testdoge

So everything is now set up. And you should `get some testdoge`!

<a name="mining"/>
### via mining

You can try to mine it yourself with the implemented cpu miner in the dogecoin-qt/dogecoind.

**linux console style**
```bash
# now we tell dogecoind to enable the mining procedure and to use 1 core of the cpu.
./dogecoind setgenerate true 1
```

After a short time, you should disable it. Believe me, it is sufficient. For an hour mining i got about >500K testdoge.

```bash
# disable the mining procedure
./dogecoind setgenerate false
```

**windows style**

Just open the mining tab in the dogecoin-qt an set up the cpu miner.

**linux/windows style**

If you like to be system independent, you can also set this via the dogecoin.conf setting file.
Add to the dogecoin.conf:
```bash
# this enables the mining procedure
gen = 1
```

<a name="faucets"/>
### via faucets

And if you don't want to mine your testdoge, you can definitly check out some `faucets for the testdoge`. Here you can find a good one [`here`](testdoge.lionservers.de).

> If you like your testdoge-faucet to be added here. Let me know.

<a name="blockexplorer"/>
## Block Exploer (Testnet)

If you are interested in analyse the current blockchain, a `blockchain explorer` can be found [`here`](testdoge.lionservers.de/explorer).

<a name="done"/>
## Well done.

*That's it!*
You have successfully set up your own client for the Dogecoin testnet. This is a perfect part of your new development environment. You don't need to be scared of losing real doge during your test runs. Great work, everybody!

**If you still have any questions, feel free to visit the [`/r/dogecoindev`](http://www.reddit.com/r/dogecoindev) subreddit. Every questions about development and the testnet is an added value for the community.**


[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/Dirrot/dogecoin-testnet/trend.png)](https://bitdeli.com/free "Bitdeli Badge")

