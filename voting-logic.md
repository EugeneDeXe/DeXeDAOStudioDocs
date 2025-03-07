---
cover: .gitbook/assets/voting logic.png
coverY: 0
---

# ✅ Voting logic

Several configurable parameters for voting are set for different types of proposals:

**Quorum** – the minimum amount of voting power ("Yes" – in favour; or "No" – opposed) to accept or decline a proposal (respectively).

**Duration of voting** - the period during which the main voting phase occurs.

**Execution delay** - the time interval after the end of the main voting phase during which the proposal cannot be executed. In the case of proposals with consequences that some organization members may disagree with, this gives them time to exit the organization.

**Early voting completion** - a parameter that determines whether the main voting phase can be prematurely concluded if the quorum "for" or "against" is reached early.

When [creating a DAO](creating-a-dao.-getting-started/), the following are configured:

1. **General voting settings** are applied by default to all types of proposals.
2. **Changing voting settings** rules for modifying parameters needed to change the general voting settings.

After creating a DAO, flexible parameters can be configured for different types of proposals using proposal changes to regulate the difficulty of decision-making depending on the potential consequences of each type of proposal. Separate voting rules can be configured for individual executor contracts, each of which can handle multiple types of proposals with similar execution mechanics.

Additionally, when creating a DAO, minimum governance token balances are configured to create a proposal and participate in voting.

### On-chain voting

On-chain proposals refer to a voting mechanism where the results are recorded on the blockchain and trigger the execution of a transaction performing the function specified by the type of proposal. This could involve various actions such as assigning roles within the DAO, transferring funds from the treasury, executing custom contracts, etc. This ensures that decisions made through voting are executed transparently and securely, following the predetermined rules of the DAO.

In on-chain voting, users always have the option to vote either "for" or "against" a given proposal. To acknowledge a proposal, the total "for" or "against" votes must meet a predetermined quorum. Once the quorum is reached, the majority of votes either "for" or "against" decides if the proposal is accepted or rejected. The required % of DAO’s governance token total supply needed for a quorum can vary for different types of proposals.

Some proposals may have parameters that allow for early completion; if the voting reaches the required quorum either "for" or "against", the voting process can be closed prematurely. Users only see the voting results once the proposal has been completed, reducing the chance for speculative voting or herd behaviour motivated by rewards and statistics.

### Off-chain voting

Off-chain proposals are a feature where the results don’t trigger any actions on the blockchain but are instead recorded in the backend. These proposals are essential for validating ideas or bringing up topics for discussion. They don’t require Validators' voting and execution and are particularly useful for preliminary consensus building. Once an off-chain proposal is accepted, it can be converted to an on-chain proposal if its nature aligns with one of the available on-chain proposal types, allowing for the execution of tangible actions on the blockchain based on community consensus.

For off-chain proposals, there are three types of voting available:

1. **For/Against Voting:** Similar to on-chain voting, this type allows users to determine whether they support the initiative or not.
2. **Single-Choice Option:** This voting method permits users to select one option from several, making it ideal for decisions where a single choice needs to be made among alternatives.
3. **Multiple-Choice Option:** In this voting style, users can choose multiple options simultaneously. It proves beneficial when prioritising or selecting multiple options from various choices.

## Validator's voting

Validator voting is the second round activated when configuring the Validators assigned during creating a DAO or when making further changes to the DAO's constitution. It is an additional security measure designed to protect the DAO from malicious proposals and manipulations, similar to double-factor authentication. After the main voting phase, the Validator voting begins. Validators use a separate token that cannot be transferred to another wallet. Validator voting takes effect after the main voting phase and also has its own quorum and voting duration settings. After the Validator voting ends, the proposal is either accepted and proceeds to the execution stage or rejected.

Additionally, Validators have their own types of proposals that they can conduct without involving the entire DAO. These proposals are essential for managing the DAO's sustainability processes that do not require full DAO participation to avoid slowing down operations.

## Voting Models

Navigating governance in a decentralized world presents a unique set of challenges. Traditional frameworks often struggle to balance efficiency and inclusivity and rarely scale well with the community's evolving needs. The Protocol suggests a solution to this challenge with various voting models. When you create a DAO, you can choose a governance logic that best suits your objectives.

### Linear Voting

Linear governance is a clear-cut approach where each token grants one vote, providing simple and direct decision-making. Such a configuration is ideal for small organizations with uncomplicated tasks that do not require complex governance logic.

While easy to understand and implement, the linear model doesn't leverage the full capabilities of the Protocol. In this model, all votes are counted linearly, equivalently to the number of tokens held. Features like expert functionality and token delegation are underutilized in such DAOs. The reason is that an expert's vote is treated the same as a regular token holder's vote, regardless of their level of expertise or trust within the DAO community. Additionally, this model does little to combat the consolidation of power, as any number of tokens can be concentrated in a single wallet without diminishing voting strength.

**Advantages:**

* Ease of Use: The linear voting model is easy to understand and implement.
* Clarity in Vote Counting: The method for tallying votes is transparent and straightforward.

**Disadvantages:**

* Underutilization of Platform Features: The model doesn't motivate users to delegate tokens to experts, thus not taking full advantage of the platform's functionalities.
* Lack of Power Decentralization: No mechanisms to discourage the concentration of tokens (and, thus, power) in a single wallet. No deterring factors or incentives exist to encourage the delegation of tokens.
* Lack of Flexibility.

### Nonlinear Voting

Weighted voting is a nonlinear voting system designed to determine the voting power based not just on token balance but also on various parameters aimed at enhancing governance efficiency and establishing a more flexible voting logic.

Nonlinear functions in this system serve to prevent plutocracy — the concentration of power in the hands of a few — by slowing down the increase in voting power as a token balance grows. This mechanism better reflects the voices of the community and diminishes the influence of large token holders.

Furthermore, weighted voting considers different coefficients when tallying votes for different groups, fully embracing the role of experts within a DAO. It creates mechanisms for building competent communities where expertise can be rewarded in decision-making processes. Ordinary DAO members can delegate their tokens to qualified experts who vote on behalf of regular holders, thus enhancing the significance of their tokens. It also saves time and gas fees by delegating decision-making to trusted experts.

DeXe Protocol DAO has introduced a specially designed governance model focusing on knowledge, expertise, and participant contributions. This model contains a combination of mathematical and conceptual measures that counteract the concentration of power in a single party, considering expertise in vote counting and encouraging active involvement by incentivisation mechanisms.

**Advantages:**

* Antiplutocratic: promotes a democratic and equitable voting structure by mitigating power dominance.
* Power of expertise: rewards knowledge and expertise over mere token ownership.
* Flexible in design: enhances adaptive approach in designing DAOs with complex structures and specific needs.

**Disadvantages:**

* More challenging to implement: demands a complex approach for implementation, requiring a more profound knowledge of math models.

DeXe Protocol DAO has developed its weighted voting model, which will be elaborated on in the section about the concept of Meritocratic Governance below. This model incorporates mathematical and conceptual solutions, blending linear and nonlinear functions to achieve practical decision-making tools. It incentivizes DAO members, encourages competent decisions, and enhances protection against malicious actions that could disrupt the DAO's operations. As with the entire Protocol, this model is open-source and will be available for selection when creating a DAO on the DeXe Protocol.

### Custom voting logic

The Protocol offers the ability to customize your voting model by integrating it as a custom contract that meets all the necessary Protocol standards. When setting up a custom voting logic, the DAO creator assumes full responsibility for tallying votes and distributing rewards for voting, as the Protocol cannot guarantee the security of user-designed solutions. However, DeXe Protocol DAO encourages the discovery of more advanced and forward-thinking governance models and therefore provides this capability out-of-the-box. The Protocol includes all the necessary methods for connecting custom contracts for the voting model.

