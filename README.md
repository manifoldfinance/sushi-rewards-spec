# sushi-rewards-spec

[Read the spec on HackMD](https://hackmd.io/@sbacha/gas-rebates-sushi)

**Atomic arbitrage profit (aarb)**: is defined as the gain of two atomically executed arbitrage trades $TA$ and $TB$ on exchange $A$ and $B$.


**Non-atomic arbitrage profit (naarb)**: is defined as the arbitrage gain, if $TA$
executes first, and $TB$’s execution follows after $i$ intermediary transactions.



**Holding value ($Hv$)**: is defined as the change in the averaged price of the given asset pair on the two exchanges, which represents the asset value change during the non-atomic execution period.



**Borrowing Capacity ($Bc$)**: Refers to the total value that a borrower is allowed to request from a lending pool, given its collateral amount. For each collateral asset 𝑖 of a borrower, its borrowing capacity is defined in Equation 3.

$$ Bc =∑︁ 𝑉 𝑎𝑙𝑢𝑒 𝑜𝑓 𝐶𝑜𝑙𝑙𝑎𝑡𝑒𝑟al  × LT𝑖 $$


**Health Factor ($Hhf$)**: The health factor measures the collateralization status of a position, defined as the ratio of the borrowing capacity over the outstanding debts (cf. Equation 4).


$$ Hhf = BC / ∑︁  𝑉𝑎𝑙𝑢𝑒 𝑜𝑓 𝐷𝑒𝑏𝑡t $$ 



**MVI**: Mininumal Profitable Viable Input


## Rebate Calculations 
<!--
@version: v0.1.0
@date: 08/11/2021
@license: CC-ND-NC-2.5
@note: naive implementation, expect changes
<!--

bundleCost = mev bribe + bundleTxs[1,2,...]

gasAllowance =  mev bribe - bundleTxs[1,2,...]

BundleTransactionGas[1,2,...] = Individual Gas Cost

BundleId = The Block Number (or hash?) in which the bundle was included

max_gasRebate = (BundleId(BundleTransactionGas[1,2,...]))

