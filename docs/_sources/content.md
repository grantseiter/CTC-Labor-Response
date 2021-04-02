# Technical Description
 
Taxes can impact an individual’s willingness to enter the labor force and how many hours they choose to work through the “substitution effect” and the “income effect.” 

The substitution effect impacts work by influencing the attractiveness of work relative to leisure. The relative attractiveness of work and leisure is influenced by marginal effective tax rates. The marginal tax rate is the ratio of additional tax paid on additional income earned.


The income effect influences a household's ability to consume goods and services, including leisure. The income effect is influenced by the after-tax income of an individual and is determined by the average tax rate. The average tax rate is the total tax paid divided by total income. 

The child tax credit (CTC) impacts both effective marginal tax rates and average tax rates. The CTC both increases and decreases marginal tax rates through phase-ins and phaseouts of benefits. The CTC decreases after-tax rates and increases after-tax income by providing additional resources to households with children.

The American Rescue Plan Act [(ARPA)](https://www.congress.gov/bill/117th-congress/house-bill/1319/text) temporarily expanded the child tax credit (CTC) for 2021 by allowing households to claim up to \$3,600 for each child under age six and \$3,000 for each child age six to seventeen. The credit was also made fully refundable and advanceable. 

We first estimated the effect of the tax policy change using [Tax-Calculator](https://github.com/PSLmodels/Tax-Calculator), an open-source microsimulation model of the federal individual income and payroll tax. Then, we estimated labor supply changes using a [method](https://www.cbo.gov/publication/43674) similar to the one employed by the Congressional Budget Office (CBO). 


## Estimating Marginal and Average Tax Rates


```{note}
The following estimates are derived from Tax-Calculator 3.1.0 with custom modifications to model the American Rescue Plan Act (H.R. 1319). Baseline is the law currently in place as of March 10, 2021, and the American Rescue Plan Act's CTC reform is assumed effective January 1, 2021.
```

Using a representative sample of tax filing units from the IRS-SOI PUF, we estimate share of total labor earnings, the effective marginal tax rate on labor income (including both the income and payroll tax), and the average effective tax rate (AETR) on all income (including both the income and payroll tax) for each income decile. 

The microsimulation estimates are shown in the tables, below.

**Table 1. Distributional Estimates of Selected Parameters (Baseline)**

| Expanded Income Decile | Total Filers (millions) | Share of Labor Earnings (%) | EMTR on Labor Income (%) | AETR on All Income (%) |
|-|-|-|-|-|
| 0-10   |       13.14  | 0.3% | 6.7%  | 5.5% |
| 10-20  |       17.98  | 1.1% | 4.5%  | 0.0% |
| 20-30  |       17.98  | 1.9% | 9.6%  | -0.6% |
| 30-40  |       17.98  | 2.9% | 14.9% | 4.3% |
| 40-50  |       17.98  | 4.3% | 18.7% | 9.0% |
| 50-60  |       17.98  | 5.9% | 20.1% | 12.8% |
| 60-70  |       17.98  | 8.0% | 22.5% | 16.6% |
| 70-80  |       17.98  | 11.7%| 23.9% | 20.4% |
| 80-90  |       17.98  | 18.8%| 27.2% | 24.3% |
| 90-100 |       17.98  | 44.9%| 29.0% | 31.9% |
| *Source:* Authors' |  |  | |  |

**Table 2. Distributional Estimates of Selected Parameters (Reform -- ARPA's CTC Expansion)**
| Expanded Income Decile | Total Filers (millions) | Share of Labor Earnings (%) | EMTR on Labor Income (%) | AETR on All Income (%) |
|-|-|-|-|-|
| 0-10   |       13.14  | 0.3% | 7.2%  | -6.5% |
| 10-20  |       17.98  | 1.1% | 6.2%  | -5.9% |
| 20-30  |       17.98  | 1.9% | 11.4% | -5.6% |
| 30-40  |       17.98  | 2.9% | 16.9% | 1.2% |
| 40-50  |       17.98  | 4.3% | 19.9% | 7.1% |
| 50-60  |       17.98  | 5.9% | 20.4% | 11.5% |
| 60-70  |       17.98  | 8.0% | 22.6% | 15.7% |
| 70-80  |       17.98  | 11.7%| 23.9% | 19.6% |
| 80-90  |       17.98  | 18.8%| 27.3% | 23.6% |
| 90-100 |       17.98  | 44.9%| 29.5% | 31.8% |
| *Source:* Authors' |  |  | |  |


## Estimating the Labor Supply Response

To estimate how much the labor supply would change in response to a permanent expansion of the American Rescue Plan's CTC we use a method similar to the one employed by the Congressional Budget Office (CBO). This method starts with the average and marginal tax rate changes for each income decile from our microsimulation model and calculates the long-term labor supply response based on estimates of substitution and income elasticities for each income decile. We then compute the earnings-weighted average percent change in labor supply across all households and estimate the total change in hours worked. 

Then, using [current U.S. average hourly earnings](https://www.bls.gov/news.release/empsit.t19.htm) (for all employees on private nonfarm payrolls, seasonally adjusted -- Feb 2021) and [total U.S. 2021 wages and salaries](https://www.cbo.gov/system/files/2021-02/51135-2021-02-economicprojections.xlsx) (from CBO's 10-Year Economic Projections -- Feb 2021), we convert the earnings-weighted average percent change in hours worked into full-time equivalent jobs lost/gained. 

CBO uses a range of substitution and income elasticities (lower, central, and higher estimates) that vary by earnings level (as shown in Tables 3 and 4 below). For a detailed discussion of how CBO determined its range of elasticity estimates, see Robert McClelland and Shannon Mok, [*A Review of Recent Research on Labor Supply Elasticities*](https://www.cbo.gov/publication/43675), CBO Working Paper 2012-12 (October 2012).

**Table 3. Substitution Elasticities**
| **Income Decile**                                            | **Lower Estimate**| **Central Estimate** | **Higher Estimate** |
|---------------------------------------------------------------|----------------|------------------|-----------------|
| 0-10%                                                      | 0.15           | 0.31             | 0.47            |
| 10-20%                                                     | 0.15           | 0.28             | 0.42            |
| 30-40%                                                     | 0.15           | 0.27             | 0.38            |
| 40-50%                                                     | 0.15           | 0.27             | 0.38            |
| 50-60%                                                     | 0.15           | 0.25             | 0.35            |
| 60-70%                                                     | 0.15           | 0.25             | 0.35            |
| 70-80%                                                     | 0.15           | 0.22             | 0.29            |
| 80-90%                                                     | 0.15           | 0.22             | 0.29            |
| 90-100%                                                    | 0.15           | 0.22             | 0.29            |
| *Source:* [Congressional Budget Office](https://www.cbo.gov/sites/default/files/112th-congress-2011-2012/reports/43674-laborsupplyfiscalpolicy.pdf)||||

**Table 4. Income Elasticities**
|                                             				    | **Lower Estimate**| **Central Estimate** | **Higher Estimate** |
|---------------------------------------------------------------|----------------|------------------|-----------------|
| All Earners                                                | -0.1           | -0.05            | 0.0               |
| *Source:* [Congressional Budget Office](https://www.cbo.gov/sites/default/files/112th-congress-2011-2012/reports/43674-laborsupplyfiscalpolicy.pdf)||||


## Summary of Results

Using the above methodology, we found that the likely impact of a permanent expansion of the American Rescue Plan’s CTC on employment will be 296,000 full-time equivalent jobs lost (+/- 155,000).

**Table 5. Full Time Equivalent Jobs (Thousands)**
|                                       | **Lower Estimate** | **Central Estimate** | **Higher Estimate** |
|---------------------------------------|----------------|------------------|-----------------|
| Substitution Effect                   | -140.6         | -221.0           | -299.9          |
| Income Effect                         | 0.0            | -74.9            | -149.8          |
| **Total**                             | **-140.6**     | **-295.9**       | **-449.8**      |
| *Source:* Authors' |  |  |  |


