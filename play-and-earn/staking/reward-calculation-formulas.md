# Reward Calculation Formulas

The **Beast Borne**, staking model rewards players, based on the amount of **Beast Coin (BST)** staked, the length of the staking period, and the share of the overall staking pool. Below are the key formulas that depict how rewards are calculated in the Beast Borne staking system:

## **Daily Interest Calculation**

Your share of the overall staking pool determines the daily rewards earned through staking in Beast Borne. The formula for calculating daily interest is:

$$
\text{Daily Interest} = \frac{\text{Shares}}{\text{Total Shares}} \times \text{Daily Payout Pool}
$$

Where:

* **Shares**: The number of shares you hold is determined by the amount of BST you staked and the duration of your stake.
* **Total Shares**: The total number of shares held by all stakers in the system.
* **Daily Payout Pool**: The total amount of BST distributed to stakers each day, influenced by the system's inflation rate and penalties from early or late unstakers.

## **Shares Calculation**

When you stake BST, you receive shares based on the amount of BST staked and the length of the stake. The formula for calculating shares is:

$$
\text{Shares} = \text{BST Staked} \times \text{Share Rate} \times \text{Bonus Rate}
$$

Where:

* **BST Staked**: The amount of BST you lock in the stake.
* **Share Rate**: A system-defined rate that increases over time, making earlier stakes more valuable.
* **Bonus Rate**: A bonus multiplier for staking more and longer periods. This bonus is calculated as:

$$
\text{Bonus Rate} = 1 + \left(\frac{\text{Staking Days}}{3650}\right) \times \text{LPB Multiplier}+ \left(\frac{\text{BST Staked}}{100'000}\right) \times \text{MPB Multiplier}
$$

Here, the system sets the **LPB** multiplier, with the maximum **LPB** achieved for a 10-year stake (3,650 days) effectively doubling the shares and M**PB** multipliers.

## **Interest Accumulation Over Time**

Interest (or rewards) accumulates throughout the staking period. The total reward by the end of the staking period is calculated as:

$$
\text{Total Rewards} = \sum_{n=1}^{N} \left(\frac{\text{Shares}}{\text{Total Shares}_n} \times \text{Daily Payout Pool}_n \right)
$$

Where:

* **N**: The number of days in the staking period.
* **Total Shares\_n**: The total shares in the system on day ( n ).
* **Daily Payout Pool\_n**: The daily payout pool on day ( n ).

## **Early Unstaking Penalty**

If you unstake before the end of the staking period, an early unstaking penalty is applied. The penalty typically reduces the interest earned and is calculated as:

$$
\text{Penalty} = \text{Interest Earned} \times \frac{\text{Days Remaining}}{\text{Staking Days}}
$$

Where:

* **Interest Earned**: The interest accumulated up to the point of early unstaking.
* **Days Remaining**: The number of days left in the original staking period.
* **Staking Days**: The total number of days the stake was intended to last.

#### Example 1

* **Share Rate**: 1 (for simplicity).
* **Daily Payout Pool**: 1,000 BST (hypothetical value).
* **Total Shares**: 1,000,000 shares (hypothetical total share count).
* **LPB Multiplier**: 2 (Maximum multiplier achieved for a 10-year stake).

| **BST Staked** | **Staking Duration** | **Daily Reward (BST)** | **Total Reward** |
| -------------- | -------------------- | ---------------------- | ---------------- |
| 1,000 BST      | 1 Month (30 days)    | 1.03 BST               | 30.99 BST        |
| 1,000 BST      | 1 Year (365 days)    | 1.40 BST               | 511.11 BST       |
| 1,000 BST      | 5 Years (1,825 days) | 15.03 BST              | 27,424.87 BST    |
| 10,000 BST     | 1 Month (30 days)    | 10.33 BST              | 309.90 BST       |
| 10,000 BST     | 1 Year (365 days)    | 14.01 BST              | 5,113.02 BST     |
| 10,000 BST     | 5 Years (1,825 days) | 150.27 BST             | 274,248.75 BST   |
| 50,000 BST     | 1 Month (30 days)    | 51.65 BST              | 1,549.50 BST     |
| 50,000 BST     | 1 Year (365 days)    | 70.05 BST              | 25,565.10 BST    |
| 50,000 BST     | 5 Years (1,825 days) | 751.37 BST             | 1,372,243.25 BST |

#### Example 2

#### **Staking 10,000 BST for 1 Month (30 days)**

$$
\text{Shares} = 10,000 \times 1 \times \left(1 + \frac{30}{1820} \times 2 \right) = 10,329.67
$$

$$
\text{Daily Interest} = \frac{10,329.67}{1,000,000} \times 1,000 = 10.33BST
$$

**Total Rewards After 30 Days =** 309.9 BST
