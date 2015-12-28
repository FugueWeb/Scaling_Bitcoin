###########################
Finding a Balanced Solution
###########################

At the beginning of this post I detailed a relatively simple framework for finding a solution by describing what the problem is. There seems to me to be five main fundamental forces at play in finding a balanced solution; 'node distribution', 'mining decentralisation', 'network utility', 'time' and 'adoption'. The optimal solution needs to find a balance between all of these forces taking into account a buffer to offset our inability to predict the future with absolute accuracy.

To find a suitable buffer we need to assign a set of red line values which certain values should not pass if we want to make sure bitcoin continues to function as well as today (at a minimum). For example, percentage of orphans should stay below a certain value. These values can only be a best estimate due to the complexity of bitcoin economics, although I have tried to provide as sound reasoning as possible.

****************
Propagation time
****************

It seems a fair limit for this would be roughly what we have now. Bitcoin is still functioning now. Could mining be more decentralised? Yes, of course, but it seems bitcoin is working fine right now and therefore our currently propagation time for blocks is a fairly conservative limit to set. `Currently <https://tradeblock.com/blog/bitcoin-network-capacity-analysis-part-6-data-propagation>`_ 1MB blocks take around 15 seconds to propagate more than 50% of the network. 15 second propagation time is what I will be using as a limit in the solution to create a buffer.

***********
Orphan Rate
***********

This is obviously a value that is a function of propagation time so the same reasoning should be used. I will use a 3% limit on orphan rate in the solution to create a buffer.

****************************
Non-Pruned Node Storage Cost
****************************

For this I am choosing a limit of $200 in the near-term and $600 in the long-term. I have chosen these values based on what I think is a reasonable (maximum) for a business or enthusiast to pay to run a full node. As the number of transactions increases as more people use bitcoin the number of people willing to pay a higher price to run a node will also increase although the percentage of people will decrease. These are of course best guess values as there is no way of knowing exactly what percentage of users are willing to pay what.

************************
Pruned Node Storage Cost
************************

For this I am choosing a limit of $3 in the near-term (next 5 years) and $9 in the long-term (Next 25 years). I have chosen these values based on what I think is a reasonable (maximum) for normal bitcoin user to pay. In fact this cost will more likely be zero as almost all users have an amount of storage free on their computers.

***************************************
Percentage of Downstream Bandwidth Used
***************************************

This is a best guess at what I think people who run nodes would be willing to use to be connected to the bitcoin network directly. I believe using 10% (maximum) of a users downstream bandwidth is the limit of what is reasonable for a full node (pruned and non-pruned). Most users would continue to access the blockchain via SPV wallets though. Downstream is generally a much more valuable resource to a user than upstream due to the nature of the internet usage.

*************************************
Percentage of Upstream Bandwidth Used
*************************************

This is a best guess at what I think people who run nodes would be willing to use to be connected to the bitcoin network directly. I believe using 25% (maximum) of a users downstream bandwidth is the limit of what is reasonable for a full node (pruned and non-pruned). Most users would continue to access the blockchain via SPV wallets though. Upstream is generally a much less valuable resource to a user than downstream due to the nature of the internet usage.

****************************
Time to Bootstrap a New Node
****************************

My limit for this value is at 5 days using 50% of downstream bandwidth in the near-term and 30 days in the long-term. This seems like a reasonable number to me for someone who wants to start running a full node. Currently opening a new bank account takes at least week until everything is set up and you have received your cards, so it seems to me people would be willing to wait this long to become connected. Again, this is a best guess on what people would be willing to do to access the blockchain in the future. Most users requiring less security will be able to use an SPV wallet.

It is important to note that we only need enough nodes to make sure the blockchain is distributed across many places with many backups of the full blockchain. It is likely that a few thousand is a minimum for this. Increasing this amount to hundreds of thousands or millions of full nodes is not necessarily that much of an advantage to node distribution but could be a significant disadvantage to mining centralisation. This is because the more nodes you have in the network, the longer it takes to propagate >50% of it.

************
Storage cost
************

`Storage cost <http://hblok.net/blog/posts/2014/07/13/historical-cost-of-computer-memory-and-storage-2/>`_ follows a linear logarithmic trend. Costs of HDD reducing by 10 times every 5 years, although this has slowed over the past few years. This can be attributed to the flooding in South East Asia and the transition to SSD technology. SSD technology also follows the linear logarithmic trend of costs reducing 10 times every 5 years, or roughly decreasing 37% per year.

*********************************************************
Average Upload and Download Bandwidth Increases Over Time
*********************************************************

`Average upload and download bandwidth <http://digitalchina.blogg.lu.se/why-so-fast-upload-speeds-in-eastern-europe-and-central-asia/>`_ increases in a linear logarithmic trend. Both upload and download bandwidth follow the same trend of doubling roughly every two years, or increasing 40% per year.

************************************************************************
What should be the acceptable limit? What would be the growth over time?
************************************************************************

* `Github Issue 1 <https://github.com/FugueWeb/Scaling_Bitcoin/issues/1>`_

I propose 200GB and 20% annually for pruned nodes. iirc comcast caps at 300GB, so 200GB seems like a good upper limit. In my country it hasn't increased 20% annually, but consumer demand for lots of data-usage is increasing a lot, so I think we can be optimistic.

For full nodes it should be a limit where limit+ 'more than average usage' will start to raise red flags with providers. If I had to pick a number I'd pick 1TB +20% annually, but I don't have any data to back that up.

To estimate the total bandwidth usage after IBLT and for pruned nodes (as they don't serve historical blocks) it would be great to have some data on transaction relaying and block relaying separately, so if anyone has some data on this that would be great.

*****
Price
*****

I was hesitant to include this one here but I feel it is unavoidable. Contrary to what people say (often when the price is trending downwards) bitcoin price is an extremely important metric in the long-term. Depending on bitcoin's price, bitcoin's is useful to; enthusiasts->some users->small companies->large companies->nations->the world, in roughly that order. The higher bitcoin's price is the more liquid the market will be and the more difficult it will be to move the price, therefore increasing bitcoin's utility. Bitcoin's price in the long-term is linked to adoption, which seems to happen in waves, as can be seen in the price bubbles over the years. If we are planning/aiming for bitcoin to at least become a currency with equal value to one of the worlds major currencies then we need to plan for a market cap and price that reflect that. I personally think there are two useful targets we should use to reflect our aims. The first, lower target is for bitcoin to have a `market cap <https://blockchain.info/charts/market-cap?timespan=all&showDataPoints=false&daysAverageString=1&show_header=true&scale=0&address=>`_ the size of a major national currency. This would put the market cap at around 2.1 trillion dollars or $100,000 per bitcoin. The second higher target is for bitcoin to become the world's major reserve currency. This would give bitcoin a market cap of around 21 trillion dollars and a value of $1,000,000 per bitcoin. A final, and much more difficult target is likely to be bitcoin as the only currency across the world, but I am not sure exactly how this could work so for now I don't think this is worth considering.

As price increases, so does the subsidy reward given out to miners who find blocks. This reward is semi-dynamic in that it remains static (in btc terms) until 210,000 blocks are found and then the subsidy is then cut in half. This continues to happen until all 21,000,000 bitcoins have been mined. If the value of each bitcoin increases faster than the btc denominated subsidy decreases then the USD denominated reward will be averagely increasing. Historically the bitcoin price has increased significantly faster than subsidy decreases. The btc denominated subsidy halves roughly every 4 years but the price of bitcoin has historically increased roughly 50 fold in the same time.

Bitcoin adoption should happen in a roughly `s curve dynamic <http://imgur.com/6A3wunT>`_ like every other technology adoption. This means exponential adoption until the market saturation starts and adoption slows, then the finally is the market becomes fully saturated and adoption slowly stops (i.e. bitcoin is fully adopted). If we assume the top of this adoption s-curve has one of the market caps above (i.e. bitcoin is successful) then we can use this assumption to see how we can transition from a subsidy paid network to a transaction fee paid network.

********
Adoption
********

`Adoption <https://www.google.com/trends/explore#q=bitcoin>`_ is the most difficult metric to determine. In fact it is impossible to determine accurately now, let alone in the future. It is also the one of the most important factors. There is no point in building software that no one is going to use after all. Equally, there is no point in achieving a large amount of adoption if bitcoin offers none of the original value propositions. Clearly there is a balance to be had. Some amount of bitcoin's original value proposition is worth losing in favour of adoption, and some amount of adoption is worth losing to keep bitcoin's original value proposition. A suitable solution should find a good balance between the two. It is clear though that any solution must have increased adoption as a basic requirement, otherwise it is not a solution at all.

One major factor related to adoption that I rarely see mentioned, is stability and predictability. This is relevant to both end users and businesses. End users rely on stability and predictability so that they do not have to constantly check if something has changed. When a person goes to get money from a cash machine or spend money in a shop, their experience is almost identical every single time. It is highly dependable. They don't need to keep up-to-date on how cash machines or shops work to make sure they are not defrauded. They know exactly what is going to happen without having to expend any effort. The more deviation from the standard experience a user experiences and the more often a user experiences a deviation, the less likely a user is going to want to continue to use that service. Users require predictability extending into the past. Businesses who's bottom line is often dependent on reliable services also require stability and predictability. Businesses require predictability that extends into the future so that they can plan. `A business <https://np.reddit.com/r/Bitcoin/comments/3kytd0/>`_ is less likely to use a service for which they do not know they can depend on in the future (or they know they cannot depend on).

For bitcoin to achieve mass adoption it needs a long-term predictable and stable plan for people to rely on.