---
description: >-
  Used to change protocol parameters or smart contract updates. Actions that
  require making discrete, binary choice decisions via voting.
---

# Tao Voting

Tao Voting \(TV\) is the voting process by which a Garden can modify its settings post-launch. It is a very powerful voting application that is capable of performing many high-impact actions, including:

* Mint and burn tokens
* Install and remove Applications in
* Modify the parameters of all existing Applications

TV is an upgraded version of Dandelion Voting with familiar parameters such as **Support Required**, **Minimum Quorum**, **Execution Delay** and **Vote Duration**.

Tao Voting also comes with two new concepts: **Delegation** and **Quiet Ending**.

### Delegation

Token holders can delegate their Tao Voting powers to another member who will cast votes on their behalf, these members become delegates. Delegates can only vote during the Delegate Voting Period, which is a specified amount of time at the beginning of the voting process. If a delegate votes contrary to their delegator the delegator can veto the delegated vote and cast their vote themselves. Any voter, delegate or otherwise, can only vote ONCE.

### Quiet Ending

In the latter portion of the Vote Duration there’s a designated Quiet Ending Period \(QEP\). If during this period the vote outcome is flipped the Quiet Ending Extension\(QEE\) will trigger. The QEE will add more time to the voting period, giving eligible members who have not yet voted more time to do so. If the vote outcome flips again during QEE then another QEE will trigger, adding more time to vote. Voting closes only when the QEP or QEE ends without the vote outcome flipping.

The Tao Voting parameters \(together with the 1hive defaults\) are:

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

