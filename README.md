# Principle Component Analysis for Stock Markets
This project demonstrates the use of PCA (Principal Component Analysis) for analyzing stock market data with Python.

PCA is a technique for reducing multidimensional data to fewer dimensions, simplifying analysis. You can learn more about its mathematical foundations here. This project applies PCA to financial data from the stock market to uncover patterns and insights. <a href="https://en.wikipedia.org/wiki/Principal_component_analysis"> here </a>. With this project I tried to analyse stock market data with PCA decomposition.

# Data
The dataset includes financial ratios from the "Borsa Istanbul 100" (BIST100) stock market index, representing Turkey's top 100 companies. The raw dataset (ticks.raw.csv) contains various financial indicators, including:

Price-to-earnings ratio
Price-to-book value
Debt-to-equity ratio
Here’s a snapshot of the raw data:(ticks.raw.csv):

<img src="https://diwsi.github.io/PCA/pcaraw.PNG" />

These are some common financial indicators to measure fair price of a company. I picked 5 of many indicators which i wanted in my sample analyse. Different choices made among the indicators will change the whole result.Therefore, it is important to make the right choices.  Raw data columns has various ranges. For instance price to earning range is 1.43 to 244.74 and price to book value range is 0.29 to 30.51. Too much numerical difference between columns affects their impact on the result which is not wanted. Thats why applied following steps to balance them:
<ul>
  <li>Normalize each ratio indicator in its own column to fit 0 to 1 </li>
  <li>Crop extreme high/lows fixed limit </li>
  <li>After normaliztion 1 should be the best and 0 should be the worst value for each column but for some ratios lower value is better. For price to book value,dept to equality,price to book, price to 52W range lower is better. Therfore subtracted their normalized value from 1 for these columns  </>
</ul>
  
Here is the result (ticks.norm.csv):
<img src="https://diwsi.github.io/PCA/pcanorm.PNG" />

Afer data fetch and normalization I pushed an other single row to final data. It is "Referance"  point. An imaginary stock with perfect ratios. All the indicators equals to 1. That point will help me to figure out better stocks after PCA decomposition.
<img src="https://diwsi.github.io/PCA/ref.PNG" />

# PCA
The dataset, initially consisting of five feature dimensions, was reduced to two principal components using PCA. These components capture the essential characteristics of the data. The analysis was performed using scikit-learn, with pandas and matplotlib for visualization.

Here’s the resulting scatter plot:

<img src="https://diwsi.github.io/PCA/pcapl.png" />

Closer to Referrance point means  better results:

<img src="https://diwsi.github.io/PCA/pcapl2.png" />
