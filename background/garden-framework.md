---
description: >-
  Together, the three pillars of Conviction voting, the Community covenant, and
  Celeste provide a framework for effective on-chain governance
---

# The Three Pillars

A Garden has three main pillars:

1. A novel voting system \(Conviction voting\)
2. A decentralised social contract \(Community Covenant\)
3. A dispute resolution protocol \(Celeste\)

Taken together, they fulfill the promise of effective community-driven, on-chain governance. Not tomorrow, but today.

## **Conviction voting \(to allocate funds\)**

_Conviction voting is the heart of a Garden._ It allows folks to signal their preferences continuously rather than forcing them to “make a decision.” From the perspective of a community member, this is as easy as just showing up and supporting the things you care about.

Under conviction voting, **the majority doesn’t need to achieve consensus on everything.** As such, we get real [proportional representation](https://en.wikipedia.org/wiki/Proportional_representation#Advantages_and_disadvantages). Community members can propose and support things they care about without fear that a whale will vote them down. In fact, there is no downvoting. **People with large stakes and strong opinions can’t suppress the community.**. Rather than relying entirely on majority rule decision-making, resource allocation decisions are regulated by staking on proposals to accumulate conviction over time. This allows resources to be allocated fairly while minimizing the political and divisive process of coming to consensus on a single course of action.[**1**](garden-framework.md#notes)

**Proposals simply need enough support to pass – the fewer funds they ask for, the less support required.** This means there’s a real sense in which everyone has a voice. The only thing token holders have to think about is whether or not they support something. _That’s it._

Under this framework, **many divergent initiatives can be proposed and run in parallel**. This allows the DAO to explore, experiment, and innovate quickly and seamlessly. If an experiment works, a larger proposal can then be submitted.

One underrated benefit of this is that it allows the DAO to grow as a [headless brand](https://otherinter.net/web3/headless-brands/), iterating through cycles of [divergence and convergence](https://otherinter.net/web3/market-protocol-fit/), and continuously reflecting the preferences and interests of token holders \(a true living organisation!\).

In sum, by giving small token holders the agency to contribute, **Conviction Voting helps lay the foundation for a fiercely loyal community**, solving the problems associated with governance attacks, low participation, and the overall inability to effectively prioritise and decide when there are many potential options all competing for consideration at once.

## **Community Covenant \(to encode values\)**

The second pillar of a Garden is the community covenant.[**2**](garden-framework.md#notes) You can think of it as a constitution or **decentralised social contract** of sorts.

On a practical level, a covenant is a document, stored on [IPFS](https://hackmd.io/KCS70fPRR9O0iXOLYCzK1w?view), which explains what a DAO is about in plain English. It establishes values, rules, and customs. And is used to protect the DAO from malicious actors _without_ sacrificing the agency of its members. It should be designed as an essential resource in moments of conflict and contextual reference for jurors \(Keepers\) to rule on a challenged proposal that has been escalated to court \(Celeste\).

The key idea here is that a covenant allows an organisation’s actions to be governed by a subjective set of rules; rules which are either impossible to encode into smart contracts, or which would otherwise result in a complicated and slow-moving organization.

Take [1Hive’s Covenant](https://1hive.org/#/covenant), for example:

> **1Hive is a community of activists seeking to build a future that is more free, fair, open, and humane.**
>
> 1Hive is also an economic protocol, similar to Bitcoin or Ethereum, where a digital currency, Honey, is issued and distributed programmatically. Unlike Bitcoin or Ethereum, the 1Hive protocol does not narrowly define the set of activities that are valuable but instead relies on community members to guide the distribution process by creating and staking on Honey distribution proposals.
>
> The goal of the 1Hive protocol is to foster a healthy community economy by allocating a steady stream of Honey towards development, maintenance, and **improvement of the common goods that bring the most value to the 1Hive community**…

Anyone interacting with the 1Hive protocol has to abide by this covenant. In particular, any proposal which violates the spirit of the covenant can be challenged and taken to Celeste \(a decentralised court\).

In a sentence, a covenant allows a DAO to adhere to an agreement specifying its values, as well as outline subjective rules for what types of proposals are allowed. This unlocks the ability for much more nuanced and complex governance.

## **Celeste \(to protect values\)**

The third pillar of Gardens, Celeste, serves as **the interface for a DAO’s shared values, beliefs, and hopes**. It provides a way to resolve subjective disputes, and to peacefully enforce the covenant.

More technically, **Celeste is a** [**BrightID**](https://www.brightid.org/) **integrated fork of Aragon Court** – the integration with BrightID allows for placing limits on how much stake an individual can add to the system.

While we’ll save the details for a dedicated follow-up post, I think it’s worth mentioning here that Celeste is invoked only if and when an action is challenged \(i.e. only in exceptional circumstances\).

Once Celeste is invoked, a decentralised \(and randomly selected\) group of BrightID verified humans – called Keepers – is drafted to rule on the dispute \(they are tasked with deciding whether or not the disputed action is compatible with that community’s covenant\).[**3**](garden-framework.md#notes)

If the Keepers decide the proposal is compatible, on-chain execution continues. If they decide it is not, the proposal is blocked.[**4**](garden-framework.md#notes)

By allowing even small token holders to challenge proposals that aren’t in line with the values of the community, Celeste provides a trustless way to uphold a DAO’s core values.[**5**](garden-framework.md#notes)

Celeste is a protocol on its own if you are interested in learning more about it check their [official documentation](https://1hive.gitbook.io/celeste/).

## **In sum**

Gardens provides a beautiful foundation for public communities to coordinate around shared resources in a bottom-up fashion.

By combining three of the most important pieces of decentralised software ever written – Conviction Voting\(Continous Signal Voting\), Community Covenants \(Aragon Agreements\), and Celeste \(a BrightID integrated Aragon Court\), we are able to fulfill the promise of effective community-driven on-chain governance, not tomorrow, but today.

With these building blocks, we now have essentially limitless abilities for completely decentralised, and completely autonomous organisations.

## **Notes**

1. Rather than relying entirely on majority rule decision making, resource allocation decisions are regulated by staking on proposals to accumulate conviction over time. This allows resources to be allocated fairly, while minimizing the political and divisive process of coming to consensus on a single course of action.
2. Covenants are the bridge between a Garden organisation and Celeste \(the dispute resolution mechanism\).
3. Well-reasoned [cryptoeconomic incentives](https://1hive.gitbook.io/celeste/keepers/dispute-lifecycle) ensure that the keepers converge to the most reasonable outcome for the dispute.
4. It’s important to note that Celeste can be used to rule on disputes arising over _any_ human readable English document that allows for the possibility of subjective outcomes, not just a Covenant. For example, you could use it to decide on whether work, as outlined in a funding proposal, was actually completed or not.
5. Celeste acts as a check on the power of _all_ individuals – even highly-trusted community members. In doing so, it protects the long-term integrity of the DAO.

