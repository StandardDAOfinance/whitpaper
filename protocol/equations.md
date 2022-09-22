# Equations

## Staking&#x20;

_deposit = withdrawal_&#x20;

Swaps between SDA and sSDA during staking and unstaking are always honored 1:1. The amount of SDA deposited into the staking contract will always result in the same amount of sSDA. And the amount of sSDA withdrawn from the staking contract will always result in the same amount of SDA.&#x20;

_rebase = 1 - ( sdaDeposits / sSDAOutstanding )_&#x20;

The treasury deposits SDA into the distributor. The distributor then deposits SDA into the staking contract, creating an imbalance between SDA and sSDA. sSDA is rebased to correct this imbalance between SDA deposited and sSDA outstanding. The rebase brings sSDA outstanding back up to parity so that 1 sSDA equals 1 staked SDA.&#x20;

## Swapping&#x20;

_swapPrice = 1 + Premium_&#x20;

SDA has an intrinsic value of 1 DAI, which is roughly equivalent to $1. In order to make a profit from swapping, Standard charges a premium for each swap.&#x20;

_Premium = debtRatio \* SCV_&#x20;

The premium is derived from the debt ratio of the system and a scaling variable called SCV. SCV allows us to control the rate at which swap prices increase. The premium determines profit due to the protocol and in turn, stakers. This is because new SDA is minted from the profit and subsequently distributed among all stakers.&#x20;

_debtRatio = swapsOutstanding / sdaSupply_&#x20;

The debt ratio is the total of all SDA promised to swappers divided by the total supply of SDA. This allows us to measure the debt of the system.&#x20;

_swapPayoutreserveSwap = marketValueasset / swapPrice_&#x20;

Swap payout determines the number of SDA sold to a swapper. For reserve swaps, the market value of the assets supplied by the swapper is used to determine the swap payout. For example, if a user supplies 1000 DAI and the swap price is 250 DAI, the user will be entitled 4 SDA.&#x20;

_swapPayoutlpSwap = marketValuelpToken / swapPrice_&#x20;

For liquidity swaps, the market value of the LP tokens supplied by the swapper is used to determine the swap payout. For example, if a user supplies 0.001 SDA-ETH LP token which is valued at 1000 DAI at the time of swapping, and the swap price is 250 DAI, the user will be entitled 4 SDA.&#x20;

## Backing per SDA&#x20;

_SDAbacking = treasuryBalancestablecoin + treasuryBalanceotherAssets ​_&#x20;

Every SDA in circulation is backed by the Standard treasury. The assets in the treasury can be divided into 2 categories: stablecoins and other assets.&#x20;

_treasuryBalancestablecoin = SDABackingStablecoinSwap + SDABackingpSwapStablecoin ​_&#x20;

The stablecoin balance in the treasury grows when bonds are sold.&#x20;

_SDABackingStablecoinSwap = assetSupplied_&#x20;

For reserve assets such as the DAI swap, SDA Backing simply equals to the amount of the underlying asset supplied by the swapper.

_SDABackingStablecoinlpSwap = 2sqrt (constantProduct) ∗ (% ownership of the pool)_

For LP swaps such as SDA-ETH swap, the SDA Backing is calculated differently because the protocol needs to mark down its value. Why? The LP token pair consists of SDA, and each SDA in circulation will be backed by these LP tokens - there is a cyclical dependency. To safely guarantee all circulating SDA are backed, the protocol marks down the value of these LP tokens marking an expected “loss” on the books.
