# Getting started

I will be using R in my project. Firstly, I import the relevant libraries and the data:

_Importing relevant libraries_

```r
# Install libraries
install.packages("RColorBrewer")

# Import libraries
library(readxl) # to read excel files
library(dplyr) # to carry out data wrangling functions
library(magrittr) # to write pipes (denoted as %>%)
library(ggplot2) # to draw graphs
library(stringr) # to wrangle strings
library(tidyr) # to tidy data
library(RColorBrewer) # for color palette
```

_Importing data_

```r
# Import dataset
data_2014_2017 <- read_excel("data_2014_2017.xlsx")
data_2017_2019 <- read_excel("data_2017_2019.xlsx")
```

