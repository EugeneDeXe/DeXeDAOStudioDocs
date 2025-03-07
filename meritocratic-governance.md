---
cover: .gitbook/assets/meritocratic governance.png
coverY: 0
---

# 💎 Meritocratic Governance

## Challenges of Existing Voting Models <a href="#challenges-of-existing-voting-models" id="challenges-of-existing-voting-models"></a>

DeXe has identified significant weaknesses in the current methodologies after a meticulous examination of various voting systems. The **linear voting model**, which parallels the standard direct democratic system, fails to recognize the expertise or knowledge levels of the participants. In this model, each vote is equal, regardless of the voter's competence and trust. It's a scenario where the vote of a random person holds the same weight as that of a Nobel laureate, provided they have an equal number of tokens. Moreover, linear voting does not safeguard against the risk of plutocracy, where power becomes concentrated in the hands of a few individuals with substantial resources.

**Square root voting**, offered as a potential remedy by notable figures, including Vitalik Buterin, has its own traps. In particular, using the square root function in quadratic voting can be manipulated. With this function, when _√x > x_ (for values between 0 and 1), where _x — is token balance_, and _y — is voting power_, it allows for synergistic manipulation. Participants could split their large token holdings into numerous smaller wallets, exploiting this function to amplify their influence without incurring extra costs.

<figure><img src="https://whitepaper.dexe.network/~gitbook/image?url=https:%2F%2F3671592714-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252Fy3BU6XjkMvE5ZpghiFRu%252Fuploads%252FiZcXhLjd8Sb0YVL8A4qa%252FFrame%25201171275840.png%3Falt=media%26token=dc75c912-3038-4291-b683-08deeb0b359a&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=e7d95e3aa1f31201673761c859efeb06fdd23bcf983cc5ae2e5644dd398997d5" alt=""><figcaption></figcaption></figure>

Therefore, both of these approaches exhibit significant limitations, inadequately addressing the expertise of participants, the risks of power concentration and manipulations. DeXe Protocol DAO is pursuing a more balanced and resilient system that diminishes these shortcomings and paves the way for broad parties engagement on equitable terms.

## Conceptual Objectives

Recognizing the strengths and weaknesses of existing models, DeXe has intentionally chosen a path of piecewise linear and nonlinear functions and has established the following criteria for the mathematical model of vote tallying and reward distribution.

### **Combatting Plutocracy and Monopoly**

The more tokens that are concentrated in one's hands, the less effective the voting power calculation should be – this helps prevent the accumulation of too much influence by any single party. As the number of tokens in a balance increases, the function for calculating voting power will deliberately slow down its growth.

### **Meritocracy**

The chosen mathematical model must account for the presence of experts and specialists whose determination is regulated by the DAO itself and whose voting efficiency is greater than that of an average token holder. Moreover, the distribution of voting efficiency among different experts can also vary.

### **Preventing Sybil Attacks and Manipulations**

Nonlinear functions must prevent exploitation in areas where they exceed the value of the linear function **y = x** (where **y** — is voting power, and **x** — is token balance). Users should not be able to distribute their token balances across multiple wallets and exploit the vote/reward counting function in areas with the most efficient growth.

### **Proportionality of Vote Strength to Rewards**

If the model includes rewards, they should be distributed proportionally to the voting power according to the respective nonlinear functions. Firstly, this incentivizes the delegation of tokens to experts for whom the voting power calculation functions are more favourable than for regular holders. Furthermore, it discourages delegating all tokens to a single expert, as the more tokens an expert holds, the fewer rewards will be paid out for each token.



## Mathematical Logic

DeXe Protocol DAO employs a nonlinear voting system that accounts for more than just the number of tokens held; it also factors in the DAO's level of trust in the voter and a variety of other controlled and customizable parameters to ensure the organization's balanced operation. At the heart of DeXe Protocol DAO's vote calculation are piecewise-defined functions allowing precise control over voting power values across all ranges, minimizing the risk of manipulation. To construct these nonlinear dependencies, the Protocol utilizes polynomial functions of the 4th and 3rd degree.

<figure><img src=".gitbook/assets/Group 1171275550.png" alt=""><figcaption></figcaption></figure>

The graph displays three functions, each illustrating how the voting power increases with the number of tokens for different cases:

1. The function for regular DAO members — the ordinary token holders.
2. The function for experts who have been granted the relevant status within the DAO, in case if 100% of the tokens are either on their own balance or delegated from the private balances of regular DAO members. This function assigns more weight to the votes of those selected by the DAO's decision.
3. The function for experts whose tokens are 100% delegated from the treasury. As shown, tokens delegated from the Treasury confer even greater weight to the experts' votes, reflecting the DAO's exceptional trust in such entities mirrored in the strength of their vote.
4. In cases where experts have tokens delegated to them both from the balances of regular DAO members and from its treasury, the function for calculating voting power will yield an intermediate value between functions 2 and 3. This value is proportionate to the ratio of tokens delegated from the treasury to those delegated by regular DAO members plus any tokens from the expert's own balance.

### Members’ function

The function for regular DAO members is a piecewise dependence consisting of two ranges: from 0% to 7% of the token's Total Supply, there's a standard linear function where the voting power is equal to the number of tokens; from 7% to 100% of the Total Supply, it's a third-degree polynomial that gradually slows its growth, preventing the concentration of power with large token holdings on a single DAO member's balance.

Unlike the square root function, this dependency prevents potential manipulations with low token balances, avoiding the exploitation of rapid function growth at smaller ranges. Thanks to its piecewise nature, the developed dependence is more balanced and secure.

$$V_{m}(t) = \begin{cases}  k_m \Bigg(7 \cdot TS \cdot \frac{1}{100}  + a \left(\frac{100t}{TS} - 7\right) \\ \quad + b \left(\frac{100t}{TS} - 7\right)^2  + c \left(\frac{100t}{TS} - 7\right)^3\Bigg)\frac{TS}{100}, & \text{for } t \geq 7\% \text{ of } TS \\\\ t, & \text{otherwise} \end{cases}$$

**Where:**

**`V_m`** — voting power for regular DAO members

**`t`** — token balance of a voter

_**`TS`** — total supply of a DAO_

_**`k_m`** —_ the slope factor for the function applied to DAO members. By default, the value of _k\_m_ = 0.97

**`a`**, **`b`**, **`c`** — parameters, which are defined to best suit the mathematical and conceptual objectives. By default, there value is:

_**a** = 1.041_

_**b** = -0.007211_

_**c** = 0.00001994_

### Expert function

The function for regular experts is a piecewise-defined 4th-degree polynomial composed of two ranges, each with its own set of coefficients for each partial. The piecewise nature of the functions allows for more precise control over the voting power value.

The basis is the core function _**V\_exp**_**(**_**t**_**)**. For each expert, this base function will have its own slope coefficient, _**k**_, within a specific range. By default, _**k**_ is within the range \[0.92; 1.08]. If all tokens are delegated to the expert from the DAO's treasury, their _**k**_ coefficient will be 1.08 — the maximum value. If all tokens are delegated to the expert by regular DAO members or are owned by the expert, _**k**_ will be at the minimum value of 0.92.

In cases where an expert has tokens delegated from both the treasury and regular members, their coefficient _**k**_ is calculated based on the proportion of these tokens, indicated as _**R** (R=1, when 100% tokens are from the treasury and R=0, when 100% tokens are from the members' balances)_.

The formula for the _**k**_ parameter is as follows:

$$k = k_{\text{min}} \cdot R + k_{\text{max}} \cdot (1 - R)$$

Therefore, the value of the expert function will be determined within the range of the piecewise-defined function _&#x56;_&#x65;xp(_t_) with k\_min = 0.92 and \*k\_\*max = 1.08:

$$V_{exp}(t) = \begin{cases}  k \Bigg(a + b \left(\frac{100t}{TS} - 6.63\right)  + c \left(\frac{100t}{TS} - 6.63\right)^2 \\ \quad + d \left(\frac{100t}{TS} - 6.63\right)^3  + e \left(\frac{100t}{TS} - 6.63\right)^4\Bigg)\frac{TS}{100}, & \text{for } t \geq 6.63\% \text{ of } TS \\\\ k \Bigg(f \left(\frac{100t}{TS}\right)^4  + g \left(\frac{100t}{TS}\right)^3 \\ \quad + h \left(\frac{100t}{TS}\right)^2  + i \left(\frac{100t}{TS}\right)\Bigg)\frac{TS}{100}, & \text{otherwise} \end{cases}$$

**Where:**

**`V_exp`** — voting power

**`t`** — token balance of a voter

_**`TS`** — total supply of a specific DAO_

_**`k`** — the slope factor for the function applied to experts of a DAO. By default, the value of k varies from 0,92 to 1,08 depending on the proportion of tokens delegated from the treasury and from members wallets or owned tokens. The greater the proportion of tokens delegated from the treasury, the higher the value of k, and consequently, the higher the values the function will reach._

**`a`, `b`, `c` , `d` , `e` , `f` , `g` , `h` , `i`**_— parameters, which are defined to best suit the mathematical and conceptual objectives. By default, there value is:_

_**`a`** = 8.83755895036092_

_**`b`** = 1.130_

_**`c`** = -0.006086_

_**`d`** = 0.00004147_

_**`e`** = -0.000000148_

_**`f`** = -0.001328_

_**`g`** = 0.023761_

_**`h`** = -0.169889_

_**`i`** = 1.801894_
