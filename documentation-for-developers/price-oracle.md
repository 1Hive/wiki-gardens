# Price Oracle

Each Garden deployment includes the deployment of a [Price Oracle contract](https://github.com/1Hive/uniswap-v2-periphery/blob/master/contracts/examples/IncentivisedSlidingWindowOracle.sol) which, when called consistently, will return the average DAI value for the Garden token over the previous 24 hours. This contract is referenced when calculating the value of proposal payouts that are defined in DAI as opposed to the payout token. This contract is also referenced when adjusting the deposit required to create and challenge actions \(decisions and proposals\) via the `collateralRequirementUpdater` contract.

It requires the `update()` function be called once every 3 hours to get and store the current price data at that time. Once it has been called once every 3 hours for 24 hours, the `consult()` function can be called to get the average DAI price of the Garden token over the previous 24 hours. If an update call is missed during a 24 hour period, consulting it will revert until it has been called consistently for another 24 hour period.

In order to ensure the price oracle is called consistently there is a [centralised service](https://github.com/1Hive/price-oracle-service) that can be given some xDai and left to run. 1Hive runs this service to call the Honey price oracle but does not intend on running it for every Garden that is deployed, so individual Garden's communities will have to decide how to manage this if they wish to use the functionality relying on it. 

The price oracle update function is incentivised, it will pay out 2% of the contract's balance of the Gardens token \(if it holds any\) to each successful caller of the `update()` function. In the future the Gardens UI will include a button prompting users to update the price oracle once every 3 hours and hopefully for popular enough Gardens this incentive and easy access should be enough to keep it up to date without the centralised service.

Find the address of the price oracle contract in the subgraph of your Garden:

* [Rinkeby subgraph query](https://thegraph.com/legacy-explorer/subgraph/1hive/gardens-rinkeby?query=Price%20Oracle%20Address)
* [xDai subgraph query](https://thegraph.com/legacy-explorer/subgraph/1hive/gardens-xdai?query=Price%20Oracle%20Address)

