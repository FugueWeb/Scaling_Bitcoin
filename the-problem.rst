###########
The Problem
###########

There seems to me to be five main fundamental forces at play in finding a balanced solution;

* node distribution
* mining decentralisation
* network utility
* time
* adoption


*****************
Node Distribution
*****************

Bandwidth has a relationship to node count and therefore `node distribution <https://bitnodes.21.co/>`_. This is because if bandwidth becomes too high then fewer people will be able to run a node. To a lesser extent bandwidth also effects 'mining decentralisation' as miners/pool owners also need to be able to run a node. I would argue that the centralisation pressures in relation to bandwidth are negligible though in comparison to the centralisation pressure caused by the usefulness of larger pools in reducing variance. The cost of a faster internet connection is negligible in comparison to the turnover of the pools. It is important to note the distinction between bandwidth required to propagate blocks quickly and the bandwidth required to propagate transactions. The bandwidth required to simply propagate transactions is still low today.

New node time (i.e. the time it takes to start up a new node) also has a relationship with node distribution. i.e. If it takes too long to start a new node then fewer people will be willing to take the time and resources to start a new node.

Storage Space also has a relationship with node distribution. If the blockchain takes up too much space on a computer then less people will be willing to store the whole blockchain.
Any suitable solution should look to not decrease node distribution significantly.

***********************
Mining Decentralisation
***********************

Broadcast time (the time it takes to upload a block to a peer) has a relationship with `mining centralisation <https://blockchain.info/pools>`_ pressures. This is because increasing broadcast time increases the propagation time, which increases the orphan rate. If the orphan rate it too high then individual miners will tend towards larger pools.

Validation time (the time it to validate a block) has a relationship with mining centralisation pressures. This is because increasing validation time increases the propagation time, which increases the orphan rate. If the orphan rate it too high then individual miners will tend towards larger pools.

Any suitable solution should look to not increase mining centralisation significantly.

***************
Network Utility
***************

Network Utility is one that I find is often overlooked, is not well understood but is equally as important. The network utility force acts as a kind of disclaimer to the other two forces. It has a balancing effect. Increasing the network utility will likely increase user adoption (The more useful something is, the more people will want to use it) and therefore decreasing network utility will likely decrease user adoption. User adoption has a relationship with node count. i.e. the more people, companies and organisations know about and use bitcoin, the more people, companies and organisations that will run nodes. For example we could reduce block size down to 10KB, which would reduce broadcast time and validation time significantly. This would also therefore reduce mining centralisation pressures significantly. What is very important to realise though is that network utility would also be significantly be reduced (fewer people able to use bitcoin) and therefore so would node distribution. Conversely, if we increased the block size (not the limit) right now to 10GB, the network utility would be very high as bitcoin would be able to process a large number of transactions but node distribution would be low and mining centralisation pressures would be high due to the larger resource requirements.

Any suitable solution should look to increase network utility as time increases.

****
Time
****

Time is an important force because of how technology improves over time. Technology improves over time in a semi-predicable fashion (often exponential). As we move through time, the cost of resources required to run the bitcoin network (if the resource requirements remained static) will decrease. This means that we are able to increase resource requirements proportional to technological improvements/cost reductions without any increase in costs to the network. Technological improvements are not perfectly predictable though so it could be advantageous to allow some buffer room for when technological improvements do not keep up with predictions. This buffer should not be applied at the expense of the balance between the other forces though (i.e. make the buffer too big and network utility will be significantly decreased).

********
Adoption
********

Increasing adoption means more people using the bitcoin/blockchain network. The more people use bitcoin the more utility it has, and the more utility Bitcoin has the more people will want to use it (network effect). The more people use bitcoin, the more people there that have an incentive to protect bitcoin.

Any suitable solution should look to increase adoption as time increases.