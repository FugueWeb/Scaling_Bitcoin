############################
Improving Network Efficiency
############################

The more efficient the network, the more we can do with what we already have. There are a number of possible efficiency improvements to the network and each of them has a slightly different effect.

*******
Pruning
*******

`Pruning <https://bitcoin.org/en/release/v0.11.0>`_ allows the stored blockchain size to be reduced significantly by not storing old data. This has the effect of lowering the resource requirements of running a node. a 40GB unpruned blockchain would be reduced in size to 550MB. (It is important to note that a pruned node has lower utility to the network)

***********
Thin Blocks
***********

`Thin blocks <https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2015-September/011157.html>`_ uses the fact that most of the nodes in the network already have a list of almost all the same transactions ready to be put into the blockchain before a block is found. If all nodes use the same/similar policy for which transactions to include in a block then you only need to broadcast a small amount of information across the network for all nodes to know which transactions have been included (as opposed to broadcasting a list of all transactions included in the block). Thin Blocks have the advantage of reducing propagation which lowers the mining centralisation pressure due to orphaned blocks.

************
libsecp256k1
************

`libsecp256k1 <https://github.com/bitcoin/bitcoin/pull/6954>`_ allows a more efficient way of validating transactions. This means that propagation time is reduced which lowers the mining centralisation pressure due to orphaned blocks. It also means reduced time to bootstrap the blockchain for a new node.

********************
Serialised Broadcast
********************

Currently block transmission to peers happens in parallel to all connected peers. Obviously for block propagation this is a poor choice in comparison to serial transmission to each peer one by one. Using parallel transmission means that the more peers you have, the slower the propagation, whereas serial transmission does not suffer this problem. The problem that serial transmission does suffer from though is variance. If the order that you send blocks to peers in is random, then it means sometimes you will send blocks to a peer who has a slow/fast connection and/or is able to validate slowly/quickly. This would mean the average propagation time would increase with serialised transmission but depending on your luck you would sometimes have faster propagation and sometimes have slower propagation. As this will lower propagation time it will also lower the mining centralisation pressure due to orphaned blocks. (This is just a concept at the moment but I don't see why it couldn't be implemented).

****************************
Serialised Broadcast Sorting
****************************

This is a fix for the variance that would occur due to serialised broadcast. This sorts the order that you broadcast a block to each peer into; fastest upload + validation speed first and slowest upload speed and validation speed last. This not only decreases the variance to zero but also allows blocks to propagation to happen much faster. This also has the effect of lowering the mining centralisation pressure due to orphaned blocks. (This is just a concept at the moment but I don't see why it couldn't be implemented).

Here is a table below that shows roughly what the effects these solutions should have.

==================== ========= ============== =============== ============= =============
Name                 Bandwidth Broadcast Time Validation Time New Node Time Storage Space
==================== ========= ============== =============== ============= =============
Pruning	             1         1	          1               1             0.014
Thin Blocks          0.42	   0.1	          0.1	          1	            1
libsecp256k1         1	       1              0.2	          0.6	        1
Serialised Broadcast 1	       0.5	          1	              1         	1
KYN                  1	       0.75	          1           	  1         	1
Segregated Witness   1	       1	          1               0.4       	1
TOTAL                0.42      0.0375         0.02	          0.24          0.014
Multiplier           2.38	   26.7	          50	          -	            70
==================== ========= ============== =============== ============= =============



