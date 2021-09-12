# Price Oracle

Each Garden deployment includes the deployment of a [Price Oracle contract](https://github.com/1Hive/uniswap-v2-periphery/blob/master/contracts/examples/IncentivisedSlidingWindowOracle.sol).

This contract, when called consistently, returns the average DAI value for the Garden token over the previous 24 hours.

It is referenced when:

1. Calculating the value of proposal payouts that are defined in DAI as opposed to the payout token
2. When adjusting the deposit required to create and challenge actions \(decisions and proposals\) via the `collateralRequirementUpdater` contract.

It requires the `update()` function be called once every 3 hours to get and store the current price data at that time. If this requirement is satisfied, then the `consult()` function can be called to get the average DAI price of the Garden token over the previous 24 hours. If an update call is missed during a 24 hour period, consulting it will revert until it has been called consistently for another 24 hour period.

In order to ensure the price oracle is called consistently there is a [centralised service](https://github.com/1Hive/price-oracle-service) \(on the xDai network\) that can be given some xDai and left to run.

1Hive runs this service to call the Honey price oracle but does not intend to run it for every Garden that is deployed. Individual Gardens will have to decide how to manage this if they wish to use the functionality relying on it. 

The price oracle update function is incentivised: it pays out 2% of the contract's balance of the Gardens token \(if it holds any\) to each successful caller of the `update()` function. 

In the future the Gardens UI will include a button prompting users to update the price oracle once every 3 hours - we expect that in most cases this should be enough to keep the oracle up to date without the centralised service.

You can dind the address of the price oracle contract in the subgraph of your Garden:

* [Rinkeby subgraph query](https://thegraph.com/legacy-explorer/subgraph/1hive/gardens-rinkeby?query=Price%20Oracle%20Address)
* [xDai subgraph query](https://thegraph.com/legacy-explorer/subgraph/1hive/gardens-xdai?query=Price%20Oracle%20Address)

