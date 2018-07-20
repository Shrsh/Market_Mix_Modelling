# Market_Mix_Modelling

The marketing mix refers to variables that a marketing manager can control to influence a brand’s sales or market share. 
Traditionally,these variables are summarized as the **four Ps of marketing: product, price, promotion, and place.**
The perennial question that managers face is,what level or combination of these variables maximizes sales, market share, or profit?
\ 
The answer to this question, in turn, depends on the following question: How do sales or market  share respond to past levels of or expenditures on these variables?

## Business Understanding
An e-commerce firm specialising in electronic products. Over the last one year, they had spent a significant amount of money in marketing. Occasionally, they had also offered big-ticket promotions (similar to the Big Billion Day). They are about to create a marketing budget for the next year which includes spending on *commercials, online campaigns, and pricing & promotion strategies.* 
\
The CFO feels that the money spent over last 12 months on marketing was not sufficiently impactful and that they can either cut on the budget or reallocate it  optimally across marketing levers to improve the revenue response. 
\
**What is the perfect way of allocating the budget to different channels so that sales can be maximized?**
\
Download the data from [here](https://drive.google.com/drive/folders/1jW1yHFiQ7d3_MI2P40hw2NLm5hJp09e8?usp=sharing)

## Instructions
* Download consumer data from the link. 
* Run Data Preprocessing 
* Run Feature Engineering
*  Run Camera Accesories, Gaming Accesories or Home Audio to see the elasticity analysis. 

## Key Performance Indicators
**Marketing Metrics and Key Performance Indicators (KPIs)** are measurable values used by marketing teams to demonstrate the effectiveness of campaigns across all marketing channels. Whether you are looking to track digital marketing performance, SEO progress, or your social media growth, having measurable marketing metrics and KPIs set up can help your business reach targets month-over-month. 

* Performance Indicators
  * Promotion Effect 
  * Holiday Effect
  * Brand Perception 
  * Adstock
  * Price Inflation 
  * Lag Sale
  * Payment Mode
  * Advertising Mode
  * Customer Loyalty 
  * Customer Feedback 
  * Competition 
  * Industry Trend

## Pipeline
### Data Preprocessing
* Converting the data into TimeSeries
* Data Cleaning
* Outlier Treatment
* Dividing the data into subclasses: Home Audio, Camera Accesory, Gaming Accesories

### Feature Engineering
* Promotion Effect: Special promotion going on site like Big Billion Day
  * Promotion offered = (MRP - list price)/MRP where list price = GMV/units sold
  * List price inflation: wrt previous week, wrt average price of previous 2/3/4/5/6 weeks, wrt moving average ofprevious week, wrt moving average of previous month.
  * Lag sale, i.e. the past value of GMV
  * Lag promotion, i.e. the past value of promotion
  * Weekly percentage change in promotion, monthly percentage change in promotion etc.
* Adstock: Adstock of each of the ‘commercial spends’ (Since we don’t have TRP/ Impression information, we will assume
spend is directly proportional to the impression)
* Variable Transformation: Log of adstock, log of other independent variables (log adstocks, log NPS etc.)
* Brand Perception: you may create a product level variable called product premium-ness – based on the MRP and units sold under each product vertical, you may tag whether the product is a mass market, aspiring or premium product
* External Variable Effect:
  * Net Promoter Score(NPS):The Net Promoter Score is an index ranging from -100 to 100 that measures the willingness of customers to recommend a  company’s products or services to others. It is used as a proxy for gauging the customer’s overall satisfaction with a company’s product or service and the customer’s loyalty to the brand.
  * Holiday Effect

#### List of Engineered KPIs
* Promotion offered
* List price inflation
* Lag sale
* Lag promotion
* Weekly percentage change in promotion, monthly percentage change in promotion etc.
* Adstock
* Log of adstock
* Product level variable - mass market, aspiring or premium product
* Total revenue from the electronic market in India (Month by month)
* Daily temperature and rainfall –
* Indian holidays
#### Advanced Feature Engineering
Created moving averages for Promotional Offer, List Price and NPS score given by customer.

### Models
#### Simple Linear Model
The aim of linear regression is to model a continuous variable Y as a mathematical function of one or more X variable(s), so that we can use this regression model to predict the Y when only the X is known. This mathematical equation can be generalized as follows:
 
  Y = β1 + β2X + ϵ

where, β1 is the intercept and β2 is the slope. Collectively, they are called regression coefficients. ϵ is the error term, the part of Y the regression model is unable to explain.

#### Multiplicative Model
This model assumes that as the data increase, so does the seasonal pattern. Most time series plots exhibit such a pattern. In this model, the trend and seasonal components are multiplied and then added to the error component.
Multiplicative model’s benefits include synergistic impact of **marketing activities, independence of shapes of transformations** independent variable scan take due to coefficient values and coefficients directly provide simple elasticity indications.

#### Kyock Model
The Koyck model may be considered a simple augmentation of the basic linear model , which includes the lagged dependent variable as independent variable.What this specification means is that sales depend on sales of the prior period and all the independent variables that caused prior sales,plus the current values of the same independent variables

#### Distributed Lag Model
A distributed-lag model is a dynamic model in which the effect of a regressor x on y occurs over time rather than all at once.
The distributed lag model is a model with multiple lagged values of both the dependent variable and the independent variable.
This model is very general and can capture a whole range of carryover effects. Indeed, the Koyck model can be considered a special case
of distributed lag model with only one lagged value of the dependent variable. The distributed lag model overcomes two of the problems with the Koyck model.
First, ***it allows for decay functions, which are nonmonotonic or humped shaped***. 
Second, ***it can partly separate out the carryover effects of different independent variables***.

## Deployment
I have used **R** for building the models and **shiny** for deploying this model.
\
[Exploratory Data Analysis](https://harsh12datascience.shinyapps.io/ExploratoryDataAnalysis/)
\
[Models and Elasticity Analysis](https://harsh12datascience.shinyapps.io/model_market_mix/)

## Authors: 
Harsh Shukla and [Priya Agrawal](https://github.com/Pryagrawal)

## License
This project is licensed under the Apache 2.0 License




