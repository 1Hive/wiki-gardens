# Dynamic issuance

Veneto Gardens come with a dynamic supply policy that can burn and issue tokens from the common pool automatically. The default parameters are inherited from [1hive's issuance policy](https://forum.1hive.org/t/dynamic-honey-supply-policy-proposal/2224).

Gardens which collectively allocate resources productively should expect to see increases in demand for their token outpace issuance, either due to their token being removed from the circulating supply \(fee capture\), or due to demand for their token increasing as a result of supply sinks \(eg staking mechanisms\).

### Details

There is a public function which anyone can call which can adjust the the total supply of the token.

However, instead of just issuing the token at a fixed rate, it adjusts the Total supply in order to target a certain percentage of the total supply in the Common Pool by either issuing new tokens to the Common Pool, or Burning tokens from the Common Pool.

The mechanism makes adjustments to the supply using a proportional control function where the further from the target the system is, the greater the magnitude of the adjustment.

```text
error = (1 - current_ratio / target_ratio) / seconds_per_year
```

This `error` term tells us how much we should be adjusting the supply to get back to the target ratio. The `seconds_per_year` constant smooths the adjustments so that even though we can adjust on a per block basis, it would take approximately a year \(all else equal\) for the system to get back to the target ratio.

To ensure that we can provide a simple and easy to understand upper bound on how quickly the total supply can change over time, we can limit the magnitude of any adjustment by a throttle parameter.

```text
error = (1 - current_ratio / target_ratio) / seconds_per_year

if error < 0:
	adjustment = max(error, -throttle) * supply
else:
  adjustment = min(error, throttle) * supply 
```

In practice the throttle is an artificial limit on the ability for the mechanism to adjust supply, if the throttle kicks in it will take longer for the system to reach the target ratio and may reach an equilibrium that is higher or lower than desired.

From a governance perspective this is useful because Gardens have the ability to make it significantly more difficult \(or impossible\) to adjust the throttle and reserve ratio parameters, while allowing more strategic discretion over the conviction voting parameters that determine the outflow rate from the common pool.

### Parameter Choice

Gardens need to determine which values will be initially used for the `initial_ratio` ,`target_ratio` and `throttle` .

See the[ dynamic issuance app](../documentation-for-developers/apps/dynamic-issuance.md) for more on these parameters.

#### Model Overview

To help inform your decisions, we highly encourage anyone interested in the topic to [read carefully through this forum post](https://forum.1hive.org/t/dynamic-honey-supply-policy-proposal/2224) and get their [hands on the model](https://github.com/1Hive/luna-swarm/tree/master/honey-supply) we created to come to help us come to our own decisions.

> It’s important to note that all models are imperfect representations of reality but can help to create a better and more robust shared understanding of how we expect the system to behave and make the assumptions we are basing our decisions on more explicit.

Play around with it, if you have question or aren’t familiar with the tooling, you can [ask for guidance on our discord.](https://discord.gg/KTbHy6fSqx)





