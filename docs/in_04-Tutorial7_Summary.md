

# Summarizing Data {#T7_summary}

Before analyzing a dataset, it's essential to understand its structure, size, and data types. This tutorial will guide you through:

1.  Viewing the dataset.
2.  Checking its dimensions, column names, and structure.
3.  Understanding data types and modifying them if necessary.
4.  Preparing for summary statistics.

### Suggested libraries


``` r
library(dplyr)
library(skimr)
library(GGally)
```

### How to edit

The tutorial is based on a small dataset called `test_data` with these four columns,

-   `Make` (categorical)
-   `MPG` (numerical)
-   `Cylinders` (categorical)
-   `Transmission` (categorical)

So to edit for your code, all you need to do is replace `test_data` with the name of your spreadsheet/data-frame, and to replace the variable you are looking at with your column name e,g,

`test_data$MPG` goes to `WhateverYourDataIsCalled$ColumnName`

Here is the full dataset.




``` r
print(test_data)
```

```
##      Make MPG Cylinders Transmission
## 1  Toyota  30         4         Auto
## 2    Ford  25         6       Manual
## 3   Honda  27         4         Auto
## 4   Chevy  22         8         Auto
## 5  Nissan  29         4       Manual
## 6     BMW  24         6       Manual
## 7  Toyota  29         8         Auto
## 8    Ford  23         4         Auto
## 9   Honda  25         5         Auto
## 10 Toyota  25         4       Manual
```

<br>

## How to view data

To explore the dataset interactively, you can:

-   **Open it in the RStudio Data Viewer**:\
    Run `View(test_data)` in the console.\
    *Note: `View()` should not be placed inside a code chunk because it only works interactively in RStudio and does not produce console output. It often breaks the knitting process*

-   **See a tabular preview in the environment pane**:\
    Click on `test_data` in the environment tab.

-   **Print the entire dataset** (not recommended for large datasets):


``` r
# this will only show the first page
test_data
```

```
##      Make MPG Cylinders Transmission
## 1  Toyota  30         4         Auto
## 2    Ford  25         6       Manual
## 3   Honda  27         4         Auto
## 4   Chevy  22         8         Auto
## 5  Nissan  29         4       Manual
## 6     BMW  24         6       Manual
## 7  Toyota  29         8         Auto
## 8    Ford  23         4         Auto
## 9   Honda  25         5         Auto
## 10 Toyota  25         4       Manual
```

-   **View only the first six rows**:


``` r
head(test_data)
```

```
##     Make MPG Cylinders Transmission
## 1 Toyota  30         4         Auto
## 2   Ford  25         6       Manual
## 3  Honda  27         4         Auto
## 4  Chevy  22         8         Auto
## 5 Nissan  29         4       Manual
## 6    BMW  24         6       Manual
```

<br>


### Print column names 

To see what columns exist:


``` r
names(test_data)
```

```
## [1] "Make"         "MPG"          "Cylinders"    "Transmission"
```



## How to summarise data

<br>

### Number of Rows/Columns

To find out how many rows and columns there are:


``` r
nrow(test_data)  # Number of rows
```

```
## [1] 10
```

``` r
ncol(test_data)  # Number of columns
```

```
## [1] 4
```

``` r
dim(test_data)   # Dimensions (rows, columns)
```

```
## [1] 10  4
```

<br>



### Checking data types

Each column in a dataset has a specific data type (e.g., numeric, character, factor). "Factor" is the R jargon for variables that have a fixed number of unique values (e.g., categories/groups/families).

We can check the data types using:


``` r
sapply(test_data, class)
```

```
##         Make          MPG    Cylinders Transmission 
##     "factor"    "numeric"     "factor"  "character"
```

<br>

If categorical variables are not stored as factors, we can explicitly define them, where levels is the ORDER I want them to be in.


``` r
test_data$Cylinders    <- factor(test_data$Cylinders, levels = c(4, 6, 8))
test_data$Transmission <- factor(test_data$Transmission, levels = c("Auto", "Manual"))
```

This ensures:

-   Consistent ordering of categorical levels.
-   Avoiding unintended sorting in plots or models.

Similarly, if data "should" be numeric, but isn't for some reason, we can convert it using as.numeric() etc.

<br><br>




## Summary commands

There are many commands!  You don't need all of these - choose your favourite :)

### str()


To get a compact summary of the dataset, `str()` provides an overview, including the number of observations, variables, and data types.


``` r
str(test_data)
```

```
## 'data.frame':	10 obs. of  4 variables:
##  $ Make        : Factor w/ 6 levels "BMW","Chevy",..: 6 3 4 2 5 1 6 3 4 6
##  $ MPG         : num  30 25 27 22 29 24 29 23 25 25
##  $ Cylinders   : Factor w/ 3 levels "4","6","8": 1 2 1 3 1 2 3 1 NA 1
##  $ Transmission: Factor w/ 2 levels "Auto","Manual": 1 2 1 1 2 2 1 1 1 2
```

<br>

### dplyr::glimpse()

Another alternative is `glimpse()` (from the `dplyr` package, so you have to have run the library code chunk first):


``` r
glimpse(test_data)
```

```
## Rows: 10
## Columns: 4
## $ Make         <fct> Toyota, Ford, Honda, Chevy, Nissan, BMW, Toyota, Ford, Ho…
## $ MPG          <dbl> 30, 25, 27, 22, 29, 24, 29, 23, 25, 25
## $ Cylinders    <fct> 4, 6, 4, 8, 4, 6, 8, 4, NA, 4
## $ Transmission <fct> Auto, Manual, Auto, Auto, Manual, Manual, Auto, Auto, Aut…
```
<br>

### summary()


We can use the `summary()` function to get a quick overview of numerical and factor variables.


``` r
summary(test_data)
```

```
##      Make        MPG        Cylinders Transmission
##  BMW   :1   Min.   :22.00   4   :5    Auto  :6    
##  Chevy :1   1st Qu.:24.25   6   :2    Manual:4    
##  Ford  :2   Median :25.00   8   :2                
##  Honda :2   Mean   :25.90   NA's:1                
##  Nissan:1   3rd Qu.:28.50                         
##  Toyota:3   Max.   :30.00
```

<br>


### skimr:skim()`

The `skim` command from the `skimr` package provides an easy and readable summary of the dataset


``` r
skim(test_data)
```


Table: (\#tab:unnamed-chunk-13)Data summary

|                         |          |
|:------------------------|:---------|
|Name                     |test_data |
|Number of rows           |10        |
|Number of columns        |4         |
|_______________________  |          |
|Column type frequency:   |          |
|factor                   |3         |
|numeric                  |1         |
|________________________ |          |
|Group variables          |None      |


**Variable type: factor**

|skim_variable | n_missing| complete_rate|ordered | n_unique|top_counts                     |
|:-------------|---------:|-------------:|:-------|--------:|:------------------------------|
|Make          |         0|           1.0|FALSE   |        6|Toy: 3, For: 2, Hon: 2, BMW: 1 |
|Cylinders     |         1|           0.9|FALSE   |        3|4: 5, 6: 2, 8: 2               |
|Transmission  |         0|           1.0|FALSE   |        2|Aut: 6, Man: 4                 |


**Variable type: numeric**

|skim_variable | n_missing| complete_rate| mean|   sd| p0|   p25| p50|  p75| p100|hist  |
|:-------------|---------:|-------------:|----:|----:|--:|-----:|---:|----:|----:|:-----|
|MPG           |         0|             1| 25.9| 2.73| 22| 24.25|  25| 28.5|   30|▃▇▁▂▆ |

<br>


### Frequency tables


We can use `table()` or `dplyr::count()` to summarize categorical variables. e.g. count how many rows there are in different categories. This is especially useful for categorical data.

The easiest way to do this is using the `table` command. 


``` r
table(test_data$Transmission)
```

```
## 
##   Auto Manual 
##      6      4
```

Shows there are three rows with automatic cars and three with manual, 

We can also make two way tables


``` r
table(test_data$Transmission, test_data$Cylinders)
```

```
##         
##          4 6 8
##   Auto   3 0 2
##   Manual 2 2 0
```

So there are 2 cars that are automatic with four cylinders. 

We can also use the `count` function in the dplyr package.


``` r
test_data %>% count(Transmission)
```

```
##   Transmission n
## 1         Auto 6
## 2       Manual 4
```





### Calculate your own

Alternatively, we can calculate specific summary statistics manually using base R and `dplyr`.


``` r
mean  (test_data$MPG, na.rm=TRUE)  # Mean MPG, ignoring missing values
```

```
## [1] 25.9
```

``` r
median(test_data$MPG, na.rm=TRUE)  # Median MPG, ignoring missing values
```

```
## [1] 25
```

``` r
sd    (test_data$MPG, na.rm=TRUE)      # Standard deviation, ignoring missing values
```

```
## [1] 2.726414
```

``` r
range (test_data$MPG, na.rm=TRUE)   # Minimum and maximum, ignoring missing values
```

```
## [1] 22 30
```


### Grouped Summary Statistics

Finally,  we can also compute statistics such as the mean, maximum, and minimum values for different groups.

Using `group_by()` and `summarise()` from dplyr() , we can compute statistics for each species:


``` r
test_data %>%
  dplyr::group_by(Transmission) %>%
  dplyr::summarise(
    Mean_MPG = mean(MPG),
    Median_MPG = median(MPG),
    Count = n()
  )
```

```
## # A tibble: 2 × 4
##   Transmission Mean_MPG Median_MPG Count
##   <fct>           <dbl>      <dbl> <int>
## 1 Auto             26           26     6
## 2 Manual           25.8         25     4
```

<br>



