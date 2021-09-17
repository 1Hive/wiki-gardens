# Create Boboli Garden

The Garden [parameters](../../../on-chain-governance/protocol-parameters/) are configured in a file with the name `params-boboli.json`.

The JSON file is formatted as follows:

```javascript
{
  "gardenTokenName": "Garden Bright",
  "gardenTokenSymbol": "gBRIGHT",
  "existingToken": "0x779ec783bbeec9350b3efb8bec775c6379f5e218",
  "honeyTokenLiquidityInXdai": 100,
  "existingTokenLiquidity": 1000,
  "convictionGrowthHours": 48,
  "spendingLimit": 0.1,
  "minimumConviction": 0.025,
  "minActiveStakePercentage": 0.2,
  "requestToken": "0x0000000000000000000000000000000000000000",
  "agreementTitle": "Bright Charter",
  "agreementContent": "ipfs:QmTwvZ9VJy1gTXxSVMmFY5W4t71aadd52SmGfygcSGp9jV",
  "settlementPeriod": 3,
  "proposalDeposit": 500,
  "challengeDeposit": 500,
  "proposalDepositStable": 50,
  "challengeDepositStable": 50,
  "voteSupportRequired": 0.5,
  "voteMinAcceptanceQuorum": 0.1,
  "voteDurationDays": 5,
  "delegatedVotingPeriodDays": 2,
  "voteQuietEndingPeriodDays": 1,
  "voteQuietEndingExtensionDays": 2,
  "voteExecutionDelayDays": 1
}

```

Once you are happy with the parameters. Execute the following `yarn` command:

```text
yarn new:garden:boboli --network <network>
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
  daoAddress: '0x38c2C0b72B86858C04352356650AB8cEc61D5FC9',
  commonPoolAddress: '0xfE5be80856c196ff6061aEb7cffbaFA305c027e2',
  convictionVotingAddress: '0x34fe61274a47371c855a7693eB88F9FAd5f77E7a',
  tokenManagerAddress: '0xC3749f257742450E3270675e7bce59cc23E4870C',
  issuanceAddress: '0x943957b519E7eF5E505d0bDa5FA6227771B7e92B',
  agreementAddress: '0x176735474907E1fDFc75093e2a334b0409e3C170',
  votingAddress: '0x9a667c19Db59F7c8d66E4adf3199EC2bd33cf1bc',
  votingAggregatorAddress: '0x66052B8Cc7B404cd26EB5F35480c6138bb5ed605',
  priceOracleAddress: '0x420788930852FE94b746A834c6C636b50009684E',
  unipoolAddress: '0x420788930852FE94b746A834c6C636b50009684E',
  unipoolDepositorAddress: 0x176735474907E1fDFc75093e2a334b0409e3C170
}
```

