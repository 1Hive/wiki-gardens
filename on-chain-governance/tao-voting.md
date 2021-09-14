---
description: 'To transform the DAO: changes to protocol parameters or smart contract updates'
---

# Decision Voting

{% hint style="info" %}
[See here](../protocol-parameters/disputable-voting.md) for the associated parameters
{% endhint %}

Decision voting is a special form of voting \(requiring community consensus around discrete, binary choice decisions\). It is used to update governance parameters \(metagovernance\), as well as anything that fundamentally changes or transforms the DAO's DNA.

From a design perspective, Gardens aims to minimise the need to make discrete decisions, favouring bottom up decision making and local autonomy of participants. As such Decision votes are not expected to be used for day to day operations or for determining strategic direction.

## Process 

Once a Decision vote is created it will show up in the frontend as a _decision._ 

{% hint style="warning" %}
Right now **there is no user interface for the creation of a Decision vote**. A technical user must prepare a transaction which creates a Decision vote. Its best practice for such transactions to be reviewed by many people publicly before they are submitted.   
  
We are working on a UI to allow anyone to be able to create a Decision vote. In the meantime, we are more than happy to guide non-technical users through the process.
{% endhint %}

Under the default initialisation parameters, Decision votes are open for 2 weeks. In order to pass there must be an **approval quorum** of at least 10 percent of the total supply voting in favour, and over 50% of voters in support.

If a vote is approved, there is a 48 hour delay before the vote can be enacted, allowing people to react to the outcome and make decisions before the effects of the vote are realised.

## Scope

### Smart contracts

Gardens DAOs are made up of smart contracts that regulate how tokens are issued and distributed. 

Communities may find they have a need in the future to upgrade contracts or change parameters that influence how these contracts work.

We expect that the need for such changes will become increasingly rare as a Garden matures, but the ability to upgrade contracts via decision votes will probably always be necessary. Note however, that there is nothing stopping a community from creating a decision vote to remove the capability of making any future decisions. 

### Covenant

Decision voting can be used to propose changes to the [Covenant](covenant.md).

### **Protocol parameters**

Decision voting can be used to update the DAO's protocol parameters.

## Relationship with Dandelion voting

Decision Voting is an upgraded version of Dandelion Voting with familiar parameters such as **Support Required**, **Minimum Quorum**, **Execution Delay** and **Vote Duration**.

Decision Voting also comes with two new concepts: **Delegation** and **Quiet Ending**.

### Delegation

Token holders can delegate their Decision Voting powers to another member who will cast votes on their behalf, these members become delegates. Delegates can only vote during the Delegate Voting Period, which is a specified amount of time at the beginning of the voting process. If a delegate votes contrary to their delegator the delegator can veto the delegated vote and cast their vote themselves. Any voter, delegate or otherwise, can only vote ONCE. Vote delegation is not yet integrated into the UI.

### Quiet ending

In the latter portion of the Vote Duration there’s a designated Quiet Ending Period \(QEP\). If during this period the vote outcome is flipped the Quiet Ending Extension \(QEE\) will trigger. The QEE will add more time to the voting period, giving eligible members who have not yet voted more time to do so. If the vote outcome flips again during QEE then another QEE will trigger, adding more time to vote. Voting closes only when the QEP or QEE ends without the vote outcome flipping.

