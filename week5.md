Work\_week5
================

``` r
library(ggplot2)
library(dplyr)
```

    ## 
    ## Attaching package: 'dplyr'

    ## The following objects are masked from 'package:stats':
    ## 
    ##     filter, lag

    ## The following objects are masked from 'package:base':
    ## 
    ##     intersect, setdiff, setequal, union

R Markdown
----------

This is an R Markdown document. Markdown is a simple formatting syntax for authoring HTML, PDF, and MS Word documents. For more details on using R Markdown see <http://rmarkdown.rstudio.com>.

When you click the **Knit** button a document will be generated that includes both content as well as the output of any embedded R code chunks within the document. You can embed an R code chunk like this:

``` r
data=read.csv('dataset_student_survey_data.csv')
```

Including Plots
---------------

You can also embed plots, for example:

``` r
data[1:10,]
```

    ##    index    Sex WrHnd NWHnd  WHnd    Fold Pulse    Clap Exer Smoke Height
    ## 1      1 Female  18.5  18.0 Right  R on L    92    Left Some Never 173.00
    ## 2      2   Male  19.5  20.5  Left  R on L   104    Left None Regul 177.80
    ## 3      3   Male  18.0  13.3 Right  L on R    87 Neither None Occas     NA
    ## 4      4   Male  18.8  18.9 Right  R on L    NA Neither None Never 160.00
    ## 5      5   Male  20.0  20.0 Right Neither    35   Right Some Never 165.00
    ## 6      6 Female  18.0  17.7 Right  L on R    64   Right Some Never 172.72
    ## 7      7   Male  17.7  17.7 Right  L on R    83   Right Freq Never 182.88
    ## 8      8 Female  17.0  17.3 Right  R on L    74   Right Freq Never 157.00
    ## 9      9   Male  20.0  19.5 Right  R on L    72   Right Some Never 175.00
    ## 10    10   Male  18.5  18.5 Right  R on L    90   Right Some Never 167.00
    ##          MI    Age
    ## 1    Metric 18.250
    ## 2  Imperial 17.583
    ## 3      <NA> 16.917
    ## 4    Metric 20.333
    ## 5    Metric 23.667
    ## 6  Imperial 21.000
    ## 7  Imperial 18.833
    ## 8    Metric 35.833
    ## 9    Metric 19.000
    ## 10   Metric 22.333

Note that the `echo = FALSE` parameter was added to the code chunk to prevent printing of the R code that generated the plot.

``` r
ggplot(data,aes(Smoke,fill=Exer) ) +geom_bar(position = 'dodge2')+
  facet_wrap(~Sex,ncol = 1)+
  ylab('Counts') +
  xlab('Smoker')+
  ggtitle('The Exercise habits of Male and Female students that smoke')
```

![](week5_files/figure-markdown_github/unnamed-chunk-3-1.png)

``` r
data2=read.csv('dataset_us_car_price_data (1).csv')
```

``` r
data2[1:10,]
```

    ##     X    Type MinPrice Price MaxPrice RangePrice RoughRange gpm100 MPGcity
    ## 1   6 Midsize     14.2  15.7     17.3        3.1       3.09    3.8      22
    ## 2   7   Large     19.9  20.8     21.7        1.8       1.79    4.2      19
    ## 3   8   Large     22.6  23.7     24.9        2.3       2.31    4.9      16
    ## 4   9 Midsize     26.3  26.3     26.3        0.0      -0.01    4.3      19
    ## 5  10   Large     33.0  34.7     36.3        3.3       3.30    4.9      16
    ## 6  11 Midsize     37.5  40.1     42.7        5.2       5.18    4.9      16
    ## 7  12 Compact      8.5  13.4     18.3        9.8       9.80    3.3      25
    ## 8  13 Compact     11.4  11.4     11.4        0.0      -0.01    3.4      25
    ## 9  14  Sporty     13.4  15.1     16.8        3.4       3.38    4.2      19
    ## 10 15 Midsize     13.4  15.9     18.4        5.0       5.01    4.0      21
    ##    MPGhighway
    ## 1          31
    ## 2          28
    ## 3          25
    ## 4          27
    ## 5          25
    ## 6          25
    ## 7          36
    ## 8          34
    ## 9          28
    ## 10         29

``` r
ggplot(data2,aes(x=Price,fill=Type)) +
  geom_histogram() +
  facet_wrap(~Type) +
  ylab('Freq') +
  ggtitle('Car Price Distribution based on Car Type')
```

    ## `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.

![](week5_files/figure-markdown_github/unnamed-chunk-6-1.png)

``` r
data3<-read.csv('dataset_production_of_rice_in_india.csv')
```

``` r
data3[1:10,]
```

    ##     X     id  size status varieties bimas seed urea phosphate pesticide
    ## 1   1 101001 3.000  owner     mixed mixed   90  900        80      6000
    ## 2   2 101001 2.000  owner      trad mixed   40  600         0      3000
    ## 3   3 101001 1.000  owner      high mixed  100  700       150      5000
    ## 4   4 101001 2.000  owner      high mixed   60  600       100      5000
    ## 5   5 101001 3.572  share      high    no  105  400       400     10200
    ## 6   6 101001 3.572  share      high    no  105  400       400     10200
    ## 7   7 101017 1.420  mixed      trad mixed   50  120         0         0
    ## 8   8 101017 1.420  mixed      high mixed   20  100         0         0
    ## 9   9 101017 0.428  mixed      high mixed   15  150        50       900
    ## 10 10 101017 0.214  owner     mixed    no    7   50         0         0
    ##    pseed purea pphosph hiredlabor famlabor totlabor   wage goutput noutput
    ## 1     80    75      75       2875       40     2915  68.49    7980    6800
    ## 2     70    75      75       2110       45     2155  60.09    4083    3500
    ## 3    140    70      70        980       95     1075  51.99    2650    2242
    ## 4     90    70      70       2081       10     2091  56.98    4500    3750
    ## 5    350    80      80       3889        1     3889 152.03   16300   13584
    ## 6    250    80      80       3519        1     3519 154.49   17424   14520
    ## 7     60    75      75        670      140      810  54.83    3840    3200
    ## 8     50    75      75        805       50      855  45.43    2800    2400
    ## 9    130    70      70        380       80      460  51.97     950     800
    ## 10   150    70      70         40       69      109  53.75     240     200
    ##    price        region
    ## 1     60 wargabinangun
    ## 2     60 wargabinangun
    ## 3     65 wargabinangun
    ## 4     70 wargabinangun
    ## 5    120 wargabinangun
    ## 6    140 wargabinangun
    ## 7     60 wargabinangun
    ## 8     50 wargabinangun
    ## 9     62 wargabinangun
    ## 10    60 wargabinangun

``` r
ggplot(data3,aes(x=varieties,y=price,fill=bimas)) +
  geom_boxplot()+
  facet_wrap(~status,ncol = 1)+
  xlab('Rice Varieties')+
  ylab('Price')+
  ggtitle('India Rice Prices based on Varieties, Land Status, and Bimas Program')
```

![](week5_files/figure-markdown_github/unnamed-chunk-9-1.png)

``` r
ggplot(data3,aes(x=price,y=wage,col=bimas,shape=bimas))+
  geom_point()+
  facet_wrap(~status, ncol = 1)+
  xlab('Rice Price')+
  ylab('Wage')+
  ggtitle('India Rice Prices vs Wage broken down by Land Status and Bimas Program')
```

![](week5_files/figure-markdown_github/unnamed-chunk-10-1.png)
