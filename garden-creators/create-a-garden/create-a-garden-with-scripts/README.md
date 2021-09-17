# Create a Garden \(with scripts\)

## Setup

Clone the Gardens repo:

```text
git clone https://github.com/1Hive/gardens
cd gardens
```

Install dependencies:

```bash
yarn
```

Go to the hardhat package:

```text
cd packages/hardhat
```

Compile contracts:

```text
yarn compile
```

Create a `.env` file with the configuration of your wallet and Ethereum node for the network you are interacting with. In the repo, you will find a `.env.example`. 

In case you want to use a hardware wallet we recommend using the [Frame](https://frame.sh) wallet. Remember to run the script with the `frame` the network defined in the `hardhat.config.ts` file.

The account used to create the garden must contain the necessary amount of Honey to lock in a Honeyswap pair, at least $100 worth, specified in the parameters below. If creating a Native Token Garden with a token GDN, the Honey will be locked in the HNY/GDN pair. If creating a Pre-existing Token Garden with a token OGT, some of the community existing token OGT must also be available in the account, specified in the parameters below, and this will be locked in the HNY/OGT pair. The LP tokens for this liquidity are burnt.

If you would like to test on Rinkeby, use the [HNYT token](https://rinkeby.etherscan.io/token/0x3050e20fabe19f8576865811c9f28e85b96fa4f9). You can exchange it on Uniswap for the Rinkeby network.

## Configure Garden Parameters

The Garden [parameters](../../../on-chain-governance/protocol-parameters/) are configured in a file with the name `params-<garden-type>.json` where `<garden-type>` is the type of Garden you will create.

Let's unpack the configuration options.

### Type Of Garden

First, you have to decide [which type of Garden is the best fit for you](../../garden-modes.md).

If you decide to deploy a[ Veneto Garden](../../garden-modes.md#veneto-gardens) you have to set:

* **Existing token:** must be the zero address `0x0000000000000000000000000000000000000000`
* **Garden token name:** the name of the new token that will be created.
* **Garden token symbol:** the symbol of the new token that will be created.
* **Seeds:** a list of addresses that will be minted the specified amount of tokens.
* **Common pool amount:** the ****number of tokens that will be minted to the common pool.
* **Honey token liquidity in xDai:** the honey deposit quantified in terms of xdai - must be at least 100 or the garden creation will revert.
* **Garden token liquidity:** the ****initial number of tokens that will be used to [create a pair in Honeyswap](../../honeyswap.md) with HNY.

If you decide to deploy a [Boboli Garden](../../garden-modes.md#boboli-gardens) you have to set:

* **Existing token:** must be the address of the community's current ERC20 token.
* **Garden token name:** the name of the new token received when wrapping the existent. We recommend following the convention: Existing `Token Name` -&gt; `Garden Token Name` eg `Honey` -&gt; `Garden Honey`
* **Garden token symbol:** the symbol of the new token received when wrapping the existing token. We recommend following the convention: `TKN` -&gt; `gTKN`.
* **Existing token liquidity:** the ****initial number of tokens that will be used to [create a pair in Honeyswap](../../honeyswap.md) with $100 worth of HNY.

### Community Covenant

As we explain in the [three pillars](../../../on-chain-governance/garden-framework/#community-covenant-to-encode-values), [the Covenant](../../../on-chain-governance/garden-framework/covenant.md) will be one of the pillars of your community. Take your time to encode your community's values in it. Once you have it ready you should upload it with a markdown format to the [IPFS network](https://ipfs.io). We recommend using a pinning service like [Pinata](https://pinata.cloud/) to keep the content pinned and accessible. 

Here are a couple of examples:

* [1Hive's Covenant](https://ipfs.io/ipfs/QmfWppqC55Xc7PU48vei2XvVAuH76z2rNFF7JMUhjVM5xV)
* [Agave's Covenant](https://ipfs.io/ipfs/QmfPADUzzPTda8LZsqQwpfquzG3awt8pFoCB2BQAuvEyFV)
* [Giveth's Covenant](https://ipfs.io/ipfs/QmarPWD4MQMKrh6aqBHo5n8PvqYocu6z6JczzkGwi9XHsm)

Next, you can fill in the next parameters:

* **Agreement title:** A title for the Covenant.
* **Agreement content:** IPFS hash uploaded of the Covenant content, with the format `ipfs:<hash>`.

### Aragon Apps Initialization

The rest of the parameters are the initial configuration for the [Dynamic Issuance](https://github.com/1Hive/issuance), [Conviction Voting](https://github.com/1Hive/conviction-voting-app), [Agreements](https://github.com/1Hive/agreement), and [Disputable Voting](https://github.com/1Hive/disputable-voting) Aragon apps. We recommend leaving the default configuration in most cases. To discuss this topic in more detail reach out to us on [Discord](https://discord.gg/d5XyGkA5uF).

```javascript
{ 
  "issuanceTargetRatio": 0.3,
  "issuanceThrottle": 0.1,
  "convictionGrowthHours": 48,
  "spendingLimit": 0.1,
  "minimumConviction": 0.025,
  "minActiveStakePercentage": 0.2,
  "requestToken": "0x0000000000000000000000000000000000000000",
  "agreementTitle": "1Hive Community Covenant",
  "agreementContent": "ipfs:QmfWppqC55Xc7PU48vei2XvVAuH76z2rNFF7JMUhjVM5xV",
  "settlementPeriod": 3,
  "proposalDeposit": 0.1,
  "challengeDeposit": 0.1,
  "proposalDepositStable": 100,
  "challengeDepositStable": 100,
  "voteSupportRequired": 0.5,
  "voteMinAcceptanceQuorum": 0.1,
  "voteDurationDays": 0.002083334,
  "delegatedVotingPeriodDays": 0.00138889,
  "voteQuietEndingPeriodDays": 0.000694445,
  "voteQuietEndingExtensionDays": 0.00068288,
  "voteExecutionDelayDays": 0.000694445
}
```

For more detailed explanations of these parameters [see here](../../../on-chain-governance/protocol-parameters/agreement.md).

