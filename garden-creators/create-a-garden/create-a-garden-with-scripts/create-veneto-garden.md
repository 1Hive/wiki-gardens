# Create Veneto Garden

## Script Execution

The Garden [parameters](../../../on-chain-governance/protocol-parameters/) are configured in a file with the name `params-veneto.json`.

The JSON file is formatted as follows:

```javascript
{
  "gardenTokenName": "Garden",
  "gardenTokenSymbol": "GDN",
  "seeds": {
    "0x4355a2cdec902c372f404007114bbcf2c65a3eb0": 10000
  },
  "commonPoolAmount": 3000,
  "honeyTokenLiquidityInXdai": 100,
  "gardenTokenLiquidity": 100,
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
  "voteDurationDays": 5,
  "delegatedVotingPeriodDays": 2,
  "voteQuietEndingPeriodDays": 1,
  "voteQuietEndingExtensionDays": 0.5,
  "voteExecutionDelayDays": 1
}
```

Once you are happy with the parameters. Execute the following `yarn` command:

```text
yarn new:garden:veneto --network <network>
```

This may take a couple of minutes. You should expect an output similar to:

```text
❯ hardhat run scripts/new-veneto-garden.ts --network <netwok>
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
  commonPoolAddress: '0xfE5be80856c196ff6061aEb7cffbaFA305c027e2',
  convictionVotingAddress: '0xCf1cC60d1dFbd0b8A48f23F3b25fBA0D233D70A1',
  tokenManagerAddress: '0x127787b54B99a7bc4dd3D494dd3935392cD123B3',
  issuanceAddress: '0x30d8F982Dc18d9925FB7136d1C3A72d71712ac9B',
  agreementAddress: '0x3a263Eef7dc6Ff19610d976A022f85309328B7dE',
  votingAddress: '0xFF3aF9d841d003911b8F82AacCBAA9F60A7275a3',
  votingAggregatorAddress: '0x5B4c27ab7ec2eE69B9AB19fa5E4bC5D0355f3f1f',
  priceOracleAddress: '0x006d42F0eBeF8bc85fe75625d3487cf625e24abb',
}
```

