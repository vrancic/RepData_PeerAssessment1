Title
========================================================

This is an R Markdown document. Markdown is a simple formatting syntax for authoring web pages (click the **Help** toolbar button for more details on using R Markdown).

When you click the **Knit HTML** button a web page will be generated that includes both content as well as the output of any embedded R code chunks within the document. You can embed an R code chunk like this:


**Loading and preprocessing the data**

Show any code that is needed to

- Load the data (i.e. read.csv())

```r
library(lattice)
activity <- read.csv("activity.csv")
```


- Process/transform the data (if necessary) into a format suitable for your analysis


```r
meanActivity <- aggregate(steps ~ interval, activity, mean)
```

**What is mean total number of steps taken per day?**

*For this part of the assignment, you can ignore the missing values in the dataset.*

- Make a histogram of the total number of steps taken each day:

```r
hist(activity$steps)
```

![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-3.png) 



- Calculate and report the mean and median total number of steps taken per day:

```r
meanActivity
```

```
##     interval     steps
## 1          0   1.71698
## 2          5   0.33962
## 3         10   0.13208
## 4         15   0.15094
## 5         20   0.07547
## 6         25   2.09434
## 7         30   0.52830
## 8         35   0.86792
## 9         40   0.00000
## 10        45   1.47170
## 11        50   0.30189
## 12        55   0.13208
## 13       100   0.32075
## 14       105   0.67925
## 15       110   0.15094
## 16       115   0.33962
## 17       120   0.00000
## 18       125   1.11321
## 19       130   1.83019
## 20       135   0.16981
## 21       140   0.16981
## 22       145   0.37736
## 23       150   0.26415
## 24       155   0.00000
## 25       200   0.00000
## 26       205   0.00000
## 27       210   1.13208
## 28       215   0.00000
## 29       220   0.00000
## 30       225   0.13208
## 31       230   0.00000
## 32       235   0.22642
## 33       240   0.00000
## 34       245   0.00000
## 35       250   1.54717
## 36       255   0.94340
## 37       300   0.00000
## 38       305   0.00000
## 39       310   0.00000
## 40       315   0.00000
## 41       320   0.20755
## 42       325   0.62264
## 43       330   1.62264
## 44       335   0.58491
## 45       340   0.49057
## 46       345   0.07547
## 47       350   0.00000
## 48       355   0.00000
## 49       400   1.18868
## 50       405   0.94340
## 51       410   2.56604
## 52       415   0.00000
## 53       420   0.33962
## 54       425   0.35849
## 55       430   4.11321
## 56       435   0.66038
## 57       440   3.49057
## 58       445   0.83019
## 59       450   3.11321
## 60       455   1.11321
## 61       500   0.00000
## 62       505   1.56604
## 63       510   3.00000
## 64       515   2.24528
## 65       520   3.32075
## 66       525   2.96226
## 67       530   2.09434
## 68       535   6.05660
## 69       540  16.01887
## 70       545  18.33962
## 71       550  39.45283
## 72       555  44.49057
## 73       600  31.49057
## 74       605  49.26415
## 75       610  53.77358
## 76       615  63.45283
## 77       620  49.96226
## 78       625  47.07547
## 79       630  52.15094
## 80       635  39.33962
## 81       640  44.01887
## 82       645  44.16981
## 83       650  37.35849
## 84       655  49.03774
## 85       700  43.81132
## 86       705  44.37736
## 87       710  50.50943
## 88       715  54.50943
## 89       720  49.92453
## 90       725  50.98113
## 91       730  55.67925
## 92       735  44.32075
## 93       740  52.26415
## 94       745  69.54717
## 95       750  57.84906
## 96       755  56.15094
## 97       800  73.37736
## 98       805  68.20755
## 99       810 129.43396
## 100      815 157.52830
## 101      820 171.15094
## 102      825 155.39623
## 103      830 177.30189
## 104      835 206.16981
## 105      840 195.92453
## 106      845 179.56604
## 107      850 183.39623
## 108      855 167.01887
## 109      900 143.45283
## 110      905 124.03774
## 111      910 109.11321
## 112      915 108.11321
## 113      920 103.71698
## 114      925  95.96226
## 115      930  66.20755
## 116      935  45.22642
## 117      940  24.79245
## 118      945  38.75472
## 119      950  34.98113
## 120      955  21.05660
## 121     1000  40.56604
## 122     1005  26.98113
## 123     1010  42.41509
## 124     1015  52.66038
## 125     1020  38.92453
## 126     1025  50.79245
## 127     1030  44.28302
## 128     1035  37.41509
## 129     1040  34.69811
## 130     1045  28.33962
## 131     1050  25.09434
## 132     1055  31.94340
## 133     1100  31.35849
## 134     1105  29.67925
## 135     1110  21.32075
## 136     1115  25.54717
## 137     1120  28.37736
## 138     1125  26.47170
## 139     1130  33.43396
## 140     1135  49.98113
## 141     1140  42.03774
## 142     1145  44.60377
## 143     1150  46.03774
## 144     1155  59.18868
## 145     1200  63.86792
## 146     1205  87.69811
## 147     1210  94.84906
## 148     1215  92.77358
## 149     1220  63.39623
## 150     1225  50.16981
## 151     1230  54.47170
## 152     1235  32.41509
## 153     1240  26.52830
## 154     1245  37.73585
## 155     1250  45.05660
## 156     1255  67.28302
## 157     1300  42.33962
## 158     1305  39.88679
## 159     1310  43.26415
## 160     1315  40.98113
## 161     1320  46.24528
## 162     1325  56.43396
## 163     1330  42.75472
## 164     1335  25.13208
## 165     1340  39.96226
## 166     1345  53.54717
## 167     1350  47.32075
## 168     1355  60.81132
## 169     1400  55.75472
## 170     1405  51.96226
## 171     1410  43.58491
## 172     1415  48.69811
## 173     1420  35.47170
## 174     1425  37.54717
## 175     1430  41.84906
## 176     1435  27.50943
## 177     1440  17.11321
## 178     1445  26.07547
## 179     1450  43.62264
## 180     1455  43.77358
## 181     1500  30.01887
## 182     1505  36.07547
## 183     1510  35.49057
## 184     1515  38.84906
## 185     1520  45.96226
## 186     1525  47.75472
## 187     1530  48.13208
## 188     1535  65.32075
## 189     1540  82.90566
## 190     1545  98.66038
## 191     1550 102.11321
## 192     1555  83.96226
## 193     1600  62.13208
## 194     1605  64.13208
## 195     1610  74.54717
## 196     1615  63.16981
## 197     1620  56.90566
## 198     1625  59.77358
## 199     1630  43.86792
## 200     1635  38.56604
## 201     1640  44.66038
## 202     1645  45.45283
## 203     1650  46.20755
## 204     1655  43.67925
## 205     1700  46.62264
## 206     1705  56.30189
## 207     1710  50.71698
## 208     1715  61.22642
## 209     1720  72.71698
## 210     1725  78.94340
## 211     1730  68.94340
## 212     1735  59.66038
## 213     1740  75.09434
## 214     1745  56.50943
## 215     1750  34.77358
## 216     1755  37.45283
## 217     1800  40.67925
## 218     1805  58.01887
## 219     1810  74.69811
## 220     1815  85.32075
## 221     1820  59.26415
## 222     1825  67.77358
## 223     1830  77.69811
## 224     1835  74.24528
## 225     1840  85.33962
## 226     1845  99.45283
## 227     1850  86.58491
## 228     1855  85.60377
## 229     1900  84.86792
## 230     1905  77.83019
## 231     1910  58.03774
## 232     1915  53.35849
## 233     1920  36.32075
## 234     1925  20.71698
## 235     1930  27.39623
## 236     1935  40.01887
## 237     1940  30.20755
## 238     1945  25.54717
## 239     1950  45.66038
## 240     1955  33.52830
## 241     2000  19.62264
## 242     2005  19.01887
## 243     2010  19.33962
## 244     2015  33.33962
## 245     2020  26.81132
## 246     2025  21.16981
## 247     2030  27.30189
## 248     2035  21.33962
## 249     2040  19.54717
## 250     2045  21.32075
## 251     2050  32.30189
## 252     2055  20.15094
## 253     2100  15.94340
## 254     2105  17.22642
## 255     2110  23.45283
## 256     2115  19.24528
## 257     2120  12.45283
## 258     2125   8.01887
## 259     2130  14.66038
## 260     2135  16.30189
## 261     2140   8.67925
## 262     2145   7.79245
## 263     2150   8.13208
## 264     2155   2.62264
## 265     2200   1.45283
## 266     2205   3.67925
## 267     2210   4.81132
## 268     2215   8.50943
## 269     2220   7.07547
## 270     2225   8.69811
## 271     2230   9.75472
## 272     2235   2.20755
## 273     2240   0.32075
## 274     2245   0.11321
## 275     2250   1.60377
## 276     2255   4.60377
## 277     2300   3.30189
## 278     2305   2.84906
## 279     2310   0.00000
## 280     2315   0.83019
## 281     2320   0.96226
## 282     2325   1.58491
## 283     2330   2.60377
## 284     2335   4.69811
## 285     2340   3.30189
## 286     2345   0.64151
## 287     2350   0.22642
## 288     2355   1.07547
```



```r
aggregate(steps ~ date, activity, median)
```

```
##          date steps
## 1  2012-10-02     0
## 2  2012-10-03     0
## 3  2012-10-04     0
## 4  2012-10-05     0
## 5  2012-10-06     0
## 6  2012-10-07     0
## 7  2012-10-09     0
## 8  2012-10-10     0
## 9  2012-10-11     0
## 10 2012-10-12     0
## 11 2012-10-13     0
## 12 2012-10-14     0
## 13 2012-10-15     0
## 14 2012-10-16     0
## 15 2012-10-17     0
## 16 2012-10-18     0
## 17 2012-10-19     0
## 18 2012-10-20     0
## 19 2012-10-21     0
## 20 2012-10-22     0
## 21 2012-10-23     0
## 22 2012-10-24     0
## 23 2012-10-25     0
## 24 2012-10-26     0
## 25 2012-10-27     0
## 26 2012-10-28     0
## 27 2012-10-29     0
## 28 2012-10-30     0
## 29 2012-10-31     0
## 30 2012-11-02     0
## 31 2012-11-03     0
## 32 2012-11-05     0
## 33 2012-11-06     0
## 34 2012-11-07     0
## 35 2012-11-08     0
## 36 2012-11-11     0
## 37 2012-11-12     0
## 38 2012-11-13     0
## 39 2012-11-15     0
## 40 2012-11-16     0
## 41 2012-11-17     0
## 42 2012-11-18     0
## 43 2012-11-19     0
## 44 2012-11-20     0
## 45 2012-11-21     0
## 46 2012-11-22     0
## 47 2012-11-23     0
## 48 2012-11-24     0
## 49 2012-11-25     0
## 50 2012-11-26     0
## 51 2012-11-27     0
## 52 2012-11-28     0
## 53 2012-11-29     0
```



**What is the average daily activity pattern?**

-Make a time series plot (i.e. type = "l") of the 5-minute interval (x-axis) and the average number of steps taken, averaged across all days (y-axis)

```r
plot(aggregate(steps ~ interval, activity, mean))
```

![plot of chunk unnamed-chunk-6](figure/unnamed-chunk-6.png) 


-Which 5-minute interval, on average across all the days in the dataset, contains the maximum number of steps?


```r

maxNumberOfSteps <- max(meanActivity$steps)
meanActivity$interval[meanActivity$steps == maxNumberOfSteps]
```

```
## [1] 835
```


**Imputing missing values**

*Note that there are a number of days/intervals where there are missing values (coded as NA). The presence of missing days may introduce bias into some calculations or summaries of the data.*

- Calculate and report the total number of missing values in the dataset (i.e. the total number of rows with NAs)


```r
sum(is.na(activity$steps))
```

```
## [1] 2304
```


- Devise a strategy for filling in all of the missing values in the dataset. The strategy does not need to be sophisticated. For example, you could use the mean/median for that day, or the mean for that 5-minute interval, etc.
Create a new dataset that is equal to the original dataset but with the missing data filled in.

```r
completeActivity <- activity
for (i in 1:length(completeActivity$steps)) {
    if (is.na(completeActivity[i, "steps"])) {
        completeActivity[i, "steps"] = round(meanActivity[meanActivity$interval == 
            completeActivity[i, "interval"], "steps"])
    }
}
```



Make a histogram of the total number of steps taken each day and Calculate and report the mean and median total number of steps taken per day. Do these values differ from the estimates from the first part of the assignment? What is the impact of imputing missing data on the estimates of the total daily number of steps?


```r
hist(completeActivity$steps)
```

![plot of chunk unnamed-chunk-10](figure/unnamed-chunk-10.png) 

```r
aggregate(steps ~ interval, completeActivity, mean)
```

```
##     interval     steps
## 1          0   1.75410
## 2          5   0.29508
## 3         10   0.11475
## 4         15   0.13115
## 5         20   0.06557
## 6         25   2.08197
## 7         30   0.59016
## 8         35   0.88525
## 9         40   0.00000
## 10        45   1.40984
## 11        50   0.26230
## 12        55   0.11475
## 13       100   0.27869
## 14       105   0.72131
## 15       110   0.13115
## 16       115   0.29508
## 17       120   0.00000
## 18       125   1.09836
## 19       130   1.85246
## 20       135   0.14754
## 21       140   0.14754
## 22       145   0.32787
## 23       150   0.22951
## 24       155   0.00000
## 25       200   0.00000
## 26       205   0.00000
## 27       210   1.11475
## 28       215   0.00000
## 29       220   0.00000
## 30       225   0.11475
## 31       230   0.00000
## 32       235   0.19672
## 33       240   0.00000
## 34       245   0.00000
## 35       250   1.60656
## 36       255   0.95082
## 37       300   0.00000
## 38       305   0.00000
## 39       310   0.00000
## 40       315   0.00000
## 41       320   0.18033
## 42       325   0.67213
## 43       330   1.67213
## 44       335   0.63934
## 45       340   0.42623
## 46       345   0.06557
## 47       350   0.00000
## 48       355   0.00000
## 49       400   1.16393
## 50       405   0.95082
## 51       410   2.62295
## 52       415   0.00000
## 53       420   0.29508
## 54       425   0.31148
## 55       430   4.09836
## 56       435   0.70492
## 57       440   3.42623
## 58       445   0.85246
## 59       450   3.09836
## 60       455   1.09836
## 61       500   0.00000
## 62       505   1.62295
## 63       510   3.00000
## 64       515   2.21311
## 65       520   3.27869
## 66       525   2.96721
## 67       530   2.08197
## 68       535   6.04918
## 69       540  16.01639
## 70       545  18.29508
## 71       550  39.39344
## 72       555  44.42623
## 73       600  31.42623
## 74       605  49.22951
## 75       610  53.80328
## 76       615  63.39344
## 77       620  49.96721
## 78       625  47.06557
## 79       630  52.13115
## 80       635  39.29508
## 81       640  44.01639
## 82       645  44.14754
## 83       650  37.31148
## 84       655  49.03279
## 85       700  43.83607
## 86       705  44.32787
## 87       710  50.57377
## 88       715  54.57377
## 89       720  49.93443
## 90       725  50.98361
## 91       730  55.72131
## 92       735  44.27869
## 93       740  52.22951
## 94       745  69.60656
## 95       750  57.86885
## 96       755  56.13115
## 97       800  73.32787
## 98       805  68.18033
## 99       810 129.37705
## 100      815 157.59016
## 101      820 171.13115
## 102      825 155.34426
## 103      830 177.26230
## 104      835 206.14754
## 105      840 195.93443
## 106      845 179.62295
## 107      850 183.34426
## 108      855 167.01639
## 109      900 143.39344
## 110      905 124.03279
## 111      910 109.09836
## 112      915 108.09836
## 113      920 103.75410
## 114      925  95.96721
## 115      930  66.18033
## 116      935  45.19672
## 117      940  24.81967
## 118      945  38.78689
## 119      950  34.98361
## 120      955  21.04918
## 121     1000  40.62295
## 122     1005  26.98361
## 123     1010  42.36066
## 124     1015  52.70492
## 125     1020  38.93443
## 126     1025  50.81967
## 127     1030  44.24590
## 128     1035  37.36066
## 129     1040  34.73770
## 130     1045  28.29508
## 131     1050  25.08197
## 132     1055  31.95082
## 133     1100  31.31148
## 134     1105  29.72131
## 135     1110  21.27869
## 136     1115  25.60656
## 137     1120  28.32787
## 138     1125  26.40984
## 139     1130  33.37705
## 140     1135  49.98361
## 141     1140  42.03279
## 142     1145  44.65574
## 143     1150  46.03279
## 144     1155  59.16393
## 145     1200  63.88525
## 146     1205  87.73770
## 147     1210  94.86885
## 148     1215  92.80328
## 149     1220  63.34426
## 150     1225  50.14754
## 151     1230  54.40984
## 152     1235  32.36066
## 153     1240  26.59016
## 154     1245  37.77049
## 155     1250  45.04918
## 156     1255  67.24590
## 157     1300  42.29508
## 158     1305  39.90164
## 159     1310  43.22951
## 160     1315  40.98361
## 161     1320  46.21311
## 162     1325  56.37705
## 163     1330  42.78689
## 164     1335  25.11475
## 165     1340  39.96721
## 166     1345  53.60656
## 167     1350  47.27869
## 168     1355  60.83607
## 169     1400  55.78689
## 170     1405  51.96721
## 171     1410  43.63934
## 172     1415  48.73770
## 173     1420  35.40984
## 174     1425  37.60656
## 175     1430  41.86885
## 176     1435  27.57377
## 177     1440  17.09836
## 178     1445  26.06557
## 179     1450  43.67213
## 180     1455  43.80328
## 181     1500  30.01639
## 182     1505  36.06557
## 183     1510  35.42623
## 184     1515  38.86885
## 185     1520  45.96721
## 186     1525  47.78689
## 187     1530  48.11475
## 188     1535  65.27869
## 189     1540  82.91803
## 190     1545  98.70492
## 191     1550 102.09836
## 192     1555  83.96721
## 193     1600  62.11475
## 194     1605  64.11475
## 195     1610  74.60656
## 196     1615  63.14754
## 197     1620  56.91803
## 198     1625  59.80328
## 199     1630  43.88525
## 200     1635  38.62295
## 201     1640  44.70492
## 202     1645  45.39344
## 203     1650  46.18033
## 204     1655  43.72131
## 205     1700  46.67213
## 206     1705  56.26230
## 207     1710  50.75410
## 208     1715  61.19672
## 209     1720  72.75410
## 210     1725  78.95082
## 211     1730  68.95082
## 212     1735  59.70492
## 213     1740  75.08197
## 214     1745  56.57377
## 215     1750  34.80328
## 216     1755  37.39344
## 217     1800  40.72131
## 218     1805  58.01639
## 219     1810  74.73770
## 220     1815  85.27869
## 221     1820  59.22951
## 222     1825  67.80328
## 223     1830  77.73770
## 224     1835  74.21311
## 225     1840  85.29508
## 226     1845  99.39344
## 227     1850  86.63934
## 228     1855  85.65574
## 229     1900  84.88525
## 230     1905  77.85246
## 231     1910  58.03279
## 232     1915  53.31148
## 233     1920  36.27869
## 234     1925  20.75410
## 235     1930  27.34426
## 236     1935  40.01639
## 237     1940  30.18033
## 238     1945  25.60656
## 239     1950  45.70492
## 240     1955  33.59016
## 241     2000  19.67213
## 242     2005  19.01639
## 243     2010  19.29508
## 244     2015  33.29508
## 245     2020  26.83607
## 246     2025  21.14754
## 247     2030  27.26230
## 248     2035  21.29508
## 249     2040  19.60656
## 250     2045  21.27869
## 251     2050  32.26230
## 252     2055  20.13115
## 253     2100  15.95082
## 254     2105  17.19672
## 255     2110  23.39344
## 256     2115  19.21311
## 257     2120  12.39344
## 258     2125   8.01639
## 259     2130  14.70492
## 260     2135  16.26230
## 261     2140   8.72131
## 262     2145   7.81967
## 263     2150   8.11475
## 264     2155   2.67213
## 265     2200   1.39344
## 266     2205   3.72131
## 267     2210   4.83607
## 268     2215   8.57377
## 269     2220   7.06557
## 270     2225   8.73770
## 271     2230   9.78689
## 272     2235   2.18033
## 273     2240   0.27869
## 274     2245   0.09836
## 275     2250   1.65574
## 276     2255   4.65574
## 277     2300   3.26230
## 278     2305   2.86885
## 279     2310   0.00000
## 280     2315   0.85246
## 281     2320   0.96721
## 282     2325   1.63934
## 283     2330   2.65574
## 284     2335   4.73770
## 285     2340   3.26230
## 286     2345   0.68852
## 287     2350   0.19672
## 288     2355   1.06557
```

```r
aggregate(steps ~ date, completeActivity, median)
```

```
##          date steps
## 1  2012-10-01  34.5
## 2  2012-10-02   0.0
## 3  2012-10-03   0.0
## 4  2012-10-04   0.0
## 5  2012-10-05   0.0
## 6  2012-10-06   0.0
## 7  2012-10-07   0.0
## 8  2012-10-08  34.5
## 9  2012-10-09   0.0
## 10 2012-10-10   0.0
## 11 2012-10-11   0.0
## 12 2012-10-12   0.0
## 13 2012-10-13   0.0
## 14 2012-10-14   0.0
## 15 2012-10-15   0.0
## 16 2012-10-16   0.0
## 17 2012-10-17   0.0
## 18 2012-10-18   0.0
## 19 2012-10-19   0.0
## 20 2012-10-20   0.0
## 21 2012-10-21   0.0
## 22 2012-10-22   0.0
## 23 2012-10-23   0.0
## 24 2012-10-24   0.0
## 25 2012-10-25   0.0
## 26 2012-10-26   0.0
## 27 2012-10-27   0.0
## 28 2012-10-28   0.0
## 29 2012-10-29   0.0
## 30 2012-10-30   0.0
## 31 2012-10-31   0.0
## 32 2012-11-01  34.5
## 33 2012-11-02   0.0
## 34 2012-11-03   0.0
## 35 2012-11-04  34.5
## 36 2012-11-05   0.0
## 37 2012-11-06   0.0
## 38 2012-11-07   0.0
## 39 2012-11-08   0.0
## 40 2012-11-09  34.5
## 41 2012-11-10  34.5
## 42 2012-11-11   0.0
## 43 2012-11-12   0.0
## 44 2012-11-13   0.0
## 45 2012-11-14  34.5
## 46 2012-11-15   0.0
## 47 2012-11-16   0.0
## 48 2012-11-17   0.0
## 49 2012-11-18   0.0
## 50 2012-11-19   0.0
## 51 2012-11-20   0.0
## 52 2012-11-21   0.0
## 53 2012-11-22   0.0
## 54 2012-11-23   0.0
## 55 2012-11-24   0.0
## 56 2012-11-25   0.0
## 57 2012-11-26   0.0
## 58 2012-11-27   0.0
## 59 2012-11-28   0.0
## 60 2012-11-29   0.0
## 61 2012-11-30  34.5
```


Lets compare mean and median total number of steps:

- *NA values were filled with mean values for missing periods*

- *Inputed values does differ from the estimates from the first part of the assignment, since missing values are filledand mean values are changed:*

```r
all.equal(aggregate(steps ~ interval, completeActivity, mean), aggregate(steps ~ 
    interval, activity, mean))
```

```
## [1] "Component \"steps\": Mean relative difference: 0.0008309"
```


- *Ther is no impact of imputing missing data on the estimates of the total daily number of steps and median values are changed:*

```r
all.equal(aggregate(steps ~ interval, completeActivity, median), aggregate(steps ~ 
    interval, activity, median))
```

```
## [1] "Component \"steps\": Mean relative difference: 0.4633"
```



**Are there differences in activity patterns between weekdays and weekends?**

*For this part the weekdays() function may be of some help here. Use the dataset with the filled-in missing values for this part.

Create a new factor variable in the dataset with two levels – “weekday” and “weekend” indicating whether a given date is a weekday or weekend day.*

Make a panel plot containing a time series plot (i.e. type = "l") of the 5-minute interval (x-axis) and the average number of steps taken, averaged across all weekday days or weekend days (y-axis). 


```r
weekend_days <- c("Saturday", "Sunday")

completeActivity$day_type <- (ifelse((weekdays(as.Date(completeActivity[, "date"])) %in% 
    weekend_days), "weekend", "weekday"))

xyplot(steps ~ interval | day_type == "weekend", data = completeActivity, type = "l")
```

![plot of chunk unnamed-chunk-13](figure/unnamed-chunk-13.png) 


As we can notice from the graps, there is more activity in the morning hours and in the evening over the weekday comparing to weekends. On the other side, there are more activity in the afternoon over the weekends. 

This can be explaind by the later weakening over the weekends.
