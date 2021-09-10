---
description: Aragon app used to increase and decrease token supply
---

# Dynamic Issuance

The [Dynamic issuance app](https://github.com/1Hive/issuance-dynamic) parameters \(together with the 1hive defaults\) are:

```javascript
"issuanceTargetRatio": 0.3,
"issuanceThrottle": 0.1,
```

Where:

`issuanceTargetRatio`is the ideal fraction of the total supply that should be in the Common Pool.  For example, a value of 0.3 means that 30% of the total supply should ideally be in the Common Pool.

`issuanceThrottle` is the maximum issuance that can happen in a year. For example, a value of 0.1 means there can never be more than 10% new issuance per year.

