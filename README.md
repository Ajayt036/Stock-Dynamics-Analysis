# Stock-Dynamics-Analysis
A stock market is where buyers and sellers trade shares of a company, and is one of the most popular ways for individuals and companies to invest money. The size of the world stock market is now estimated to be in the trillions. The largest stock market in the world is the New York Stock Exchange (NYSE), located in New York City. About 2,800 companies were listed on the NSYE at the time time of this data xtarcted. In this problem, we'll look at the monthly stock prices of five of these companies: IBM, General Electric (GE), Procter and Gamble, Coca Cola, and Boeinga and create someisngiths and studies out of it with analysis and visualization


### Agenda:
    
- Load, observe, summarise the data sets
- Changing date formats compatible to pandas, and extract Date and years columns
- Analyse Stack price of each Company on plot chart.
- Observe trends of stiock prices  from 1970 tO 201o.
- Comparison of one company's stock price to the other.
- Impact of 2000 Global Technogy buuuble in the stock price of each of five company
- Impact of 1997 Asian Economy Mini Crash Ton the stock price of each of five company

### Libraries 
Installing all required libraries to be used in our analysis and visulization.

```ruby
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
%matplotlib inline
```
### Loading data sets.
Laoding data set of each comapny to start our Analaysis.
```ruby
IBM = pd.read_csv("IBMStock.csv")
GE = pd.read_csv("GEStock.csv")
PG = pd.read_csv("ProcterGambleStock.csv")
CocaCola = pd.read_csv("CocaColaStock.csv")
Boeing = pd.read_csv("BoeingStock.csv")
```

### Max, Min, Mean, Median and SD 
Lets find the the the maximun, minimum, average and standard deviation of different data set for our understanding.

```ruby
#Maximum stock price of CocaCola
round(float(CocaCola.StockPrice.max()),2)

#Minmum stock price of PG
round(float(PG.StockPrice.min()),2)

#Mean Stock Price of Boeing
round(float(Boeing.StockPrice.mean()),2)

#Median Stock Price of IBM
IBM.StockPrice.median()

#Standard deviation of stock price of Boeing
round(float(Boeing.StockPrice.std()),2)

```

### Ploting stock Price of CocaCola
stock price of CocaCola on the plot chart to observe the trend of its Stock proce over the from 1970 to 2010.

 ``` ruby
 plt.plot(CocaCola.Year, CocaCola.StockPrice,"o")
plt.xlabel("Year")
plt.ylabel("Stock Price")
plt.title ("Stock Price of CocaCola")
plt.show()
```
![image](https://user-images.githubusercontent.com/64645859/135140692-1461e054-b201-437b-8af0-4b8b32a2e751.png)


### Comparison of Stock Prices of Procter and Gamble and Coca Cola

```ruby
PG["Date"] = pd.to_datetime(PG["Date"])
PG["Year"] = PG["Date"].dt.year

Line1, = plt.plot(PG.Year, PG.StockPrice)
Line2, = plt.plot(CocaCola.Year, CocaCola.StockPrice)
plt.xlabel("Year")
plt.ylabel("Stock Price")


plt.title ("Stock Price of CocaCola and PG")
plt.legend([Line1,Line2],["PG","CocaCola"])
plt.show()
```
![image](https://user-images.githubusercontent.com/64645859/135140814-7bebd7e7-8702-4e11-a5d8-6b30e38c1ab8.png)


### Impact of 2000 Technology bubble

In Technogly bubble of 2000, Mnay comapny Stock prices started to crashed and Maany started to rise. We Will see this Impact all five companies.

```ruby
plt.plot(CocaCola.Year[301:432], CocaCola.StockPrice[301:432],label = "CocaCola")
plt.plot(PG.Year[301:432], PG.StockPrice[301:432],label = "PG")
plt.plot(Boeing.Year[301:432], Boeing.StockPrice[301:432],label = "Boeing")
plt.plot(GE.Year[301:432], GE.StockPrice[301:432],label = "GE")
plt.plot(IBM.Year[301:432], IBM.StockPrice[301:432],label = "IBM")

plt.title ("Stock Price of all comanies during Mini Asian Crash from Sep to Nov in 1997")
plt.xlabel("Month")
plt.ylabel("Stock Price")
plt.legend()
plt.show()
```
![image](https://user-images.githubusercontent.com/64645859/135140912-4444c1e1-03df-420a-9e69-93bfa4a2e9da.png)

### Impact of 1997 Asin Economy MiniCrash
In October of 1997, there was a global stock market crash that was caused by an economic crisis in Asia. Comparing September 1997 to November 1997, Lets observe which companies saw a decreasing trend in their stock price?
```ruby
plt.plot(CocaCola.Month[332:335], CocaCola.StockPrice[332:335],label = "CocaCola")
plt.plot(PG.Month[332:335], PG.StockPrice[332:335],label = "PG")
plt.plot(Boeing.Month[332:335], Boeing.StockPrice[332:335],label = "Boeing")
plt.plot(GE.Month[332:335], GE.StockPrice[332:335],label = "GE")
plt.plot(IBM.Month[332:335], IBM.StockPrice[332:335],label = "IBM")

plt.title ("Stock Price of all comanies during Mini Asian Crash from Sep to Nov in 1997")
plt.xlabel("Month")
plt.ylabel("Stock Price")
plt.legend()
plt.show()
```
![image](https://user-images.githubusercontent.com/64645859/135141140-bbdbf2d1-09c3-45e1-b00f-60f1ce2ebe3e.png)



