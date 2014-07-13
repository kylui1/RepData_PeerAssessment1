# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data


```r
data =  read.csv("activity.csv", stringsAsFactors=FALSE)
data$date= as.Date(data$date, format="%Y-%m-%d")
```


## What is mean total number of steps taken per day?

The histogram of the total number of steps taken each day

```r
data2 = data[!is.na(data$steps),1:3]
result = tapply(data2$steps, list(data2$date), sum)
hist(result, xlab = "Total Steps Per Day", ylab = "Frequency", 
              main="Total Number of Steps Per Day")
```

![plot of chunk unnamed-chunk-2](figure/unnamed-chunk-2.png) 

```r
cat("Mean is", mean(result))
```

```
## Mean is 10766
```

```r
cat("Median is", median(result))
```

```
## Median is 10765
```

## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
