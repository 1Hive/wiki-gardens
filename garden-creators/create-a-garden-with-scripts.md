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

The Garden parameters are configured in a file with the name `params-<network>.json` where `<network>` is the network configured in the `hardhat.config.ts` file \(this is the network used to execute the deployment script during the Garden creation\).

The JSON file is formatted as follows:

```javascript
{
  "gardenTokenName": "Garden",
  "gardenTokenSymbol": "GDN",
  "seeds": {
    "0xb4124cEB3451635DAcedd11767f004d8a28c6eE7": 2.5,
    "0x8401Eb5ff34cc943f096A32EF3d5113FEbE8D4Eb": 1
  },
  "existingToken": "0x31c952C47EE29058C0558475bb9E77604C52fE5f",
  "commonPoolAmount": 100,
  "honeyTokenLiquidityInXdai": 100,
  "gardenTokenLiquidity": 100,
  "existingTokenLiquidity": 100,
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

Let's unpack the above configuration.

### Type Of Garden

First, you have to decide [which type of Garden is the best fit for you](garden-modes.md).

If you decide to deploy a[ Veneto Garden](garden-modes.md#veneto-gardens) you have to set the:

* **Existing token:** must be the zero address `0x0000000000000000000000000000000000000000`
* **Garden token name:** the name of the new token that will be created.
* **Garden token symbol:** the symbol of the new token that will be created.
* **Seeds:** a list of addresses that will be minted the specified amount of tokens.
* **Common pool amount:** the ****number of tokens that will be minted to the common pool.
* **Honey token liquidity in xDai:** the honey deposit quantified in terms of xdai - must be at least 100 or the garden creation will revert.
* **Garden token liquidity:** the ****initial number of tokens that will be used to [create a pair in Honeyswap](honeyswap.md) with HNY.

If you decide to deploy a [Boboli Garden](garden-modes.md#boboli-gardens) you have to choose:

* **Existing token:** must be the address of the community's current ERC20 token.
* **Garden token name:** the name of the new token received when wrapping the existent. We recommend following the convention: Existing `Token Name` -&gt; `Garden Token Name` eg `Honey` -&gt; `Garden Honey`
* **Garden token symbol:** the symbol of the new token received when wrapping the existing token. We recommend following the convention: `TKN` -&gt; `gTKN`.
* **Existing token liquidity:** the ****initial number of tokens that will be used to [create a pair in Honeyswap](honeyswap.md) with $100 worth of HNY.

### Community Covenant

As we explain in the [three pillars](../on-chain-governance/garden-framework.md#community-covenant-to-encode-values), [the Covenant](../on-chain-governance/covenant.md) will be one of the pillars of your community. Take your time to encode your community's values in it. Once you have it ready you should upload it with a markdown format to the [IPFS network](https://ipfs.io). We recommend using a pinning service like [Pinata](https://pinata.cloud/) to keep the content pinned and accessible. 

Here are a couple of examples:

* [1Hive's Covenant](https://ipfs.io/ipfs/QmfWppqC55Xc7PU48vei2XvVAuH76z2rNFF7JMUhjVM5xV)
* [Agave's Covenant](https://ipfs.io/ipfs/QmfPADUzzPTda8LZsqQwpfquzG3awt8pFoCB2BQAuvEyFV)
* [Giveth's Covenant](https://ipfs.io/ipfs/QmarPWD4MQMKrh6aqBHo5n8PvqYocu6z6JczzkGwi9XHsm)

Next you can fill in the next parameters:

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

For more detailed explanations of these parameters [see here](../protocol-parameters/agreement.md).

## Script Execution

Once you are happy with the parameters. Execute the following `yarn` command:

```text
yarn newdao --network <network>
```

This may take a couple of minutes. You should expect an output similar to:

```text
➜ npx hardhat run scripts/new-dao.ts --network rinkeby
Creating Typechain artifacts in directory typechain for target ethers-v5
Successfully generated Typechain artifacts!
Every 15s a new block is mined in rinkeby.
Create garden transaction one...
Tx one completed: Gardens DAO (0xDA1b46663B5BA949f6213D7c3135080B32AD2295) created.
Create token holders...
Tx create token holders completed.
Create garden transaction two...
Tx two completed.
Create garden transaction three...
Tx three completed.
{
  daoAddress: '0xDA1b46663B5BA949f6213D7c3135080B32AD2295',
  convictionVotingAddress: '0xCf1cC60d1dFbd0b8A48f23F3b25fBA0D233D70A1',
  tokenManagerAddress: '0x127787b54B99a7bc4dd3D494dd3935392cD123B3',
  issuanceAddress: '0x30d8F982Dc18d9925FB7136d1C3A72d71712ac9B',
  agreementAddress: '0x3a263Eef7dc6Ff19610d976A022f85309328B7dE',
  votingAddress: '0xFF3aF9d841d003911b8F82AacCBAA9F60A7275a3',
  votingAggregatorAddress: '0x5B4c27ab7ec2eE69B9AB19fa5E4bC5D0355f3f1f',
  priceOracleAddress: '0x006d42F0eBeF8bc85fe75625d3487cf625e24abb',
  unipoolAddress: '0x0000000000000000000000000000000000000000',
  unipoolDepositorAddress: undefined
}
```

## Include Your Metadata

Now that you have deployed a new Garden on-chain you should add your own data and assets to the Gardens website. To do it, create a PR in the [`dao-list` repository](https://github.com/1Hive/dao-list).

The format of the data you need to include looks as follows:

```javascript
{
    "address": "0x02945Cf2FbCB01119F1B26503b42416b53aF703C",
    "name": "Agave",
    "description": "Agave rewards depositors with passive income and lets them use their deposits as collateral to borrow and lend digital assets",
    "wrappableToken": {
      "logo": "https://raw.githubusercontent.com/1Hive/dao-list/master/src/assets/rinkeby/0x02945Cf2FbCB01119F1B26503b42416b53aF703C/logo.png"
    },
    "logo": "https://raw.githubusercontent.com/1Hive/dao-list/master/src/assets/rinkeby/0x02945Cf2FbCB01119F1B26503b42416b53aF703C/logo.png",
    "logo_type": "https://raw.githubusercontent.com/1Hive/dao-list/master/src/assets/rinkeby/0x02945Cf2FbCB01119F1B26503b42416b53aF703C/logo_type.png",
    "forum": "https://forum.1hive.org/",
    "links": {
      "community": [
        {
          "label": "Discord",
          "link": "https://discord.gg/86eVaKfv2Z"
        },
        {
          "label": "Github",
          "link": "https://github.com/agave-dao"
        },
        {
          "label": "Twitter",
          "link": "https://twitter.com/Agave_lending"
        },
        {
          "label": "Telegram",
          "link": "https://t.me/Agave1Hive"
        },
        {
          "label": "Forum",
          "link": "https://forum.1hive.org/"
        }
      ],
      "documentation": [
        {
          "label": "FAQs",
          "link": "https://wiki.1hive.org/guides/agave-faq"
        }
      ]
    }
  },
}
```

Where:

* **Address:** `Gardens DAO` address showed during the deployment script execution.
* **Token:** an optional asset of `Native Token Gardens` to display the token symbol logo.
* **Descriptions**: a brief description of the community.
* **Wrappable token:** an optional asset of `Pre-existing Token Garden` to display the token symbol logo.
* **Logo:** an optional asset to display the community logo.
* **Logotype:** an optional asset used in the header, to display the community logotype.
* **Forum**: an optional link to the forum where proposals will be discussed. Defaults to [1Hive forum](https://forum.1hive.org).
* **Links:** list of links to display in the footer of the Garden home screen.
* **Documentation:** list of documentation resources to display in the footer of the Garden home screen.

Optionally you can place your assets under the directory: `assets/<network>/<address>`.

