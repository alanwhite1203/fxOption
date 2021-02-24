# Understanding Currency Option Pricing

	Overview
A currency option or FX option is a contract that gives the buyer the right, but not the obligation, to buy or sell a certain currency at a specified exchange rate on or before a specified date. Currency options are one of the most common ways for corporations, individuals or financial institutions to hedge against adverse movements in exchange rates. 
A currency option, also known as FX Option, is a derivative contract that grants the buyer the right but not the obligation to exchange money denominated in one currency into another currency at a pre-agreed exchange rate on a specified future date. The FX options market is the deepest, largest and most liquid market for options of any kind. Most FX derivatives trading is over the counter (OTC) and is lightly regulated. 
There are call options and put options. Also a currency option could be European style or American style. Call options provide the holder the right but not the obligation to purchase an underlying currency at a specified FX rate on a future date, while Put options give the holder the right to sell an underlying currency at a specified FX rate on a future date. A European option can be exercised only at the expiration date of the option, whereas an American option can be exercised anytime during its life.
FX options contain Vanilla FX option and Listed FX option. Although both have similar characteristics, they differ mainly in two respects: First, Vanilla options are traded OTC while Listed options are exchanged-traded. Secondly, the underlying of Vanilla options is FX spot while the one of Listed options is FX future. Nevertheless, their analytics are very similar.
Currency options are one of the most common ways for corporations, individuals or financial institutions to hedge against adverse movements in exchange rates. Corporations primarily use FX options to hedge uncertain future cash flows in a foreign currency. The general rule is to hedge certain foreign currency cash flows with forwards, and uncertain foreign cash flows with options.
Options give market participants many opportunities to limit risk and increase profit. Investors buy calls when they think the FX rate will rise or sell a call if they think it will fall. Selling an option is also referred to as ''writing'' an option. On the other hand, they buy puts if they think the FX rate will fall, or sell one if they think it will rise.
One of the most common reasons for using FX options is for short-term hedges of spot FX or foreign market positions. Unlike a forward contract that locks in the FX rate for a future transaction, FX options allow the investors to benefit from favorable FX rate movements. Currency market fluctuations can have a lasting impact on cash flow whether it is buying a property, paying salaries, making an investment or settling invoices. By utilizing FX Options, business can protect themselves against adverse movements in exchange rates.
FX Options are also useful tools which can be easily combined with Spot and Forward contracts to create bespoke hedging strategies. There are many bullish, bearish and even neutral strategies that can be implemented with options contracts. Spread strategies that are used in equity options can also be used with FX options, including vertical spreads, straddles, condors and butterflies. This presentation gives an overview of FX option definition and pricing model. 

	FX Option Introduction
	A currency option is a derivative contract that grants the buyer the right but not the obligation to exchange money denominated in one currency into another currency at a pre-agreed exchange rate on a specified future date.
	The FX options market is the deepest, largest and most liquid market for options of any kind. 
	Most trading is over the counter (OTC) and is lightly regulated.
	There are call options and put options. Also a currency option could be European style or American style.
	Call options provide the holder the right but not the obligation to purchase an underlying currency at a specified FX rate on a future date.
	Put options give the holder the right to sell an underlying currency at a specified FX rate on a future date.
	A European option can be exercised only at the expiration date of the option.
	An American option can be exercised anytime during its life.
	FX options contain Vanilla FX option and Listed FX option. Although both have similar characteristics, they differ mainly in two respects: First, Vanilla options are traded OTC while Listed options are exchanged-traded. Secondly, the underlying of Vanilla options is FX spot while the one of Listed options is FX future. Nevertheless, their analytics are very similar.


	The Use of FX Options
	Currency options are one of the most common ways for corporations, individuals or financial institutions to hedge against adverse movements in exchange rates.

	Corporations primarily use FX options to hedge uncertain future cash flows in a foreign currency. The general rule is to hedge certain foreign currency cash flows with forwards, and uncertain foreign cash flows with options.
	Options give market participants many opportunities to limit risk and increase profit. 
	Investors buy calls when they think the FX rate will rise or sell a call if they think it will fall. Selling an option is also referred to as ''writing'' an option.
	Investors buy puts if they think the FX rate will fall, or sell one if they think it will rise.
	One of the most common reasons for using FX options is for short-term hedges of spot FX or foreign market positions. Unlike a forward contract that locks in the FX rate for a future transaction, FX options allow the investors to benefit from favorable FX rate movements.
	Currency market fluctuations can have a lasting impact on cash flow whether it is buying a property, paying salaries, making an investment or settling invoices. By utilising FX Options, business can protect themselves against adverse movements in exchange rates.
	FX Options are also useful tools which can be easily combined with Spot and Forward contracts to create bespoke hedging strategies.
	There are many bullish, bearish and even neutral strategies that can be implemented with options contracts. Spread strategies that are used in equity options can also be used with FX options, including vertical spreads, straddles, condors and butterflies.

3. 	Payoffs

	The payoff of a European call option

Payoff=N_b*max(X-K,0)
where 
Nb 	the notional of the base currency
X	the spot FX rate
K 	the strike.

	The payoff diagram of a European call option


 

	The payoff of a European put option

Payoff=N_b*max(K-X,0)
where 
Nb – the notional of the base currency
X – the spot FX rate
K – the strike

	Payoff diagram of a European put option

 

	Valuation
European FX Option
The present value of a European call option is given by

 PV(t)=[X_0 e^(-r_q (T_d-T_s ) ) Φ(d_1 )-Ke^(-r_b (T_d-T_s ) ) Φ(d_2)]
where
	d_1,2=[ln(X_0⁄K)+r_b (T_d-T_s )-r_q (T_d-T_s)±σ^2 (T_e-t)]⁄(σ√(T_e-t))
	t 	the valuation date
	X_0 	the spot FX rate quoted as base/quote
	K 	the strike using the same quotation as the spot rate
	T_s 	the spot date (several days after valuation date)
	T_d 	the option delivery date
	T_e 	the option expiry date
	r_b 	the base currency interest rate for period (T_s, T_d)
	r_q 	the quote currency interest rate for period (T_s, T_d)
	σ 	the volatility corresponding to K and (T_e-t)
	Φ 	the cumulative standard normal distribution function

The present value of a European put option is given by

 PV(t)=[Ke^(-r_b (T_d-T_s ) ) Φ(-d_2 )-X_0 e^(-r_q (T_d-T_s ) ) Φ(-d_1 )]

where all notations are the same as above

American FX Option
FinPricing is using the Odd-Even Cox Ross Binomial model to compute prices and risk sensitivities for American-style FX OTC options. 

The Odd-Even Binomial model is an extension of the Cox Ross Binomial model. Compared to Cox Ross Binomial model, the Odd-Even Binomial model provides better price accuracy. It was implemented by creating two tress, one with even number n of iterations and another with n+1 number of iterations, then taking the average of the two results. This method also helps to reduce the number of oscillations that can be observed with traditional Binomial models, where the option value depends quite heavily on the number of periods. 

	Practical Notes
	Anyone new to the FX market needs to understand the forex market conventions first. <a href=”/lib/FxFuture.html”>See details</a>
	Please note the time differences in (1) and (2), which is an important factor in order to apply the Black formula to the FX market. Usually the delivery date is different from the expiry date.
	First, you need to construct interest rate zero curves for both base and quote currencies.
The curve construction in FX world is different from the one in interest rate world. <> provides useful tools to contruct various curves and volatility surfaces.
	Second, you need to construct an arbitrage-free volatility surface. <> is using Vanna Volga model to construct FX volatility surface.
	After that, you can use formula (1) or (2) to calculate the fair value.


	A Real World Example
Reporting Currency	USD
Base Currency	USD
Base Currency Notional	1790000
Underlying Currency	JPY
Underlying Currency Notional	200000000
Trade Date	11/23/2016
Maturity Date	6/9/2017
Settlement Date	6/9/2017
Underlying Future Label	JUN 17
Call or Put	Put
Buy or Sell	Buy
Strike Quotation	USD/JPY
Strike Value	0.895
Instrument	CME JPYUSD


You can find more details at
https://finpricing.com/knowledge.html
