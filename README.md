# general_dynamics_roa_profit_driver_analysis
This repository contains the original excel documents, analyzed excel documents with Excel formulas and data visualizations, and a README file that summarizes findings from a ROA profit driver analysis performed for General Dynamics Corporation. It also contains a copy of the Google Colaboratory notebook used to re-create the data exploration analysis and data visualizations using Python.



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

We’ll use Microsoft Excel and Python to answer:

* **What were the net profit margin, total asset turnover, return on assets, financial leverage ratio, and return on equity for General Dynamics Corporation from 2006-2020?**
* **Is there evidence of a linear relationship between net income and the above profit drivers? Which ratio has the greatest explanatory power?** 
* **What additional insights can we gain about General Dynamics' performance from changes in exogenous, macro-level conditions such as the federal funds rate, GDP, and national defense consumption expenditures and investment?** 

## Data Answer

We can use simple and multiple linear regression analysis to model the relationship between General Dynamics' net income and the aforementioned variables and make predictions about net income based on known or estimated values for the independent variables. 

#### What were the net profit margin, total asset turnover, return on assets, financial leverage ratio, and return on equity for General Dynamics Corporation from 2006-2020?

![fin_ratios](https://user-images.githubusercontent.com/78438582/110003452-655e5200-7ce4-11eb-934a-51c565b16614.png)

The values for net profit margin, total asset turnover, return on assets, financial leverage ratio, and return on equity were calculated as follows:
1. Profitability (net profit margin) = net income / net sales
2. Efficiency (total asset turnover) = net sales / average total assets
3. ROA = net profit margin x total asset turnover
4. Financial leverage = average total assets / average shareholders' equity
5. ROE = ROA x financial leverage

Excel formulas were used to perform the ratio computations for the first row, and the autofill feature was used to extend the formulas to the rest of the dataset. A preliminary overview of the ratios seems to suggest that during the period from 2006-2020, General Dynamics Corporation's profitability increased steadily, its effiency trended down, its ROA alternated between gains and losses, its financial leverage registered significant gains, and its return on equity hovered around its average value of .22.

#### Is there evidence of a linear relationship between net income and the above profit drivers? Which ratio has the greatest explanatory power?

![endogenous_regression1](https://user-images.githubusercontent.com/78438582/110005962-0f3ede00-7ce7-11eb-9c93-c53b3f12e07a.png)

Multiple regression analysis was used to estimate the dependence of net income on profitability, efficiency, ROA, financial leverage, and ROE. In the initial run, the regression output appeared to indicate that none of the independent variables were signficant since each had a p-value greater than .05. However, that none of the independent variables were significant in predicting net income seemed to defy common sense, and contradicted the computed R-squared value of 0.978566511 which indicated that the linear relationship explains 97.86% of the variation in net income.

![multicollinearity](https://user-images.githubusercontent.com/78438582/110006163-5036f280-7ce7-11eb-93a1-df2e98aadfc1.png)

Taking a closer look at the independent variables, it became clear that the regression output had been distorted by multicollinearity, or the occurrence of high intercorrelations among two or more independent variables in a multiple regression model. Multicollinearity among independent variables may result in less reliable statistical inferences, and can be measured using the correlation function in the Data Analysis ToolPak. The issue derived from the fact that several of the ratios were linked by common terms, such as net sales in the equations for both net profit margin and total asset turnover. The cells highlighted in the image above represent potential sources of distortion; to address this issue, the variables with the highest correlation were either dropped or proxied using other independent variables that contained their component parts. ROA and financial leverage, the drivers of ROE, were included in the rerun, and the resulting linear regression produced the regression output below: 

![endogenous_rerun](https://user-images.githubusercontent.com/78438582/110006480-b7ed3d80-7ce7-11eb-9d70-6ccab1ea2c7d.png)

The p-values for ROA and financial leverage indicated that both were significant, and the regression analysis yielded the following equation for net income: net income = -2829.070068 + 16835.31414(ROA) + 1403.078719(financial leverage).

![roa](https://user-images.githubusercontent.com/78438582/110006508-c2a7d280-7ce7-11eb-8a76-9b978409d5fb.png)

![Screen Shot 2021-04-15 at 1 18 19 PM](https://user-images.githubusercontent.com/78438582/114911487-12041700-9ded-11eb-8991-1e8c72040127.png)


The graphs above display the relationship between net income and ROA, while the graphs below depict the relationship between net income and financial leverage. The R-squared value of .9148 for financial leverage suggests that it has strong explanatory power for net income. 

![fin_leverage](https://user-images.githubusercontent.com/78438582/110006519-c89db380-7ce7-11eb-8312-30d2eef71fc4.png)

![Screen Shot 2021-04-15 at 1 18 46 PM](https://user-images.githubusercontent.com/78438582/114911547-1fb99c80-9ded-11eb-9735-a1c9ed06b874.png)

#### What additional insights can we gain about General Dynamics' performance from changes in exogenous, macro-level conditions such as the federal funds rate, GDP, and national defense consumption expenditures and investment?

![exogenous_regression](https://user-images.githubusercontent.com/78438582/110006767-069ad780-7ce8-11eb-86a9-41f266dca0b3.png)

In order to provide a macro-level context for GDC's net income over the time period in question, macroeconomic data from FRED were analyzed for evidence of a linear relationship between net income and GDP, national defense consumption expenditures and investment, and the effective federal funds rate. The regression output above indicated that none of the independent variables were signficant. Moreover, the Significance F value of 0.245799786 in the ANOVA section of the output was insufficient to cause rejection of the null hypothesis, further indicating that the independent variables do not have significant predictive value.

![defense](https://user-images.githubusercontent.com/78438582/110006575-d3584880-7ce7-11eb-8512-004b16b43099.png)

![Screen Shot 2021-04-15 at 1 20 09 PM](https://user-images.githubusercontent.com/78438582/114911760-4f68a480-9ded-11eb-9e58-a355d4c23cac.png)

The graph above depicts the relationship between real government consumption expenditures and gross investment on national defense and net income. The R-squared value of .0006 suggests that the variables do not have a strong linear relationship.

![Screen Shot 2021-04-15 at 1 21 09 PM](https://user-images.githubusercontent.com/78438582/114911958-732bea80-9ded-11eb-802c-3cee67c95ade.png)

Finally, the plotly.express library in Python was used to create the above multi-attribute bubble scatter plot which graphs the relationship between net income, financial leverage, and national defense expenditures and investment. The size of the bubble corresponds to the relative expenditure level in the given year. This  graph allows us to view the relationship and interaction between multiple variables and confirms the weak correlation between defense expenditures and net income. The specific values attached to each data point can be seen by hovering over the data points.

## Data Interpretation - Excel

The linear regression analysis above provides a useful starting point for investigating trends in General Dynamics' Corporation's growth and performance in the period from 2006-2020. The analysis indicated a strong linear relationship between financial leverage and net income, which may have important implications for General Dynamics' long-term business strategy. Interestingly, ROA had substantially less predictive value, with a R-squared value of .1946. These facts seem to indicate that increasing leverage will be essential to continued growth as measured by net income. Moreover, the macro-level analysis seemed to suggest that GDC's net income was not strongly correlated with national defense expenditures and investment, GDP, or the federal funds rate. 

## Data Interpretation - Python

I found that the results of my analysis did not change after recreating the data exploration analysis and data visualizations using Python. Python contributed to this analysis in a number of ways. First, the plotly library equipped me with an incredibly useful tool for producing clean, professional, and dynamic graphs. Plotly's dynamic features allow users to engage with the data at a deeper level by revealing the exact values associated with particular observations. Second, the software architecture I created in Python has provided me with a effective tool to repeat the above analysis at scale. Python enjoys a clear advantage in the analysis of large data sets, and rerunning the same analyses to create new visualizations with much larger data files would require a minimal time investment since the underlying mathematical operations performed on the data would not be changing.

As a higher level program, Excel is more user-friendly than Python in that instructing the software to perform a particular task would require a sequence of commands that are easier to interpret or compile, and developing the code to perform it would probably take longer using Python than Excel. A major drawback to using Excel, however, is its low memory efficiency which, as suggested above, would require longer run times to perform the same tasks with larger data sets.

Based on these findings, General Dynamics should carefully weigh the relative benefits of increasing financial leverage against the risks of taking on more debt. The company should compare its financial ratios to those of other companies in the same industry, review its cost structure, and conduct additional analyses (such as cost-volume-profit analysis) to assess its bandwith for incurring higher levels of debt in order to magnify its gains.


## Step-by-step Instructions for Excel Data Analysis

1. Download GDP, national defense expenditures and spending, and the effective federal funds rate from FRED
2. Extract revenue, total assets, and shareholders' equity data from GDC's form 10-K reports
3. Use ratio analysis formulas to compute net profit margin, total asset turnover, ROA, leverage, and ROE
4. Use Data Analysis ToolPak to run multiple linear regression analysis for net operating income (dependent variable) and net profit margin, total asset turnover, ROA, leverage, and ROE (independent variables)
5. Check for multicollinearity using correlation function in Data Analysis ToolPak
6. Remove variables with high correlation
7. Rerun multiple linear regression analysis
8. Perform multiple linear regression analysis for net operating income (dependent variable) and GDP, national defense consumption expenditures and investment, and the effective federal funds rate (independent variables)
9. Create scatterplots for net income vs. ROA, net income vs. financial leverage, and net income vs. national defense consumption expenditures and investment

## Step-by-step Instructions for Python Data Analysis
1. Import pandas, plotly.express, and io libraries from Python, as well as files from google.colab
2. Upload local file to Google Colaboratory notebook using files.upload() and save to variable "uploaded"
3. Read in data and create dataframe using pd.read_excel function
4. Preview first 5 rows of data using df.head
5. Use plotly to create scatter plots of the relationships between net income and ROA, net income and financial leverage, and net income and national defense spending and expenditures
6. Use plotly to create multi-attribute bubble scatter plot to visualize the interactions between net income, financial leverage and national defense spending and expenditures
