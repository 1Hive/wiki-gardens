# Aragon Apps

> TODO

Gardens inherit the base template Aragon apps.

[https://github.com/aragon/dao-templates/blob/master/shared/contracts/BaseTemplate.sol](https://github.com/aragon/dao-templates/blob/master/shared/contracts/BaseTemplate.sol)  


The additional apps are listed here:

{% embed url="https://github.com/1Hive/gardens/blob/master/packages/hardhat/contracts/appIds/AppIdsRinkeby.sol" %}



The only app an out of the box Garden needs to use from the base template is the Agent app. 

We actually create two instances of Agent, one for the Common Pool, and the other for treasury assets that are not part of the Common Pool \( assets which are held in another token or which are not distributable through conviction voting\).



