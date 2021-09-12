# Aragon Apps

All Gardens inherit the [base template](https://github.com/aragon/dao-templates/blob/master/shared/contracts/BaseTemplate.sol) Aragon apps.

The additional apps that make up a Garden are [listed here](https://github.com/1Hive/gardens/blob/master/packages/hardhat/contracts/appIds/AppIdsRinkeby.sol).

{% hint style="info" %}
The only app a newly created Garden uses from the base template is the [Agent app](https://hack.aragon.org/docs/guides-use-agent).  
  
A Garden actually has two instances of Agent, one for the Common Pool, and the other for treasury assets that are not part of the Common Pool \(assets which are held in another token or which are not distributable through conviction voting\).
{% endhint %}



