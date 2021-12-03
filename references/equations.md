# Equations

## Staking

$$
deposit = withdrawal
$$

Swaps between HETA and sHETA during staking and unstaking are always honored 1:1. The amount of HETA deposited into the staking contract will always result in the same amount of sHETA. And the amount of sHETA withdrawn from the staking contract will always result in the same amount of HETA.

$$
harvest = 1 - ( HETA_{Deposits} / sHETA_{Outstanding} )
$$

The treasury deposits HETA into the distributor. The distributor then deposits HETA into the staking contract, creating an imbalance between HETA and sHETA. sHETA is harvested to correct this imbalance between HETA deposited and sHETA outstanding. The harvest brings sHETA outstanding back up to parity so that 1 sHETA equals 1 staked HETA.

## Bonding

$$
bond Price = 1 + Premium
$$

HETA has an intrinsic value of 1 MAI, which is roughly equivalent to $1. In order to make a profit from bonding, HemetaHeta charges a premium for each bond.

$$
Premium = debt Ratio * BCV
$$

The premium is derived from the debt ratio of the system and a scaling variable called [BCV](https://docs.hemetaheta.finance/references/glossary#bcv). BCV allows us to control the rate at which bond prices increase.

The premium determines profit due to the protocol and in turn, stakers. This is because new HETA is minted from the profit and subsequently distributed among all stakers.

$$
debt Ratio = bondsOutstanding/HETA_{Supply}
$$

The debt ratio is the total of all HETA promised to bonders divided by the total supply of HETA. This allows us to measure the debt of the system.

$$
bondPayout_{reserveBond} = marketValue_{asset}\ /\ bondPrice
$$

Bond payout determines the number of HETA sold to a bonder. For [reserve bonds](https://docs.hemetaheta.finance/references/glossary#reserve-bonds), the market value of the assets supplied by the bonder is used to determine the bond payout. For example, if a user supplies 1000 MAI and the bond price is 250 MAI, the user will be entitled 4 HETA.

$$
bondPayout_{lpBond} = marketValue_{lpToken}\ /\ bondPrice
$$

For [liquidity bonds](https://docs.hemetaheta.finance/references/glossary#liquidity-bonds), the market value of the LP tokens supplied by the bonder is used to determine the bond payout. For example, if a user supplies 0.001 HETA-MAI LP token which is valued at 1000 MAI at the time of bonding, and the bond price is 250 MAI, the user will be entitled 4 HETA.

## HETA Supply

$$
HETA_{supplyGrowth} = HETA_{stakers} + HETA_{bonders} + HETA_{DAO} + HETA_{pHETAExercise}
$$

HETA supply does not have a hard cap. Its supply increases when:

* HETA is minted and distributed to the stakers.
* HETA is minted for the bonder. This happens whenever someone purchases a bond.
* HETA is minted for the DAO. This happens whenever someone purchases a bond. The DAO gets the same number of HETA as the bonder.
* HETA is minted for the team, investors, advisors, or the DAO. This happens whenever

  the aforementioned party exercises their pHETA.

$$
HETA_{stakers} = HETA_{totalSupply} * rewardRate
$$

At the end of each epoch, the treasury mints HETA at a set [reward rate](https://docs.hemetaheta.finance/references/glossary#reward-rate). These HETA will be distributed to all the stakers in the protocol. You can track the latest reward rate on the [HemetaHeta Policy dashboard](https://dune.xyz/shadow/HemetaHeta-Policy).

$$
HETA_{bonders} = bondPayout
$$

Whenever someone purchases a bond, a set number of HETA is minted. These HETA will not be released to the bonder all at once - they are vested to the bonder linearly over time. The bond payout uses a different formula for different types of bonds. Check the [bonding section above](equations.md#bonding) to see how it is calculated.

$$
HETA_{DAO} = HETA_{bonders}
$$

The DAO receives the same amount of HETA as the bonder. This represents the DAO profit.

$$
HETA_{pHetaExercise} = pHETA + MAI
$$

The individual would supply 1 pHETA along with 1 MAI to mint 1 HETA. The pHETA is subsequently burned.

## Backing per HETA

$$
HETA_{backing} = treasuryBalance_{stablecoin} + treasuryBalance_{otherAssets}
$$

Every HETA in circulation is backed by the Hemeta's treasury. The assets in the treasury can be divided into two categories: stablecoin and non-stablecoin.

$$
treasuryBalance_{stablecoin} = RFV_{reserveBond} + RFV_{lpBond}
$$

The stablecoin balance in the treasury grows when bonds are sold. [RFV](https://docs.hemetaheta.finance/references/glossary#rfv) is calculated differently for different bond types.

$$
RFV_{reserveBond} = assetSupplied
$$

For reserve bonds such as MAI bond, the RFV simply equals to the amount of the underlying asset supplied by the bonder.

$$
RFV_{lpBond} = 2sqrt(constantProduct) * (\%\ ownership\ of\ the\ pool)
$$

For LP bonds such as HETA-MAI bond, the RFV is calculated differently because the protocol needs to mark down its value. Why? The LP token pair consists of HETA, and each HETA in circulation will be backed by these LP tokens - there is a cyclical dependency. To safely guarantee all circulating HETA are backed, the protocol marks down the value of these LP tokens, hence the name _risk-free_ value \(RFV\).

