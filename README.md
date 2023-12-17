/kaggle/input/product-advertising-data/Advertising_Data.csv

```
df = pd.read_csv("/kaggle/input/product-advertising-data/Advertising_Data.csv")
df.head()
```
 
<img width="583" alt="image" src="https://github.com/tuerkerme/A_Python_Based_Advertising_Analysis/assets/149696414/943219fa-4056-4e97-9427-811dc7497e22">
 
```
df.describe()
```
<img width="651" alt="image" src="https://github.com/tuerkerme/A_Python_Based_Advertising_Analysis/assets/149696414/a631f350-38f9-44c8-abb4-a42bbf52fad1">
 
```
df.isnull().sum()
 
```
 
<img width="199" alt="image" src="https://github.com/tuerkerme/A_Python_Based_Advertising_Analysis/assets/149696414/48188b6d-610c-4bb7-a4f4-8b3dd802299d">
 
The dataset contains the following columns:
 
TV: Advertising costs for TV.
 
Billboards: Advertising costs for billboards.
 
Google_Ads: Advertising costs for Google Ads.
 
Social_Media: Advertising costs for social media.
 
Influencer_Marketing: Advertising costs for influencer marketing.
 
Affiliate_Marketing: Advertising costs for affiliate marketing.
 
Product_Sold: Number of products sold, presumably influenced by the advertising costs.
 
```
import matplotlib.pyplot as plt
 
#### Histograms for Advertising Costs and Product Sold
df.hist(bins=30, figsize=(15, 10))
plt.suptitle(`Distribution of Advertising Costs and Product Sold`)
plt.show()
 
```
 
<img width="516" alt="image" src="https://github.com/tuerkerme/A_Python_Based_Advertising_Analysis/assets/149696414/0a92bae8-e9ac-461e-85ab-f6ee886b78db">
 
 ```
 import seaborn as sns
 ### Correlation Matrix and Heatmap
#### Correlation matrix
corr = df.corr()
 
#### Heatmap
plt.figure(figsize=(10, 8))
sns.heatmap(corr, annot=True, cmap=`coolwarm`)
plt.title(`Correlation Matrix`)
plt.show()
 
```
 <img width="432" alt="image" src="https://github.com/tuerkerme/A_Python_Based_Advertising_Analysis/assets/149696414/e3dac7fc-2100-49d5-845d-2679ea627e9b">
 
 ```
 ### Pairplot to Visualize Relationships
sns.pairplot(df)
plt.show()
 
```
 <img width="364" alt="image" src="https://github.com/tuerkerme/A_Python_Based_Advertising_Analysis/assets/149696414/f0adfadc-fc62-4b69-b4ca-dd6cadac0422">
 
```
### Scatter Plots with Regression Lines
ad_channels = [`TV`, `Billboards`, `Google_Ads`, `Social_Media`, `Influencer_Marketing`, `Affiliate_Marketing`]
for channel in ad_channels:
 sns.jointplot(x=channel, y=`Product_Sold`, data=df, kind=`reg`)
 plt.show()
 
```
 <img width="234" alt="image" src="https://github.com/tuerkerme/A_Python_Based_Advertising_Analysis/assets/149696414/2f4b0ac3-679e-4cfb-b74e-61c6e30d6e70">  <img width="223" alt="image" src="https://github.com/tuerkerme/A_Python_Based_Advertising_Analysis/assets/149696414/723f667b-bc94-457f-b4dc-f9a6e0a26413"> <img width="217" alt="image" src="https://github.com/tuerkerme/A_Python_Based_Advertising_Analysis/assets/149696414/1eab539f-401d-4d50-9e94-7a60bf87e033">
 
### FINDINGS

The visualizations provide further insights into the dataset:
Scatter Plots (Advertising Channels vs. Product Sold):
Each plot shows the relationship between the spending in a specific advertising channel and the number of products sold. There seems to be a general trend where higher advertising spending correlates with higher sales, especially noticeable in channels like Affiliate Marketing and Billboards.

Correlation Matrix (Heatmap):
The heatmap visualizes the correlation coefficients between different variables.

Affiliate Marketing has the highest positive correlation with Product Sold, reinforcing its potential effectiveness in driving sales. Other channels like Billboards and Social Media also show positive correlations with sales, albeit to a lesser extent.

These analyses suggest that advertising, particularly through channels like Affiliate Marketing, Billboards, and Social Media, is positively associated with sales. However, the exact effectiveness of each channel can vary, and these insights can guide you in optimizing your advertising strategy.

Descriptive Statistics
TV, Billboards, Google_Ads, Social_Media, Influencer_Marketing, Affiliate_Marketing:
The average advertising costs across these channels are fairly evenly distributed, with means ranging from approximately 466to
517. The standard deviations indicate a moderate level of variability in spending across these channels.
Product_Sold:
The average number of products sold is about 7032 units, with a standard deviation of 1704 units, indicating variability in sales figures.
TV Advertising Costs:

Mean (Average): $517.43, on average, is spent on TV advertising.

Standard Deviation: $288.11, TV advertising costs vary widely across the dataset.

Minimum: 1.04, indicating at least one very low spend in TV advertising.

Maximum: $998.10, showing that some campaigns have very high TV advertising costs.

Median (50th percentile): $513.97, meaning that half of the TV advertising costs are below this value and half are above.

Billboards Advertising Costs:

Mean: $502.64.

Standard Deviation: $275.84, indicating variability but slightly less than TV advertising.

Minimum: $3.63.

Maximum: $995.32.

Median: $533.02.

Google_Ads Advertising Costs:

Mean: $512.44.

Standard Deviation: $285.42.

Minimum: $14.86.

Maximum: $999.23.

Median: $528.96.

Social_Media Advertising Costs:

Mean: $489.80.

Standard Deviation: $273.88.

Minimum: $11.69.

Maximum: $996.16.

Median: $486.38.

Influencer_Marketing Advertising Costs:

Mean: $465.73.

Standard Deviation: $288.31, showing significant variability.

Minimum: $0.77.

Maximum: $999.83.

Median: $480.35.

Affiliate_Marketing Advertising Costs:

Mean: $484.43.

Standard Deviation: $277.96.

Minimum: $6.74.

Maximum: $987.58.

Median: $451.31.

Product Sold:

Mean: 7031.52 units, which is a strong indication of sales volume.

Standard Deviation: 1703.61 units, suggesting that sales figures also vary considerably across different campaigns or time periods.

Minimum: 2259 units, indicating the lowest sales in the dataset.

Maximum: 12227 units, showing the highest sales figure achieved.

Median: 7051 units, which helps in understanding that half of the sales figures are below this value and half above.

Interpretation:

The means and medians of the advertising costs across different channels are relatively close, suggesting a roughly symmetric distribution of spending in these channels.

The standard deviations are substantial in comparison to the means, indicating a wide range of spending across all advertising channels. Sales figures (Product Sold) show a high mean and median, but with a large standard deviation, indicating variability in sales performance.

These detailed statistics provide a more nuanced view of the spending patterns in each advertising channel and their potential impact on sales.

Correlation Analysis:
The correlation coefficients range from -0.13 to 0.61. Affiliate_Marketing shows the strongest positive correlation with Product_Sold (0.61), suggesting a strong relationship between affiliate marketing spending and sales.

Billboards and Social_Media also show notable positive correlations with sales (0.48 and 0.40, respectively). Other advertising channels like TV and Google_Ads have positive but weaker correlations with sales.

Affiliate Marketing and Product Sold (Correlation: 0.61)
This is a moderately strong positive correlation. It suggests that increases in affiliate marketing spending are associated with increases in the number of products sold. The relationship is significant but not perfect, indicating other factors also influence sales.

Billboards and Product Sold (Correlation: 0.48)
A moderate positive correlation. This indicates that higher billboard advertising costs tend to be associated with higher sales. While the relationship is notable, it is less strong than that of affiliate marketing, suggesting billboard advertising might be an important but not the only factor in driving sales.

Social Media and Product Sold (Correlation: 0.40)
A moderate positive correlation. Social media spending shows a significant relationship with sales, but the correlation is weaker compared to affiliate marketing and billboards. This suggests that while social media advertising impacts sales, its effectiveness might be less consistent or dependent on other variables. TV and Product Sold (Correlation: 0.37)

A moderate positive correlation, slightly weaker than that of social media. This indicates a relationship where higher spending on TV advertising correlates with higher sales, but the relationship is not as strong as some other channels. This could imply that while TV advertising has an impact, it might not be the most effective channel relative to others.

Google Ads and Product Sold (Correlation: 0.20)
A weak positive correlation. This suggests that while there is some relationship between spending on Google Ads and sales, it is not as pronounced as other advertising channels. This may indicate that Google Ads contribute to sales but are not the primary driver. Influencer Marketing and Product Sold (Correlation: 0.14)

A very weak positive correlation. This indicates a minimal relationship between influencer marketing spending and sales. The low correlation suggests that influencer marketing, in this particular dataset, does not have a substantial impact on sales, or its impact is overshadowed by other factors.

Interpretation:
Affiliate Marketing emerges as the most strongly correlated channel with sales, suggesting its effectiveness in this dataset. Billboards and Social Media also show good potential in influencing sales.

TV and Google Ads exhibit some influence on sales but are less effective compared to other channels. Influencer Marketing shows the least correlation with sales, suggesting it may not be the most effective channel in this specific context.

These correlations provide insights into where advertising budgets might be most effectively allocated to maximize sales. However, it`s important to note that correlation does not imply causation, and these relationships might be influenced by various external factors.
 
 
 
 
 
 
 
 
 
 
 
