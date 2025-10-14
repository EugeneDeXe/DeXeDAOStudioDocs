---
cover: .gitbook/assets/rewards.png
coverY: 0
---

# 💰 Rewards System

Existing DAOs struggle with low activity due to incentive imbalance. Members who invest time and cover costs in decision-making do not receive more benefits than less active members. This lack of differential rewards demotivates active participation, leading to decision-making often falling to a small, engaged group. This imbalance undermines both motivation and the principles of decentralized governance in DAOs.

Incentivizing DAO members through rewards for their significant contributions to the organization's activities is an essential strategy. This approach encourages high-quality contributions and compensates members for the time and gas fees they incur.

DeXe DAO Studio has designed a flexible rewards system that you can easily customize yourself when creating a DAO or later via proposal and voting.&#x20;

## Reward types

DeXe DAO Studio has implemented three main types of rewards for the user voting phase that you can enable in your DAO:

### Voting Rewards

This reward is given to those who vote for proposals the DAO has accepted. In this case, individuals who vote "For" will receive rewards proportionate to their voting power. The distribution of voting rewards is based on the percentage of tokens involved in voting and is allocated to members according to their voting power.

### Proposal Creation Rewards

This crucial type of reward is given for creating a proposal that the DAO later accepts. Such rewards encourage members to take the initiative. However, useless or not accepted proposals are not rewarded, ensuring that DAO members need to prove value to earn the reward and that the DAO does not waste funds. In this type of reward, you set a fixed number of token rewards for creating a proposal.

### Transaction Execution Rewards

This reward offsets the costs for those executing transactions after a proposal is accepted.&#x20;

You set a specific number of token rewards for transaction execution.



## Voting Rewards Distribution

### Total number of rewards&#x20;

The allocation of rewards in a given voting process is determined by the total number of tokens participating in this vote. For instance, if the DAO voting rewards are set at 1%, the aggregate reward received by all members will be equivalent to 1% of the total tokens utilized in the voting process.

{% hint style="success" %}
Hint: You can configure the percentage of the voting power, that will be rewarded for voting, when creating the DAO or change it later with a DAO decision.
{% endhint %}

### Distribution of rewards between voting participants

The allocation of rewards to voters is determined based on their Voting Power (VP). Various voting systems within the DeXe DAO Studio use different methods to calculate Voting Power. Let's look at them in detail.

### **Linear Voting**&#x20;

In this model, all votes are counted linearly, equivalently to the number of tokens held. Therefore, voting power changes directly to the number of tokens of DAO members, and rewards will be distributed according to the number of tokens they use to vote.

### **Meritocratic Non-linear Voting or Custom Logic**

In Meritocratic Non-linear or Custom Voting Logic, the voting power does not equal the number of tokens. All the rewards are distributed proportionally to the Voting Power.

You can read how voting power is calculated In the Meritocratic Non-linear voting system [at the link](https://whitepaper.dexe.network/meritocratic-governance/mathematical-logic).

### Experts and delegators rewards&#x20;

An Expert is a person or DAO trusted by the community of another DAO who is granted this status through a proposal and voting process. Members can delegate governance tokens to any member of their DAO. It lets them transfer decision-making power to other DAO members or experts, allowing them to withdraw their tokens anytime. When delegating, tokens are locked in a smart contract, and only their owner can revoke them. Learn more about experts [by the link.](https://docs.dexe.io/advanced-features/experts)

{% hint style="info" %}
Delegating tokens to an expert with a high VEI is more profitable than voting by yourself.
{% endhint %}

If the DAO has experts with a higher voting rate, it is beneficial for members to delegate tokens to experts because they have higher voting power coefficients than other members. However, it is necessary to consider that according to the Meritocratic Non-linear voting system, as the number of tokens on the balance increases, the function of calculating the voting power will deliberately slow down its growth.

When deciding whether to delegate to a particular expert, it is necessary to consider his **Voting Efficiency Index (VEI).**

$$VEI=VotingPower/TokenNumber$$

\
Consequently, in this voting model only experts can have a VEI of more than 1, and delegating to experts with a greater VEI is beneficial.

### Expert voting rewards distribution

Let's look at the distribution of voting rewards among experts and delegates. Ordinary DAO members receive 80% of the rewards from tokens they delegate, while experts receive a 20% commission.

### Rewards distribution for delegated from DAO Treasury Tokens

The DAO can also delegate tokens from its Treasury, which allows more tokens to be used in actual governance and attracts authoritative and competent parties to the organization. Experts can use tokens delegated from the Treasury for voting and receive rewards, as well as those delegated by DAO members, but rewards are distributed in other proportions.

Experts receive 1.618% of the rewards for tokens delegated from the Treasury. The remaining 98.382% are returned to the Treasury.

### NFTs with rewards multiplier

DeXe DAO Studio allows customization for adjusting the additional multiplier for voting rewards within the NFT for DAO members. The NFT collection is created through a proposal and voting using the appropriate template. You can customize the NFT validity time and the multiplier of the rewards received.

The NFT with reward multipliers is the top calculation level and is applied after all other reward calculation formulas. For example, look at the Dexe Protocol NFT rewards campaign and read how it works [at the link](https://dexenetwork.medium.com/the-rewards-program-within-the-dexe-protocol-dao-66d0ffbfc8d5).

## DeXe Protocol rewards commissions

DeXe Protocol and DeXe DAO Studio are free to use, except for commission on token sales and rewards. Reward fees are directed to DeXe Protocol DAO's treasury to contribute to the further development of the protocol and decentralized governance technologies. The current reward fee rate is 30%.

## Rewards claiming

To get the rewards, you have to claim them on your profile page. Also, you can withdraw your tokens back into your wallet here. All the rewards are distributed from the DAO treasury, and any token from the treasury can be assigned as a reward token. You can always check which token is assigned for rewards distribution and other rewards settings on the Voting Rules DAO page.

Rewards are credited even if the reward token has an insufficient balance in the treasury or is missing. In this case, you can claim your reward later, when the treasury will have enough reward token balance.



See more about how to get rewards in our video:

{% embed url="https://youtu.be/fO2ouf7FSsE?si=jonbNLYOnNo2GkJ2" %}
