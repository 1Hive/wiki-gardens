

# Types of Gardens

Each Garden has a Common Pool which will hold DAO funds that can be requested by proposals made on a Gardens. Your community can choose how to contribute funds to this pool.

Every Garden also needs a Token, it will quantify each member's ability to propose and influence decisions that are made in your DAO. Using this metric, Gardens can be separated into two categories: **Native Token Gardens** and **Pre-existing Token Gardens**. Each has a unique setup process and certain economic implications, weigh your options before proceeding.


### Native Token Gardens

This is the type of Garden that 1Hive uses. The advantage of this option is that the economics are for the most part figured out for you.

When a community launches this type of Garden, they also create a community token. This token is used to grant voting power to vote on proposals that allocate shared resources from the Common Pool.

The key features are:

* A configurable amount of community tokens is minted and sent to the common pool.
* An airdrop of initial tokens can be made by the garden creator to accounts within the related community.
* A [Dynamic Issuance Policy](https://forum.1hive.org/t/dynamic-honey-supply-policy-proposal/2224) is configured to mint and burn the community tokens relative to a specified threshold of tokens in the common pool.

### Pre-existing Token Gardens

Under this type of Garden, you have more flexibility in the sense that you are importing an existing token that may already have its own supply policy and rules associated with it. Once imported, this token is used to attribute voting power over the Garden's shared resources.

One key difference between this model and the native model is the [incentive contract](https://github.com/1Hive/unipool). The incentive contract is used to reward users who import their existing ERC-20 token into the Garden in order to gain governance rights within that Garden.

The community creating the Garden is encouraged to:

* Allocate a portion of their treasury to the Garden common pool.
* Send tokens to the [incentive contract](https://github.com/1Hive/unipool) in order to reward users who wrap the original token to earn governance rights in the Garden.

## Technical Details

1. The Common Pool funds are handled by an [Aragon Agent app](https://aragon.org/agent).
2. Gardens accepts [several configuration parameters](../developers/apps/) to initialize them.
3. Pre-existing Token Gardens have a [build-in reward system](../garden-creators/byot-garden-wrapping-incentive.md) to incentivize participation in governance.
