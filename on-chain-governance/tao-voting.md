---
description: 'To transform the DAO: changes to protocol parameters or smart contract updates'
---

# Tao voting

> Right now **there is no user interface for the creation of a Tao vote**. A technical user must prepare a transaction which creates a Tao vote. Its best practice for such transactions to be reviewed by many people publicly before they are submitted. 
>
> We are working on a UI to allow anyone to be able to create a Tao vote. In the meantime, we are happy to guide non-technical users through the process.

Tao voting is a special form of voting \(requiring community consensus around discrete, binary choice decisions\). It is used to update governance parameters \(metagovernance\), as well as anything that fundamentally changes or transforms the DAO's DNA.

From a design perspective, Gardens aims to minimise the need to make discrete decisions, favouring bottom up decision making and local autonomy of participants.  As such Tao votes are not expected to be used for day to day operations or for determining strategic direction.

## Process 

Once a Tao vote is created it will show up in the frontend as a _decision._ 

Under the default initialisation parameters, Tao votes are open for 2 weeks. In order to pass there must be an **approval quorum** of at least 10 percent of the total supply voting in favour, and over 50% of voters in support.

 If a vote is approved, there is a 48 hour delay before the vote can be enacted, allowing people to react to the outcome and make decisions before the effects of the vote are realised. 

Additionally, the entire balance of the Garden token for accounts which vote in support of a decision are locked as soon as they vote yes, preventing all transfers from their address until after the vote has concluded. 

This restriction helps to ensure that people that vote in favour of a decision have a strong belief that approving the decision is both necessary and beneficial to the community because they will be locked in and exposed  to any changes in value associated with a controversial decision being forced through, while people who vote against are free to exit by selling their tokens.

## Scope

### Smart contracts

Gardens DAOs are made up of smart contracts that regulate how tokens are issued and distributed. 

Communities may find they have a need in the future to upgrade or change parameters that influence how these contracts work.

We expect that the need for such changes will become increasing rare, and perhaps eventually become so rare they are deemed unnecessary, but for now it is seems prudent to retain the ability to upgrade contracts via decision votes. If and when the community deems appropriate a decision vote can be used to remove the capability of making any future decisions. 

### Covenant

Tao voting can be used to propose changes to the [Covenant](covenant.md).

### **Protocol parameters**

Tao voting can be used to update the DAO's protocol parameters.

## Relationship with Dandelion voting

Tao Voting is an upgraded version of Dandelion Voting with familiar parameters such as **Support Required**, **Minimum Quorum**, **Execution Delay** and **Vote Duration**.

Tao Voting also comes with two new concepts: **Delegation** and **Quiet Ending**.

### Delegation

Token holders can delegate their Tao Voting powers to another member who will cast votes on their behalf, these members become delegates. Delegates can only vote during the Delegate Voting Period, which is a specified amount of time at the beginning of the voting process. If a delegate votes contrary to their delegator the delegator can veto the delegated vote and cast their vote themselves. Any voter, delegate or otherwise, can only vote ONCE.

### Quiet ending

In the latter portion of the Vote Duration there’s a designated Quiet Ending Period \(QEP\). If during this period the vote outcome is flipped the Quiet Ending Extension\(QEE\) will trigger. The QEE will add more time to the voting period, giving eligible members who have not yet voted more time to do so. If the vote outcome flips again during QEE then another QEE will trigger, adding more time to vote. Voting closes only when the QEP or QEE ends without the vote outcome flipping.

