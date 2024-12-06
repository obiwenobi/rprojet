Mauritius time series
================
Obiwenobi
2024-12-06

# Introduction

This document aims to define whether macroeconomics variables in
Mauritius are endogenous. The dataset used to produce these figures and
tables is merge from various sources. It gathers data from 1964 to 2018.

# Data summary

The dataset **dbase** includes the following variables:

    ##  [1] "year"         "birth"        "death"        "infmortality" "stillbirth"  
    ##  [6] "marriage"     "divorce"      "gdp"          "g"            "inf"

- **birth**: The number of live births in a year per 1,000 mid-year
  population.
- **death**: The number of deaths in a year per 1,000 mid-year
  population.
- **infmortality**: The number of infant deaths in a year per 1,000 live
  births during the year.
- **g**: Annual growth rate
- **inf**: Annual inflation rate,Percent, Not Seasonally Adjusted
- **gdp**: Gross domestic product, billions of US \$

<!-- Compléter les autres  variables -->

Let’s look at the descriptive statistics of our variables.

``` r
summary(dbase)
```

    ##       year          birth           death        infmortality     stillbirth   
    ##  Min.   :1964   Min.   :10.10   Min.   :6.476   Min.   :11.80   Min.   : 6.80  
    ##  1st Qu.:1978   1st Qu.:15.50   1st Qu.:6.770   1st Qu.:14.40   1st Qu.:10.05  
    ##  Median :1991   Median :19.60   Median :7.162   Median :20.44   Median :15.89  
    ##  Mean   :1991   Mean   :20.29   Mean   :7.321   Mean   :29.48   Mean   :20.72  
    ##  3rd Qu.:2004   3rd Qu.:25.61   3rd Qu.:7.752   3rd Qu.:37.81   3rd Qu.:28.18  
    ##  Max.   :2018   Max.   :38.90   Max.   :9.188   Max.   :71.97   Max.   :55.20  
    ##     marriage         divorce            gdp                g           
    ##  Min.   : 9.947   Min.   :0.2169   Min.   : 0.3163   Min.   :-0.79486  
    ##  1st Qu.:15.741   1st Qu.:0.4878   1st Qu.: 3.2169   1st Qu.:-0.33537  
    ##  Median :18.400   Median :1.3889   Median : 6.4193   Median :-0.05803  
    ##  Mean   :17.353   Mean   :1.4790   Mean   : 7.3360   Mean   : 0.73759  
    ##  3rd Qu.:20.057   3rd Qu.:2.1000   3rd Qu.: 9.0364   3rd Qu.: 0.35264  
    ##  Max.   :23.012   Max.   :3.8000   Max.   :41.9995   Max.   :16.65818  
    ##       inf         
    ##  Min.   : 0.3163  
    ##  1st Qu.: 3.2169  
    ##  Median : 6.4193  
    ##  Mean   : 7.3360  
    ##  3rd Qu.: 9.0364  
    ##  Max.   :41.9995

How did the variables evolve during the years ? First, the health data.

``` r
dbase %>% 
  ggplot() + 
  geom_line(aes(y = stillbirth, x = year, color = "Stillbirth")) + 
  geom_line(aes(y = death, x = year, color = "death")) + 
  geom_line(aes(y = infmortality, x = year, color = "infmortality")) +
  geom_line(aes(y = birth, x = year, color = "Birth")) +
  xlab('Year') +
  ylab('') +
  labs(title = "Health variables over Time - Mauritius", color = "Legend") +
  scale_color_manual(values = c("Stillbirth" = "red", "Birth" = "blue","death"="black",
                                "infmortality"="green"))
```

![](wp_files/figure-gfm/unnamed-chunk-2-1.png)<!-- -->

We can see that every rate is decreasing and might probably be
correlated. Evaluating this effect through regression would probably be
misleading as all those variable are likely to be endogenous. Methods
such as Vector Auto-Regressive models suits well to identify such
relationships but requires high frequency data such as quarterly data.
The data set only provides yearly data which does not ensure the
estimations to be converging.

Before we investigate this, let’s consider macroeconomic data.
