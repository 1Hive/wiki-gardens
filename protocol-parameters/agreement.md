# Covenant

{% hint style="info" %}
The [covenant](../on-chain-governance/covenant.md) parameters are set in the [Agreement app](https://github.com/1Hive/agreement): an Aragon app used to define and enforce subjective rules that cannot be easily encoded in smart contracts.
{% endhint %}

The parameters \(together with the 1hive defaults\) are:

```text
"agreementTitle": "1Hive Community Covenant",
"agreementContent": "ipfs:QmfWppqC55Xc7PU48vei2XvVAuH76z2rNFF7JMUhjVM5xV",
"settlementPeriod": 3,
"actionAmount": 0.1,
"challengeAmount": 0.1,
"actionAmountStable": 100,
"challengeAmountStable": 100,
```

Where:

 `agreementTitle` is the title of the Community Covenant

`agreementContent` is the IPFS hash of the Community Covenant

`settlementPeriod` is the interval of time that starts when an action is challenged and lasts until it’s either resolved between the parties \(submitter and challenger\) or escalated to Celeste.

`proposalDeposit` is the initial amount of the token a community member needs to stake in order to perform an action \(for example, to create a proposal\). In 1hive's case it's 0.1 HNY, hence the 0.1 value given above.

`challengeDeposit`  is the initial amount of the token a community member needs to stake in order to challenge an action \(for example, to challenge a proposal\). In 1hive's case it's 0.1 HNY, hence the 0.1 value given above.

`proposalDepositStable` is the amount of the token in USD terms that a community member needs to stake in order to perform an action. This value is used to update `proposalDeposit`.

`challengeDepositStable` is the amount of the token in USD terms that a community member needs to stake in order to challenge an action. This value is used to update `challengeDeposit`.

## Recommendations

We recommend using symmetrical values for both the action and challenge amounts. This ensures it is just as easy to create a proposal as it is to challenge one.

Defining a stable \(USD\) action and challenge amount brings with it important UX and security considerations. From a security point of view, it means the Garden relies on a price oracle \(an extra attack surface\). From a UX point of view, community members need to ensure the value is kept up to date - this requires regularly executing a transaction to update the action and challenge amounts.

On the other hand, without a stable action and challenge amount, you may find you have to update `proposalDeposit` and `challengeDeposit` using a decision vote at some point - this is more costly and can take many days to pass.

As such, we recommend thinking hard about whether it makes sense for you to launch with or without defining `proposalDepositStable` and `challengeDepositStable`.

#### A note on the price oracle

Honeyswap inherits Uniswap's price accumulator. This means it uses a price accumulator for each pair which it stores once every 3 hours. The price the oracle gives is the average of these over the previous 24 hours. If the oracle misses being called in a 3 hour period you have to wait another 24 hours of it being called consistently every 3 hours for it to return a price. In sum, the attack vector to be aware of is your Honeyswap GDN/XDAI pair being manipulated consistently for at least 24 hours.

