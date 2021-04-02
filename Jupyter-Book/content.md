# Technical Description
 
In choosing whether to enter or leave the workforce or how many hours to work, individuals respond to incentives that are partly determined by the tax code. Taxes can influence an individual's willingness to work through the “substitution effect” and the “income effect.” The substitution effect occurs when an increase in the after-tax wage rate -- due to a tax cut that reduces marginal tax rates -- increases the attractiveness of work relative to leisure. The income effect occurs when an increase in after-tax income, such as from a tax cut that reduces average tax rates, increases an individual’s ability to consume more.

The marginal tax rate is the ratio of additional tax paid on additional income, and it measures the degree to which taxes affect incentives. The average tax rate is the total tax paid divided by total income. Average tax rates measure how taxes affect an individual's ability to consume. 

The child tax credit (CTC) influences effective marginal tax rates (EMTRs) through phase-ins and phaseouts of benefits. The phase-in for low-income households increases both the incentive to enter the labor force and increase hours worked. The phaseout for low- and middle-income households reduces the incentive to work additional hours.

The American Rescue Plan Act [(ARPA)](https://www.congress.gov/bill/117th-congress/house-bill/1319/text) temporarily expanded the child tax credit (CTC) for 2021 by allowing households to claim up to \$3,600 for each child under age six and \$3,000 for each child age six to seventeen. The credit was also made fully refundable and advanceable. 

We first estimate the effect of the tax policy change using [Tax-Calculator](https://github.com/PSLmodels/Tax-Calculator), an open-source microsimulation model of the federal individual income and payroll tax. Then, we estimate labor supply changes using a modified [method](https://www.cbo.gov/publication/43674) employed by the Congressional Budget Office (CBO). 


## Estimating ARPA's Distributional Effects


```{note}
The following estimates are derived from Tax-Calculator 3.1.0 with custom modifications to model the American Rescue Plan Act (H.R. 1319). Baseline is the law currently in place as of March 10, 2021, and the American Rescue Plan Act's CTC reform is assumed effective January 1, 2021.
```

Using a representative sample of tax filing units from the IRS-SOI PUF, we estimate total filers, total labor earnings, the effective marginal tax rate on labor income (including both the income and payroll tax), and the average effective tax rate (AETR) on all income (including both the income and payroll tax) for each income decile. 

The microsimulation estimates are shown in the tables, below.

**Table 1. Distributional Estimates of Selected Parameters (Baseline)**

| Expanded Income Decile | Total Filers (millions) | Labor Earnings (billions) | EMTR on Labor Income (%) | AETR on All Income (%) |
|-|-|-|-|-|
| 0-10   |       13.14  |            23.94     | 6.7%  | 5.5% |
| 10-20  |       17.98  |            93.03     | 4.5%  | 0.0% |
| 20-30  |       17.98  |            158.50    | 9.6%  | -0.6% |
| 30-40  |       17.98  |            245.74    | 14.9% | 4.3% |
| 40-50  |       17.98  |            364.24    | 18.7% | 9.0% |
| 50-60  |       17.98  |            495.48    | 20.1% | 12.8% |
| 60-70  |       17.98  |            680.98    | 22.5% | 16.6% |
| 70-80  |       17.98  |            987.57    | 23.9% | 20.4% |
| 80-90  |       17.98  |            1,589.31  | 27.2% | 24.3% |
| 90-100 |       17.98  |            3,801.87  | 29.0% | 31.9% |
| *Source:* Authors' |  |  | |  |

**Table 2. Distributional Estimates of Selected Parameters (Reform -- ARPA's CTC Expansion)**
| Expanded Income Decile | Total Filers (millions) | Labor Earnings (billions) | EMTR on Labor Income (%) | AETR on All Income (%) |
|-|-|-|-|-|
| 0-10   |       13.14  |            23.94     | 7.2%  | -6.5% |
| 10-20  |       17.98  |            93.03     | 6.2%  | -5.9% |
| 20-30  |       17.98  |            158.50    | 11.4% | -5.6% |
| 30-40  |       17.98  |            245.74    | 16.9% | 1.2% |
| 40-50  |       17.98  |            364.24    | 19.9% | 7.1% |
| 50-60  |       17.98  |            495.48    | 20.4% | 11.5% |
| 60-70  |       17.98  |            680.98    | 22.6% | 15.7% |
| 70-80  |       17.98  |            987.57    | 23.9% | 19.6% |
| 80-90  |       17.98  |            1,589.31  | 27.3% | 23.6% |
| 90-100 |       17.98  |            3,801.87  | 29.5% | 31.8% |
| *Source:* Authors' |  |  | |  |


## Estimating the Labor Supply Response

To estimate how much the labor supply would change in response to a permanent expansion of the American Rescue Plan's CTC we use a modified method employed by the Congressional Budget Office (CBO). This method starts with the average and marginal tax rate changes for each income decile from our microsimulation model and calculates the long-term labor supply response based on estimates of substitution and income elasticities. For more details on CBO's model, see [this](https://www.cbo.gov/publication/43674) report. We then compute the earnings-weighted average percent change in labor supply across all workers and estimate the total change in hours worked. Using [current U.S. average hourly earnings](https://www.bls.gov/news.release/empsit.t19.htm) (for all employees on private nonfarm payrolls, seasonally adjusted -- Feb 2021) and [total U.S. 2021 wages and salaries](https://www.cbo.gov/system/files/2021-02/51135-2021-02-economicprojections.xlsx) (from CBO's 10-Year Economic Projections -- Feb 2021), we convert that estimate into full-time equivalent jobs lost/gained. 

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


Substitution and income elasticities are measured with respect to after-tax wage rates. The after-tax wage rate represents the percentage of earnings a worker receives after taxes, $W = (1-t)$, where $W$ is the after-tax wage rate and $t$ is the tax rate. When $t$ is the marginal effective tax rate, $W$ is the after-tax marginal wage rate, $W_{M}$, and when $t$ is the average effective tax rate, $W$ is the after-tax average wage rate, $W_{A}$. 

The percentage change in the after-tax marginal wage rate and after-tax average wage rate, $\Delta W_{M,A} = \left(\frac{W_{reform}}{W_{base}}\right)$, can be multiplied by the substitution and income elasticities, respectively, to estimate each effect's percentage change in the labor supply. $ L_{M} = (\Delta W_{M} * \epsilon) $ is the labor supply response resulting from the substitution effect and $ L_{A} = (\Delta W_{A} * \eta)$ is the labor supply response resulting from the income effect, where $\epsilon$ is the substitution elasticity and $\eta$ is the income elasticity.

The earnings-weighted average percent change in labor supply across all workers, $ L^* $, is 

$L^* = \displaystyle\frac{\sum\limits_{i=1}^{10} w_{i} L_{M_i}}{\sum\limits_{i=1}^{10} w_i} + \frac{\sum\limits_{i=1}^{10} w_{i} L_{A_i}}{\sum\limits_{i=1}^{10} w_i}$ , 

where $w_i$ is total labor income for each income decile $i$. 

Total full-time equivalent jobs lost or gained, $J$, is 

$J = \displaystyle\frac{L^* * \left(\frac{C}{E}\right)}{A}$, 

where $C$ is total U.S. wages and salaries, $E$ is current average U.S. hourly earnings, and $A$ is average annual full-time hours for a single employee.


## Summary of Results

According to our calculation, using the above methodology, the likely impact of a permanent expansion of the American Rescue Plan’s CTC on employment will be 296,000 full-time equivalent jobs lost (+/- 155,000).

**Table 5. Full Time Equivalent Jobs (Thousands)**
|                                       | **Lower Estimate** | **Central Estimate** | **Higher Estimate** |
|---------------------------------------|----------------|------------------|-----------------|
| Substitution Effect                   | -140.6         | -221.0           | -299.9          |
| Income Effect                         | 0.0            | -74.9            | -149.8          |
| **Total**                             | **-140.6**     | **-295.9**       | **-449.8**      |
| *Source:* Authors' |  |  |  |


