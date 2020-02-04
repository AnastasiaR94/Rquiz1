##First Quiz R course

# what are the column names of the dataset? 
mydata= read.csv("hw1_data.csv")
head(mydata)

#Extract the first two rows of the data set
mydata[1:2, ]

#How many rows are in the data?
nrow(mydata)

#Extract the last two rows of the data set
rows <- nrow(mydata)
> mydata[(rows-1):rows,]
        
        or
        
tail(mydata)

#What is the value of Ozone in the 47th row?
mydata[47, 1]

#How many missing values are in the comun Ozone?
sum(!complete.cases(mydata[, 1]))

# What is the mean of the Ozone column in this dataset? Exclude missing values (coded as NA) from this calculation.
mean(mydata[complete.cases(mydata), 1])

#Extract the subset of rows of the data frame where Ozone values are above 31 and Temp values are above 90. What is the mean of Solar.R in this subset?
mean(subset(mydata, Ozone>30 & Temp>90)[, 2])

#What is the mean of Temp when the month is 6?
mean(subset(mydata, Month==6)[, 4])

#What was the maximum ozone value in the month of May (i.e. Month is equal to 5)?
 mydata = read.csv("hw1_data.csv")
sub = subset(mydata, Month == 5 & !is.na(Ozone), select = Ozone)
apply(sub, 2, max)
