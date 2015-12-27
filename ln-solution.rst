#####################
The Lightning Network
#####################

*********************************************
Proposed Solutions by Some Bitcoin Developers
*********************************************

The `Lightning Network <https://lightning.network/lightning-network-paper.pdf>`_ (LN) is an attempt at scaling the number of transactions that can happen between parties by not publishing any transaction onto the blockchain unless it is absolutely necessary. This is achieved by having people pool bitcoin together in a "Channel" and then these people can transact instantly within that channel. If any shenanigans happen between any of the parties, the channel can be closed and the transactions will be settled on the blockchain. The second part of their plan is limit the block size to turn bitcoin into a settlement network. The original block size limit of 1MB was originally put in place by Satoshi as an `anti DOS measure <https://bitcointalk.org/index.php?topic=946236.msg10388435#msg10388435>`_. It was to make sure a bad actor could not propagate a very large block that would crash nodes and increase the size of the blockchain unnecessarily. Certain developers now want to use this 1MB limit in a different way to make sure that resource requirements will stay low, block space always remains full, fees increase significantly and people use the lightning network as their main way of transacting rather than the blockchain. They also say that keeping the resource requirements very low will make sure that bitcoin remains decentralised.

***********************************
Problems with the Lightning Network
***********************************

The LN works relatively well (in theory) when the cost and time to publish a set of transactions to the network are kept low. Unfortunately, when the cost and time to publish a set of transactions on the blockchain become high, the LN's utility is diminished. The trust you get from a transaction on the LN comes only from the trustless nature of having transactions published to the bitcoin network. What this means is that if a transaction cannot be published on the bitcoin network then the LN transaction is not secured at all. As transactions fees rise on the bitcoin blockchain the LN utility is diminished. Lets take an example:

* Cost of publishing a transaction to the bitcoin network = $20
* LN transaction between Bob and Alice = $20.
* Transaction between Bob and Alice has problem therefore we want to publish it to the blockchain.
* Amount of funds left after transaction is published to the blockchain = $20 - $20 = $0.

This is also not a binary situation. If for example in this scenario, the cost to publish the transaction to blockchain was $10 then still only 50% of the transaction would be secure. It is unlikely anyone really call this a secure transaction.

Will a user make a non-secured/poorly secured transaction on the LN when they could make the same transaction via an altcoin or non-cryptocurrency transaction and have it well secured? It's unlikely. What is much more likely to happen is that transaction that are not secured by bitcoin because of the cost to publish to the blockchain will simply overflow into altcoins or will simply not happen on any cryptocurrency network. The reality is though, that we don't know exactly what will happen because there is no precedent for it.

Another problem outside of security is convenience. With a highly oversaturated block space (very large backlog of transactions) it could take months to have a transaction published to the blockchain. During this time your funds will simply be stuck. If you want to buy a coffee with a shop you don't have a channel open with, instead of simply paying with bitcoin directly, you would have to wait months to open a channel by publishing a transaction to the bitcoin blockchain. I think your coffee might be a little cold by then (and mouldy).

I suggest reading this excellent post `HERE <https://chrispacia.wordpress.com/2015/12/23/lightning-network-skepticism/>`_ for other rather significant problems with the LN when people are forced to use it.

The LN is currently not complete and due to its high complexity it will take some time to have industry wide implementation. If it is implemented on top of a bitcoin-as-a-settlement-network economy it will likely have very little utility.

*****************************
Uses of the Lightning Network
*****************************

The LN is actually an extremely useful layer-2 technology when it is used with it's strengths. When the bitcoin blockchain is fast and cheap to transact on, the LN is also extremely useful. One of the major uses for the LN is for trust-based transactions. If you are transacting often between a set of parties you can truly trust then using LN makes absolute sense since the trustless model of bitcoin is not necessary. Then once you require your funds to be unlocked again it will only take a short time and small cost to open them up to the full bitcoin network again. Another excellent use of LN would be for layer-3 apps. For example a casino app: Anyone can by into the casino channel and play using real bitcoins instantly in the knowledge that is anything nefarious happens you can instantly settle and unlock your funds. Another example would be a computer game where you can use real bitcoin in game, the only difference is that you connect to the game's LN channel and can transact instantly and cheaply. Then whenever you want to unlock your funds you can settle on the blockchain and use your bitcoins normally again.

LN is hugely more powerful, the more powerful bitcoin is. The people making the LN need to stick with its strengths rather than sell it as an all-in-one solution to bitcoin's scaling problem. It is just one piece of the puzzle.