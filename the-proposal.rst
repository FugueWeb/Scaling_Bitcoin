########
Proposal
########

This proposal is one based on determining a best fit balance of every factor and a large enough buffer to allows for our inability to perfectly predict the future. No one can predict the future with absolutely certainty but it does not mean we cannot make educated guesses and plan for it.

The first part of the proposal is to spend 2016 implementing all available efficiency improvements (i.e the ones detailed above) and making sure the move to a scaled bitcoin happens as smoothly as possible. It seems we should set a target of implementing all of the above improvements within the first 6 months of 2016. These improvements should be implemented in the first hardfork of its kind, with full community wide consensus. A hardfork with this much consensus is the perfect time to test and learn from the hardforking mechanism. Thanks to Seg Wit, this would give us an effective 2 fold capacity increase and set us on our path to scalability.

The second part of the proposal is to target the release of a second hardfork to happen at the end of 2016. Inline with all the above factors this would start with a real block size limit increase to 2MB (effectively increasing the throughput to 4x compared to today thanks to Seg Wit) and a `doubling of the block size limit every two years thereafter <http://imgur.com/LvJ0VTP>`_ (with linear scaling in between). The scaling would end with an 8GB block size limit in the year 2039.

*******************************************
How does the Proposal fit inside the Limits
*******************************************

TODO: add source links
`See original Reddit post <https://www.reddit.com/r/Bitcoin/comments/3ybaqj/an_attempt_at_a_fully_comprehensive_look_at_how/>`_

****************
Propagation time
****************

If trends for average upload and bandwidth continue then propagation time for a block to reach >50% of the nodes in the network should never go above 1s. This is significantly quickly than propagation times we currently see.

In a worst case scenario we can we wrong in the negative direction (i.e. bandwidth does not increase as quickly as predicted) by 15% absolute and 37.5% relative (i.e. bandwidth improves at a rate of 25% per year rather than the predicted 40%) and we would still only ever see propagation times similar to today and it would take 20 years before this would happen.

***********
Orphan Rate
***********

Using our best guess predictions the orphan rate would never go over 0.2%.

In a worst case scenario where we are wrong in our bandwidth prediction in the negative direction by 37.5% relative, orphan rate would never go above 2.3% and it would take over 20 years to happen.

****************************
Non-Pruned Node Storage Cost
****************************

Using our best guess predictions the cost of storage for a non-pruned full node would never exceed $40 with blocks consistently 50% full and would in fact decrease significantly after reaching the peak cost. If blocks were consistently 100% full (which is highly unlikely) then the maximum cost of an un-pruned full node would never exceed $90.

In a worst case scenario where we are wrong in our bandwidth prediction in the negative direction by 37.5% relative and we are wrong in our storage cost prediction by 20% relative (storage cost decreases in cost by 25% per year instead of the predicted 37% per year), we would see a max cost to run a node with 50% full blocks of $100 by 2022 and $300 by 2039. If blocks are always 100% full then this max cost rises to $230 by 2022 and $650 in 2039. It is important to note that for storage costs to be as high as this, bitcoin will have to be enormously successful, meaning many many more people will be incentivised to run a full node (businesses etc.)

************************
Pruned Node Storage Cost
************************

Using our best guess predictions the cost of storage for a pruned full node would never exceed $0.60 with blocks consistently 50% full. If blocks were consistently 100% full (which is highly unlikely) then the max cost of an un-pruned full node would never exceed $1.30.

In a worst case scenario where we are wrong in our bandwidth prediction in the negative direction by 37.5% relative and we are wrong in our storage cost prediction by 20% relative (storage cost decreases in cost by 25% per year instead of the predicted 37% per year), we would see a max cost to run a node with 50% full blocks of $1.40 by 2022 and $5 by 2039. If blocks are always 100% full then this max cost rises to $3.20 by 2022 and $10 in 2039. It is important to note that at this amount of storage the cost would be effectively zero since users almost always have a large amount of free storage space on computers they already own.

***************************************
Percentage of Downstream Bandwidth Used
***************************************

Using our best guess predictions running a full node will never use more than 0.3% of a users download bandwidth (on average).

In a worst case scenario we can we wrong in the negative direction by 37.5% relative in our bandwidth predictions and we would still only ever see a max download bandwidth use of 4% (average).

*************************************
Percentage of Upstream Bandwidth Used
*************************************

Using our best guess predictions running a full node will never use more than 1.6% of a users download bandwidth (on average).

In a worst case scenario we can we wrong in the negative direction by 37.5% relative in our bandwidth predictions and we would only ever see a max download bandwidth use of 24% (average) and this would take over 20 years to occur.

****************************
Time to Bootstrap a New Node
****************************

Using our best guess predictions bootstrapping a new node onto the network should never take more than just over a day using 50% bandwidth.

In a worst case scenario we can we wrong in the negative direction by 37.5% relative in our bandwidth predictions and it would take one and 1/4 days to bootstrap the blockchain using 50% of the download bandwidth. By 2039 it would take 16 days to bootstrap the entire blockchain when using 50% bandwidth. I think it is important to note that by this point it is very possible the bootstrapping the blockchain could very well be done by simply buying an SSD with blockchain already bootstrapped. 16 days would be a lot of time to download software but it does not necessarily mean a decrease in centralisation. As you will see in the next section, if bitcoin has reached this level of adoption, there may well be many parties will to spend 16 days downloading the blockchain.

**************************************************
What if Things Turn Out Worse than the Worse Case?
**************************************************

While it is likely that future trends in the technology required to scale bitcoin will continue relatively similar to the past, it is possible that the predictions are completely and utterly wrong. This plan takes this into account though by making sure the buffer is large enough to give us time to adjust our course. Even if no technological/cost improvements (near zero likelihood) are made to bandwidth and storage in the future this proposal still gives us years to adjust course.