# Types of Gardens

We currently support two types of Gardens: **Veneto** \(native token\)  and  **Boboli** \(imported token\) Gardens.

Each Garden has a Common Pool which will hold DAO funds that can be requested by proposals made on a Gardens. Your community can choose how to contribute funds to this pool.

### Veneto Gardens

This is the type of Garden that 1hive uses. It comes with a powerful [dynamic issuance policy](issuance-policy/dynamic-issuance.md) \(the details of which you can fine tune\).

When a community launches this type of Garden, they also create a community token. This token is used to grant voting power to vote on proposals that allocate shared resources from the Common Pool.

The key features are:

* A configurable amount of community tokens is minted and sent to the common pool.
* A pre-distribution of initial tokens can be made by the garden summoner to accounts within the related community.
* A [Dynamic Issuance Policy](https://forum.1hive.org/t/dynamic-honey-supply-policy-proposal/2224) is configured to mint and burn the community tokens relative to a specified threshold of tokens in the common pool.
* A configurable amount of community tokens is minted and sent to the common pool.
* An airdrop of initial tokens can be made by the garden creator to accounts within the related community.
* A [Dynamic Issuance Policy](https://forum.1hive.org/t/dynamic-honey-supply-policy-proposal/2224) is configured to mint and burn the community tokens relative to a specified threshold of tokens in the common pool.

### Boboli Gardens

Under this type of Garden, you have more flexibility in the sense that you are importing an existing token that may already have its own supply policy and rules associated with it. Once imported, this token is used to attribute voting power over the Garden's shared resources.

One key difference between this type of garden and a Veneto garden is the [incentive contract](https://github.com/1Hive/unipool). The incentive contract can be used to reward users who import their existing ERC20 token into the Garden in order to gain governance rights within that Garden.

The community creating the Garden is encouraged to:

* Allocate a portion of their treasury to the Garden common pool.
* Send tokens to the [incentive contract](https://github.com/1Hive/unipool) in order to reward users who wrap the original token in exchange for governance rights in the Garden.
* Allocate a portion of their treasury to the Garden common pool.
* Send tokens to the [incentive contract](https://github.com/1Hive/unipool) in order to reward users who wrap the original token to earn governance rights in the Garden.

## Technical Details

1. The common pool funds are handled by an [Aragon Agent app](https://aragon.org/agent).
2. Gardens accept s[everal configuration parameters](documentation-for-developers/apps/) to initialize them.
3. Boboli Gardens have a [built-in reward system](garden-creators/byot-garden-wrapping-incentive.md) to incentivize participation in governance.

