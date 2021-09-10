---
description: >-
  Aragon app used to collectively update smart contracts and protocol parameters
  (formerly disputable voting)
---

# Tao Voting

The [Tao Voting app](https://github.com/1Hive/disputable-voting) parameters \(together with the 1hive defaults\) are:

```text
"voteMinAcceptanceQuorum": 0.1,
"voteSupportRequired": 0.5,
"voteDurationDays": 5,
"delegatedVotingPeriodDays": 2,
"voteQuietEndingPeriodDays": 1,
"voteQuietEndingExtensionDays": 0.5,
"voteExecutionDelayDays": 1,
```

Where:

`voteMinAcceptanceQuorum` is the minimum percentage of the total token supply that needs to be in support for a decision vote to pass. For example, a value of 0.1 means that in order to pass there must be at least 10 percent of the total token supply voting in favour.

`voteSupportRequired` is the minimum percentage of voting stake \(yes power / voted power\) that needs to be in support for a decision vote to pass. For example, a value of 0.5 means over 50% of voting stake needs to be in support.

`voteDurationDays` is the base duration of each vote in days.

`delegatedVotingPeriodDays` is the duration from the start of a vote that Delegates are allowed to vote on behalf of Delegators.

`voteQuietEndingPeriodDays` is the duration before the end of a vote to detect non-quiet endings. Non-quiet endings are endings which involve a late swing in the vote.

`voteQuietEndingExtensionDays` is the duration to extend a vote in the case of a non-quiet ending.

`voteExecutionDelayDays` is the duration to wait before a passed vote can be executed. This allows people to react to the outcome and make decisions before the effects of the vote are realised.

## Recommendations

Since there are only one set of voting parameters for all Gardens components, strong thresholds for passing proposals in TV are critical to ensure the Gardens integrity remains uncompromised. `voteSupportRequired` and `voteMinAcceptanceQuorum` are your main defensive parameters in this aspect.

The `delegatedVotingPeriodDays` should be short enough to leave room for Delegators across all time-zones to verify how their Delegates have voted, and veto if necessary. It is recommended to leave a difference of at least one full day between the `delegatedVotingPeriodDays` and the `voteDurationDays`.

The `voteQuietEndingExtensionDays` should give enough time for your community to mobilize in case of malicious voters or contentious proposals.

The `voteExecutionDelayDays` should offer your members enough time to view and consider the consequences of a passed proposal, and if possible, exit the DAO if they so choose.

## More Resources

[Quiet Ending](https://forum.1hive.org/t/tao-voting-quiet-ending-period-and-quiet-ending-extension/4224) [Delegation](https://forum.1hive.org/t/tao-voting-delegation/4225)

