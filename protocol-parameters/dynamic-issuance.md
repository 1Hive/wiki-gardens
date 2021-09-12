# Dynamic Issuance

{% hint style="info" %}
The [dynamic issuance](../issuance-policy/dynamic-issuance.md) parameter are set in the [Dynamic Issuance app](https://github.com/1Hive/issuance-dynamic): an Aragon app used to increase and decrease token supply
{% endhint %}

The parameters \(together with the 1hive defaults\) are:

```javascript
"issuanceTargetRatio": 0.3,
"issuanceThrottle": 0.1,
```

Where:

`issuanceTargetRatio`is the ideal fraction of the total supply that should be in the Common Pool.  For example, a value of 0.3 means that 30% of the total supply should ideally be in the Common Pool.

`issuanceThrottle` is the maximum issuance that can happen in a year. For example, a value of 0.1 means there can never be more than 10% new issuance per year.

