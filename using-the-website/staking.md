# 🦦 Stake Your HETA

Staking allows you to earn HETA passively via auto-compounding. By staking your HETA with HemetaHeta, you receive sHETA (staked HETA) in return at a 1:1 ratio. After that, your sHETA balance will increase automatically on every epoch based on the current APY.

## How to Buy HETA

{% hint style="warning" %}
Purchase HETA on: [Quickswap](https://quickswap.exchange). Make sure to **check the slippage first** before buying HETA, as some venue offers worse rate than the others due to low liquidity.
{% endhint %}

1. Go to [this Sushiswap swap page](https://app.sushi.com/swap?outputCurrency=0x383518188c0c6d7730d91b2c03a03c837814a899). We use Sushiswap as an example here. It is recommended to compare the exchange rate across different DEXes to ensure you are getting the best price.
2. Make sure the output currency is HETA. You can also copy and paste the [HETA contract address](broken-reference) into the output currency field to ensure you are swapping for the right token.

![Paste HETA contract address](../.gitbook/assets/ohm\_contract.png)

1. You can select any input currency based on your available wallet balance. It is recommended to use MAI as the input currency to minimize the slippage.

![Make sure the output currency is HETA](../.gitbook/assets/buy\_ohm.png)

1. Select the amount of HETA you want to swap for. Then click "Approve" and sign the transaction.
2. After the "Approve" transaction has been processed successfully, click "Swap" and sign the transaction.
3. You should see HETA in your wallet balance now after the swap transaction is successful. If you cannot find it in your wallet, add [HETA contract address](broken-reference) to your wallet.

{% hint style="info" %}
The "Approve" transaction is only needed when you swap HETA for the first time; subsequent swapping only requires you to perform the "Swap" transaction.
{% endhint %}

## How to Stake

1. Go to the [Stake page of the HemetaHeta website](https://app.hemetaheta.finance/#/). Select the "Stake" tab.
2. Enter the amount of HETA that you would like to stake in the input field. If you would like to stake all your HETA, press the "Max" button and the input field will be populated with all your available HETA balance.
3. Click "Approve" and sign the transaction.
4. After the "Approve" transaction has been processed successfully, click "Stake" and sign the transaction. Voila, you have staked your HETA!

## How to Unstake

1. Go to the [Stake page of the HemetaHeta website](https://app.hemetaheta.finance/#/). Select the "Unstake" tab.
2. Enter the amount of sHETA that you would like to unstake in the input field. If you would like to unstake all your sHETA, press the "Max" button and the input field will be populated with all your available sHETA balance.
3. Click "Approve" and sign the transaction.
4. After the "Approve" transaction has been processed successfully, click "Unstake" and sign the transaction.

_Note: The "Approve" transaction is only needed when staking/unstaking for the first time; subsequent staking/unstaking only requires you to perform the "Stake" or "Unstake" transaction._

## Reading the Info

![The staking page](../.gitbook/assets/staking\_page\_index.png)

**APY** tells you the annualized rate of return based on the reward yield. It takes into account the effect of compounding since sHETA harvests exponentially.

**TVL** measures the dollar amount of all the staked HETA in HemetaHeta.

**Current Index** allows you to track your gain from staking. The index started from 1 at epoch 0, and increases every epoch. If you staked at genesis (epoch 0) and never unstaked any HETA, your balance today would be X times greater, where X is the current index. You can use the index to track your position by marking down the index number when you stake and unstake. You divide the index number when you unstake by the index number when you stake to get the ratio by which your sHETA balance has increased.

**Your Balance** tells you how many unstaked HETA are in your wallet. This is the maximum amount that you can stake.

**Your Staked Balance** tells you how many staked HETA are in your wallet. This is the maximum amount that you can unstake.

**Next Harvest** tells you the remaining time until the next harvest.

**Reward Yield** tells you how much your sHETA balance will increase when the next epoch begins. For example, if you stake 100 HETA and the upcoming harvest is 0.5427%, your sHETA balance would increase from 100 to 100.5427.

**ROI (5-Day Rate)** estimates how much your sHETA balance will increase after 5 days, if the reward yield stays the same during this period. For example, if you stake 100 HETA and the rate is 8.4577%, your sHETA balance would increase from 100 to 108.4577 after 5 days.
