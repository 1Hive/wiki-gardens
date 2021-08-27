---
description: >-
  Used to change protocol parameters or smart contract updates. Actions that
  require making discrete, binary choice decisions via voting.
---

# Tao Voting

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

`voteMinAcceptanceQuorum` is the minimum fraction of the total supply that needs to be in support for a decision vote to pass. For example, a value of 0.1 means that in order to pass there must be at least 10 percent of the total supply voting in favour.

`voteSupportRequired` is the minimum fraction of voting stake \(yes power / voted power\) that needs to be in support for a decision vote to pass. For example, a value of 0.5 means over 50% of voting stake needs to be in support.

`voteDurationDays` is the base duration of each vote in days.

`delegatedVotingPeriodDays` is the duration from the start of a vote that representatives are allowed to vote on behalf of principals.

`voteQuietEndingPeriodDays` is the duration  before the end of a vote to detect non-quiet endings. Non-quiet endings are endings which involve a late swing in the vote.

`voteQuietEndingExtensionDays` is the duration to extend a vote in the case of a non-quiet ending. 

`voteExecutionDelayDays` is the duration to wait before a passed vote can be executed. This allows people to react to the outcome and make decisions before the effects of the vote are realised. 

