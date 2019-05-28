Kevin Nguyen, Lucas Woo, Andy Chen, Zachary Tan
<br>March 1, 2019
<br>INFO 370
<br>Project Proposal

# Project Description
The purpose of our research project is to be able to perform predictions on the open stock
price of a company to enable investors to be more confident as to where they invest their
money. This can be very difficult to do because of the many factors that go into a stock price
which can be both physical and physiological. If investors know which factors are the most
important and correlated to the stock price, this will be able to guide them to make the
right investments. This can also be for people who want to make a model to predict stock 
prices and help them find those factors that are the most dominating than others. Further,
the research should detail specific characteristics that have have in the past been positively
related to the stock price as well as negatively related. The hope is to aid novice investors
on investment decisions and inform them on factors that might impact future returns.

Currently, there is the Capital Asset Pricing Model (CAPM) that many in the financial realm
use to describe the relationship between systematic risk and expected return for assets. Using
the CAPM will generate expected returns for assets given the risk of those assets and the
cost of capital. The risk of the asset is measured by the asset’s Beta while the cost of
capital used is the risk free interest rate. The beta of the underlying asset is the measure
of risk of the investment and represents the covariance with the market as a whole. If there
is a Beta of 1, the asset is perfectly correlated with the market, a Beta of 0 implies no
correlation with the market, and a correlation of -1 implies a perfectly negative correlation
with the market. This model demonstrates how if the CAPM is accurate, investors will be
compensated for risk and the time value of money. The investor is compensated proportionally
to the risk and the stocks return should be equal to the risk free rate plus the Beta
multiplied the risk premium (risk premium is expected market return minus risk free rate).
(https://www.investopedia.com/terms/c/capm.asp)

The Fama French Three Factor Model is an extension of the CAPM model for pricing assets. This
model considers the fact that value and small-cap stocks outperform markets on a regular basis.
By including these two additional factors, the model adjusts for this outperforming tendency which
is important to encapsulate in the model which the CAPM leaves out. Laureate Fama and Kenneth
French found that value stocks outperform growth stocks while small-cap stocks tend to outperform
large-cap  stocks. For those without a background in Finance, value stocks are those with high
book to market ratios while the converse is true for growth stocks. The book value is calculated
by looking at the firm’s historical cost, or accounting value while the market value is determined
in the stock market through its market capitalization. Small-cap stocks are those that are under
the median market capitalization while large-cap stocks are those that are above the median market
capitalization. This new model adjusts for these out performances. This adds another layer into
the pricing of stocks which need to be accounted for when predicting stock price and adjusting for
risk. (https://www.investopedia.com/terms/c/capm.asp)

There is roughly 80-90% of non-institutional traders that lose money when trading. It has become
increasingly more difficult for traders to beat the market due to the rise of algorithmic trading
which virtually eliminates any chance for individuals to make money trading on a short-term basis.
Further, day trading is now the least profitable way to trade, as only advanced supercomputers can
now benefit from world news and company earnings. Because of the widely advertised strategy of day
trading, many retail traders begin to attempt this tactic and lose money quickly and then likely
end with a money manager. What often isn’t publicized are specific features of companies that tend
to do well in the market. Because of this, we would like to highlight this so that non-institutional
investors can profit as well.
(https://medium.com/s/story/predicting-the-stock-market-is-easier-than-you-might-think-4f1e0bc05cfe)

These three articles describe what current factors are used when determining future stock price
predictions, as well as represents the difficulty retail investors have in today’s market. Because
of this, data would greatly benefit those without formal financial training and educational backgrounds.
By clearly identifying data and making correlation with price outcomes transparent, we hope to better
inform the non-institutional investors.

The null hypothesis that we are testing is that company financials and fundamental characteristics
do not correlate future prices of the stock. While the alternative hypothesis we are testing is
that company financials and fundamental characteristics do correlate with future prices of the
stock.

The dataset that we are working with is one that we found from https://www.kaggle.com/.
The person who scraped the data fetched the prices from Yahoo Finance and grabbed the
fundamental columns from Nasdaq Financials and some of those columns were extended using fields
from the EDGAR SEC databases.

In terms of statistical methods, we will try to do a multivariate regression by using both linear
regression and polynomial regression based on the data distribution. This way we will try to
figure out which model fits the data best. For machine learning methods, we will mainly be using
K-nearest neighbors and the decision tree algorithm to try to construct our machine learning
model. The main reason for applying both is because we want to see which model will give us
the most accurate result. Then when we do the model selection for each of them, we will to
apply forward selection to select variables that can give us best prediction.

There are three primary audiences for our resource. The first is stock investors, with an
emphasis on investors with little to no background with the stock market and investing. We
hope to increase their knowledge on potential influencers of stock price based on company
fundamentals and to help make rational investment decisions. Additionally, companies who want
to predict their companies price by using their internal information. Lastly, data
scientists who want to develop some statistical model. We are honing in on the investors
as an audience to try to help with more data driven investment decisions.

From our research, our audience should be able to know what variables potentially correlate to
stock price (opening price) and the strength of each factors individually. We can develop a
machine learning model that can potentially guide investors, companies and other data scientists
to make educated decisions on investing into businesses based on their predicted stock price.
The audience should also learn which stocks have outperformed or underperformed the relative market.
Further, it should provide realistic expectations for portfolio returns on investments and also help
highlight the variance in stock price. We also want the audience to learn how risky the stock market
is and that even companies with the best features can underperform and result in a net loss.

# Technical Description

The format of our final web resource will be an HTML page that we have created from R Markdown. We
wanted to do this because it is a web resource that we have been using all quarter and since it is
very familiar to us, we won't have any problems.

The biggest challenge about the management of this dataset will be that because there are so
many fundamental columns that are provided to predict the open stock prices on, if we choose
the wrong variables, it might throw our whole model off. We also don’t want to just use all
of the features provided to us because this will overfit the data and thus create unnecessary
confusion for our model that will detract from the important features. It is also important to
note that we don’t want to perform a forward/backward selection process with that many columns
because of the amount of time it takes to process all of that information in our machine.

Some of the new technical skills that we would have to learn for this project would include:
how to create an identifier column and making sure that we are merging on that, how to create a
heat map of correlations, and how to perform forward selection on a polynomial regression. Other
than that, this class has given us enough knowledge to perform the other actions confidently.

We will conduct our analysis by first merging the two datasets together because the datasets are
split into two tables. Since there is no identifier column, we will have to create that to able to
merge the sets. We will do this by combining the date and the business’s abbreviation together to
make a new column that is going to be used as the ID column. After this, we will have to clean up
the data by removing the rows with null values. We opted to do this rather than filling in the data
with forward filling, the average, or just filling it as zero because that would not make sense for
this kind of dataset since these are individual businesses and the attributes of one company is not
dependent on all of the attributes of all of the other businesses. We also have so many rows of data
that we feel as if just removing them won’t impact our analysis much. Once we have cleaned the data,
we will create a heat map of all of the variables and their correlations so that we can have an idea
of the strength of each variable in the dataset. We will use this and our prior knowledge of the most
important factors in a business to choose the top 15 variables and run preliminary regressions on
factors that had low lower correlations to analyze them further.

We will then run a multivariate regression on the condensed dataset and see how much variation of the
open stock price can be explained by the variables we have chosen. After this, we will run the polynomial
multivariate regression to the same variables and compare the results to understand which regression fit
better and which one to go with. Moreover, we will do a forward selection on the dataset to pick out the
most accurate model and compare that to our results before. More specifically, we want to take an extra
good look at the p-values, r-squared values, confidence intervals, and coefficients. Based on these
values, we will continue extra testing and potentially removing some factors to not overfit the model
if they don’t have statistically significant relations with our outcome variable.

After this, we will try to construct the machine learning model by using the same variables. We will
first try to use decision tree algorithm to make the model and then use the K-nearest neighbors algorithm
to find the best model. Then we will examine both models’ adjusted r squared value, p value, coefficients
and confidence interval.

Predicting stock prices has always been a challenge for even the biggest experts on the topic of machine
learning and business, and no one has ever been able to do it accurately before. Knowing this, we are
aware that we may run into a lot of trouble trying to find the best predictors and we might not be able
to create a model that is clearly defined to predict open stock prices, but we would love to try and get
as close as possible.
