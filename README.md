# general_dynamics_roa_profit_driver_analysis
This repository contains the original excel documents, analyzed excel documents with Excel formulas and data visualizations, and a README file that summarizes findings from a ROA profit driver analysis performed for General Dynamics Corporation.

# General Dynamics Corporation ROA Profit Driver Analysis

## Background
[General Dynamics](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&cad=rja&uact=8&ved=2ahUKEwi2nMG--ZbvAhX9FVkFHRepA7EQFjAAegQIARAE&url=https%3A%2F%2Fwww.gd.com%2F&usg=AOvVaw3vakUBl6fNkvrTiR11h_hT) is a global aerospace and defense company that offers a broad portfolio of innovative products and services in business aviation, combat vehicles, weapons systems, and munitions. With a market capitalization of $46.81B and gross revenues of nearly $38B in 2020, the company is the fifth-largest defense contractor in the U.S., and the sixth-largest in the world, by sales. 

According to [General Dynamics' 2021 form 10-k report](https://investorrelations.gd.com/financial-reports/sec-filings/sec-filings-details/default.aspx?FilingId=14683590), the company has invested nearly $20 billion to "create, renew or expand our portfolio of products and services across our businesses to drive long-term growth and shareholder value creation." Thus, in addition to seeking short-term profits through a low-cost strategy which relies on efficient management of accounts receivable, inventory, and productive assets to produce high asset turnover, the corporation has pursued long-term value creation through a high-value, product-differentiation strategy which trades on R&D and product promotion to convince customers of the superiority and distinctiveness of their products.

Return on asset profit driver analysis (also called ROA decomposition or DuPont analysis) breaks down return on assets into two profit levers: profitability and efficiency, each of which describes a different way management can improve ROA. ROA profit driver analysis involves the computation of key ratios and evaluating trends in order to gain insights into a company's performance over time. The DuPont model may also provide a useful analytical framework in which to recalibrate or revise a company's business strategy. What factors have contributed most to General Dynamics' growth over the past two decades? What impact do profitability, efficiency, and financial leverage have on its net operating income? Can we develop an equation to predict General Dynamics' net income based on its ROA and financial leverage ratio? We’ll take a look at open data from the company's financial statements, as well as data obtained from Federal Reserve Economic Data (FRED) database, to explore answers to these questions and see whether we can glean any additional insights into the corporation's performance based on changes in macro-level trends such as the effective federal funds rate and national defense consumption expenditures and investment. 

## Business Question

_**What is the relationship between General Dynamics' net income and key financial ratios such as net profit margin, total asset turnover, return on assets, and financial leverage?**_

## Data Question - Open Data

We'l use open data from two sources: 

1. **Federal Reserve Economic Data (FRED)**: this database produces high-quality original research in the areas of macroeconomics, money and banking, and applied microeconomics and aggregates over 750,000 financial and economic data series from more than 100 public and proprietary sources. We will use four datasets from this source:
   1. [Gross Domestic Product, Billions of Dollars, Annual, Seasonally Adjusted Annual Rate](https://fred.stlouisfed.org/series/GDP): this dataset displays economic output, reported as the nominal value of all new goods and services produced by labor and property located in the U.S.
   2. [Real government consumption expenditures and gross investment: Federal: National defense](https://fred.stlouisfed.org/series/A824RX1Q020SBEA) \(mrc\_table02\): this dataset summarizes real government national defense consumption expenditures and gross investment. The data are adjusted for inflation and expressed in units of billions of chained 2012 dollars.
   3. [Effective Federal Funds Rate](https://fred.stlouisfed.org/series/EFFR): this dataset contains historical data on the Effective Federal Funds Rate, the interest rate depository institutions charge each other for overnight loans of funds.
2. **General Dynamics Investor Relations**: this website lists resources for external parties (investors, creditors, and lenders) on topics including equity information, financial reports, events, and corporate governance. 
   1. [General Dynamics Form 10-K (2021)](https://investorrelations.gd.com/financial-reports/sec-filings/default.aspx) this dataset provides a comprehensive overview of the company's business and financial condition and includes audited financial statements for the years 2016-2020. 
   2. [General Dynamics Form 10-K (2016)](https://investorrelations.gd.com/financial-reports/sec-filings/default.aspx): this dataset provides a comprehensive overview of the company's business and financial condition and includes audited financial statements for the years 2014-2015. 
   3. [General Dynamics Form 10-K (2014)](https://investorrelations.gd.com/financial-reports/sec-filings/default.aspx): this dataset provides a comprehensive overview of the company's business and financial condition and includes audited financial statements for the years 2009-2013. 
   4. [General Dynamics Form 10-K (2009)](https://investorrelations.gd.com/financial-reports/sec-filings/default.aspx): this dataset provides a comprehensive overview of the company's business and financial condition and includes audited financial statements for the years 2006-2008. 

## Data Question - Analysis

We’ll use Microsoft Excel to answer:

* **What were the net profit margin, total asset turnover, return on assets, financial leverage ratio, and return on equity for General Dynamics Corporation from 2006-2020?**
* **Is there evidence of a linear relationship between net income and the above profit drivers? Which ratio has the greatest explanatory power?** 
* **What additional insights can we gain about General Dynamics' performance from changes in exogenous, macro-level conditions such as the federal funds rate, GDP, and national defense consumption expenditures and investment?** 

## Data Answer

We can use simple and multiple linear regression analysis to model the relationship between General Dynamics' net income and the aforementioned variables and make predictions about net income based on known or estimated values for the independent variables. 

#### What were the net profit margin, total asset turnover, return on assets, financial leverage ratio, and return on equity for General Dynamics Corporation from 2006-2020?

![fin_ratios](https://user-images.githubusercontent.com/78438582/110003452-655e5200-7ce4-11eb-934a-51c565b16614.png)

Here we can see that two-year public and private higher education institutions make up most of the volume of colleges in the US, followed by "selective private" and "selective public" schools. As we might expect, there are very few "Ivy Plus" schools \(highly selective and highly ranked\), "other elite" schools \(including Johns Hopkins\), and "highly selective" public and private schools \(perhaps less than one per state\). This gives us an idea of the type of quantitative impact that education or admissions reform might have based on what type of institutions the reform focuses on.

#### Is there evidence of a linear relationship between net income and the above profit drivers? Which ratio has the greatest explanatory power?

![](.gitbook/assets/final-chart.png)

Here we see almost an opposite type of distribution--the highly selective private schools have the highest sticker price, and the two-year not-for-profit institutions have the lowest sticker price. We should also note that the sticker price also does not necessarily reflect the price that students need to pay to attend the institution, however, it can give us insight into the type of students who attend those schools and who don't receive financial aid. Additionally, highly selective public schools have a significantly lower sticker price than their peer institutions, so this may indicate that students could get a better "bang for their buck" here if the student outcomes are similar to peer institutions. 

#### What additional insights can we gain about General Dynamics' performance from changes in exogenous, macro-level conditions such as the federal funds rate, GDP, and national defense consumption expenditures and investment?

![](.gitbook/assets/parent_income_dist_by_tier.png)

We can also look at the average income distribution at the different higher education tiers where Q1 indicates families in the lowest income quintile and Q5 indicates families in the highest income quintile. We can see that the income distribution starts to even out when we look at nonselective four-year colleges and that elite and other highly selective institutions are predominantly filled with students from the highest income quintile.


## Business Answer
