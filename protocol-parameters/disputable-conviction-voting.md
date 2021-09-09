# Conviction Voting

The Conviction Voting parameters \(together with the 1hive defaults\) are:

```text
  "convictionGrowthHours": 48,
  "spendingLimit": 0.1,
  "minThreshold": 0.025,
  "minEffectiveStake": 0.2,
```

Where:

`convictionGrowthHours` refers to how quickly support charges up and down. When a community member starts supporting a proposal, the support \(called conviction\) does not immediately apply but instead must charge up over time according to an exponential decay function or half-life. The lower the value `convictionGrowthHours` has the faster the support charges up. In the default case, `convictionGrowthHours` is set to `48` which means that support charges up to half its potential value in 2 days \(2 days = 48 hours\). By extension after 4 days support will have charged up to 3/4 of its potential value, after 6 days, 7/8, after 8 days, 15/16, etc.

`spendingLimit` sets the threshold formula to only allow proposals that request less than a `spendingLimit` proportion of the available funds from the common pool. In the default case, it is set to `0.1`, which means no proposal can request more than 10% of the funds from the common pool.

`minimumConviction` is the minimum conviction required for small proposals. By requiring all proposals to have some minimum conviction to pass, we are able to prevent small proposals from spamming or draining the communal funding pool. In the default case, it is set to `0.025`, which means the required threshold for any proposal is at least 2.5% of the max conviction that the currently active staked tokens could accrue.

`minEffectiveStake` is the minimum percent of the token's current supply \(including the common pool\) that is used to calculate the conviction. If the actual active stake is below `minActiveStakePercentage`, then `minActiveStakePercentage` is used to calculate conviction voting required thresholds instead of active stake. In the default case, it is set to `0.2`,which means that the minimum percent of the token's current supply used to calculate conviction is 20%.

## Recommendations

We can see that there is a minimum amount of conviction that must be reached for any proposal, and also a maximum achievable funds released for a single proposal. These are important bounds for a community to establish for their funding pool.

As such, we recommend that implementers take special care in their choice of `spendingLimit` \(% of total funds that can be requested by any one proposal\) and `minimumConviction` \(the minimum conviction required for small proposals to pass\) parameters, as these will have a high impact on your system design.

The `convictionGrowthHours` effectively sets the pace of your Garden. How quickly decisions can be made are affected heavily by this parameter. If you want your DAO's funding scheme to be more agile then a lower value is recommended. If you prefer to have a more prolongated, assured process then a higher value is better suited.

## More resources

[Minimum Conviction](https://forum.1hive.org/t/cv-params-deep-dive-minimum-conviction-aka-minimum-threshold/4209)  
[Spending Limit](https://forum.1hive.org/t/cv-params-deep-dive-spending-limit-aka-max-ratio-beta/4208)  
[Coviction Growth](https://forum.1hive.org/t/cv-params-deep-dive-conviction-growth-aka-half-life/4207)

