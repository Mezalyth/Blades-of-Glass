---
draft: true
tags:
  - wgu
  - schoolwork
---
## Finance Basics
- Finance is the term for analytics that support decision-making
- Finance should always serve your strategic imperatives
- The goal is to have benefits outweigh costs
- **Utility** is an economic term referring to the total satisfaction received from consuming goods and services.

## 3 economic indicators

### Leading
**Yield Curve**
- Normal - longer maturity bonds have higher interest rates than shorter ones. (growing)
- Inverted - longer-term bonds have a lower interest rate than shorter-term bonds (economic downturn)
- Flat - same (transitional state)
**Stock Market Return**

### Lagging

**Unemployment Rate**
**Consumer Price Index** - Rate of inflation

### Coincidental
**Gross Domestic Product** - Value of all finished goods in a nation
**Personal Income**

## Fundamental Finance Principles

**MAIN QUESTION: DO BENEFITS OUTWEIGH COSTS?**

### Types of Interest
**SIMPLE INTEREST RATE**
Annual Interest = Principal × Interest Rate

**find the total interest amount using simple interest for t years:**
Total Interest = Annual Interest × t(years)

**COMPOUNDING INTEREST RATE**
Total Interest = Principal(1+Interest Rate)^Number of Periods − Principal

#### Components of Req'd Rate of Return (Interest)
1. Opportunity Cost
2. Risk
3. Inflation

#### Inflation Causes
1. Increased demand for goods/services
2. Rising costs
3. Adaptive expectations

**REAL RATE = NOMINAL RATE - INFLATION**

### TVM Variables in Excel

| Input Table       |                                                                                                                                                                                                                                                                                                                                                               |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Variable          | Description                                                                                                                                                                                                                                                                                                                                                   |
| rate              | Interest rate per period                                                                                                                                                                                                                                                                                                                                      |
| nper              | Number of payment periods in an annuity                                                                                                                                                                                                                                                                                                                       |
| pmt               | Payment made each period                                                                                                                                                                                                                                                                                                                                      |
| pv                | Present value, or the lump-sum amount that a series of future payments is worth right now                                                                                                                                                                                                                                                                     |
| fv                | Future value, or the cash balance you want to attain after the last payment is made                                                                                                                                                                                                                                                                           |
| type              | Type of annuity—0 indicates an ordinary annuity; 1 indicates an annuity due. The default is ordinary annuity if you do not enter 0 or 1.                                                                                                                                                                                                                      |
| value1,[value2],… | value1 is the given first payment one period from today; value2 is the second payment one period after value1. Each payment must be equally spaced in time and occur at the end of each period. You can separate those payments with commas and enter them in order, or input each period’s payment next to one another in a row and highlight them together. |
| values            | An array or reference to cells that contain numbers for which you want to calculate the internal rate of return                                                                                                                                                                                                                                               |
### TVM Functions in Excel

|Output Table|   |
|---|---|
|Function|Description|
|=RATE(nper,pmt,pv,[fv],[type],[guess])|Returns the interest rate per period|
|=NPER(rate,pmt,pv,[fv],[type])|Returns the number of payment periods in an annuity|
|=PMT(rate,nper,pv,[fv],[type])|Returns the payment made each period (this has to be an annuity)|
|=PV(rate,nper,pmt,[fv],[type])|Returns the present value, or the lump-sum amount that a series of future payments is worth right now|
|=FV(rate,nper,pmt,[pv],[type])|Returns the future value, or the cash balance you want to attain after the last payment is made|
|=NPV(rate,value1,[value2],…)|Returns the net present value of a series of future payments with a given rate|
|=IRR(values,[guess])|Returns the internal rate of return of a series of future payments|
### Ratios in Finance
**Liquidity**
Ability to meet short term obligations without raising external capital

**Activity**
AKA Efficiency. How well a co. can generate sales/cash

**Leverage**
Financing/solvency. How the firm is financed.

**Profitability**
Based on sales or investment. How well management is maximizing shareholder wealth

**Market**
Determines if stock value is under or overvalued

