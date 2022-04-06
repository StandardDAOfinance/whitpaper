# Protocol Mechanics

## SDA is backed, not pegged

Similar to OHM, each SDA is backed by 1 DAI, not pegged to it. Because the treasury backs every SDA with at least 1 DAI, the protocol would buy back and burn SDA in the event it trades below 1 DAI. This has the effect of pushing SDA price back up to 1 DAI. SDA could always trade above 1 DAI because there is no upper limit imposed by the protocol. Think pegged == 1, while backed >= 1. Intrinsic value of SDA is 1 DAI based on the contract. In reality, it becomes 1 DAI + premium as the treasury grows in assets.

## Autostake swaps

Standard uses the same mechanics as Olympus with a simple tweak on the swapping mechanism. During the swapping process for all assets sold to the treasury, swappers receive staked SDA or sSDA coins automatically giving the ability to compound yield without paying fees each day a portion of the swap reward is released. This provides greater benefits to swappers over the course of their term as well as the protocol since liquidity is automatically staked over the five days providing greater stability for token price.

## Initial Network State

Our goal is to provide a robust foundation for SDA token by building a diverse and performing treasury of Standard Assets. This should theoretically drive the price of the SDA token correlated to the growth of the treasury assets. Growth of the treasury will be dependent upon partnerships, marketing, and continued development of novel industry solutions with SDA at the center. The vision for SDA is to build a diverse ecosystem with incentives for bonding and staking at the center to increase treasury holdings and decrease volatility from selling.

### Alpha State

The initial network features a one-way treasury (money goes in, none comes out), the swapping contract (through which supply increases and profits are produced), and the staking contract (where profits are distributed).

#### **SCV**

SCV varies based on swap types. It is tuned regularly by the Policy team to meet the protocol goals. For example, if the protocol wants to accumulate more liquidity into its treasury, it can lower the SCV for liquidity swaps to increase their swap capacity.

#### Swap vesting term

Approximately 5 days for all swap types.

#### SDA distribution

Every time someone purchases a swap, the proceeds will go to the Standard treasury. A corresponding amount of SDA will be minted and distributed to three parties:&#x20;

* Swapper: The swap purchaser will receive the quoted amount of SDA in the form of sSDA linearly over the vesting term.&#x20;
* DAO: The DAO receives the same amount of SDA as the swapper. This represents the DAO profit.&#x20;
* Stakers: After accounting for the SDA distributed to the swapper and the DAO, the rest will be distributed among all stakers in the protocol.

## Policy

Standard features policy constants that allow us to optimize the system.

#### Swaps

The [SCV ](https://docs.standarddao.finance/protocol/definitions#scv)allows us to scale the rate at which swap premiums increase. A higher SCV means a lower discount for swappers and more protocol profit. A lower SCV means a higher discount for swappers and less protocol profit.&#x20;

The vesting term determines how long it takes for swaps to become fully redeemable. A longer term means lower inflation and lower swap demand. Providing automated staking provides swappers more yield over the 5 day term in an effort to increase swap demand and retention.

#### **Sales**

The [DCV ](https://docs.standarddao.finance/protocol/definitions#dcv)allows us to scale protocol buy pressure up or down. A higher DCV means more buy pressure and higher deflation. A lower DCV means less buy pressure and a weaker floor.

#### **Treasury**

Profit Allocations are the only treasury variable. This allows us to choose who receives profits from the protocol.

#### Staking

There are no variables in the staking contract. SDA and sSDA are always redeemable 1:1, and profits are always distributed equally through rebase.

## Market Dynamics

There are several feedback mechanisms within the system. These are self-reinforcing behaviors; action 1 increases the rate of action 2 which increases the rate of action 1. Circular mechanics like this are the drivers of exponential expansion and boom and bust cycles. Loose policy states enable these dynamics while tight policy states suppress them. The goal of Standard is to maximize both token growth and stabilized yield for stakers to enable the greatest liquidity for the protocol.
