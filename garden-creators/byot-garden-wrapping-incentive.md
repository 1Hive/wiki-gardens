# Governance Incentives

For pre-existing token Gardens, a farming contract is deployed during creation. Anyone can deposit the original token, that's available for distribution within the Garden, to this farming contract. This deposit can be claimed by users who have wrapped the pre-existing token Garden's original token to earn governance rights in the Garden.

The farming contract deployed is a [modified Unipool contract](https://github.com/1Hive/unipool/blob/master/contracts/Unipool.sol). Each time a reward is deposited it will be distributed to users proportional to the amount they have wrapped and the amount of time it remains wrapped within the following reward period of 30 days. The farming contract rewards users every second at the rate of `deposit amount / 30 days in seconds` this amount is then divided further for each user proportional to the amount of tokens they have wrapped relative to the total wrapped tokens at that time. 

To deposit a reward to the farming contract requires approving the deposit amount for the farming contract and calling the `notifyRewardAmount(uint256 _amount)` function with the reward amount. **Do not send tokens directly to this contract to create a reward as they will be lost forever.** This process is currently not integrated into the Gardens UI but you can use other methods to approve and call this function eg via Remix or Blockscout. You can only deposit the Gardens original token as a reward.

Find the address of the farming contract in the subgraph of your Garden:

* [Rinekby subgraph query](https://thegraph.com/legacy-explorer/subgraph/1hive/gardens-rinkeby?query=Farming%20Contract%20Address)
* [xDai subgraph query](https://thegraph.com/legacy-explorer/subgraph/1hive/gardens-xdai?query=Farming%20Contract%20Address)

