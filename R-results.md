R Code for Data Analysis.

Loading Data and Seperating Groups

```r
> data = read.csv("~/Desktop/School/HCI/HCI-Stats.csv")
> group_A = data[data$A_B==0,]
> group_B = data[data$A_B==1,]

```

CHAT:
IVs: A (List) vs B (Grouped by Interest)
[x] Chat Time

```r

t.test(group_A$Usability_Chat_Time, group_B$Usability_Chat_Time)

    data:  group_A$Usability_Chat_Time and group_B$Usability_Chat_Time
    t = -1.485, df = 9.1115, p-value =
    0.1713
    alternative hypothesis: true difference in means is not equal to 0
    95 percent confidence interval:
    -27.725053   5.725053
    sample estimates:
    mean of x mean of y
        33        44

boxplot(Usability_Chat_Time~A_B, data=data, main="Comparison of Chat Task Time", xlab="Interface Type", ylab="Time (in seconds)", names=c("A (List Layout)", "B (Grouped by Interest)"), col=c("#E14C1E", "#1EB3E1"))
```

[x] Chat Error

### Significant!

```r

t.test(group_A$Usability_Chat_Error, group_B$Usability_Chat_Error)

	Welch Two Sample t-test

    data:  group_A$Usability_Chat_Error and group_B$Usability_Chat_Error
    t = -2.4445, df = 9.7168, p-value =
    0.03524
    alternative hypothesis: true difference in means is not equal to 0
    95 percent confidence interval:
    -2.23428645 -0.09904688
    sample estimates:
    mean of x mean of y
    1.000000  2.166667

boxplot(Usability_Chat_Error~A_B, data=data, main="Chat Task: Number of Errors", xlab="Interface Type", ylab="Number of Errors", names=c("A (List Layout)", "B (Grouped by Interest)"), col=c("#E14C1E", "#1EB3E1"))
```

[x] Chat SR

```r

t.test(group_A$Usability_Chat_SR, group_B$Usability_Chat_SR)

    data:  group_A$Usability_Chat_SR and group_B$Usability_Chat_SR
    t = 1.1767, df = 8.8002, p-value =
    0.2702
    alternative hypothesis: true difference in means is not equal to 0
    95 percent confidence interval:
    -0.9291363  2.9291363
    sample estimates:
    mean of x mean of y
    5.833333  4.833333

boxplot(Usability_Chat_SR~A_B, data=data, main="Comparison of Chat Self-Reported Scores", xlab="Interface Type", ylim=c(1,7), ylab="LIKERT Score (1 - 7)", names=c("A (List Layout)", "B (Grouped by Interest)"), col=c("#E14C1E", "#1EB3E1"))
```

[x] Chat Completion Rate

```r
sum(group_A$Usability_Chat_Complete==1) / length(group_A$Usability_Chat_Complete)
sum(group_B$Usability_Chat_Complete==1) / length(group_B$Usability_Chat_Complete)
```

Friends List:
IVs: A (List) vs B (Carousel)
[x] Friend Time

```r

t.test(group_A$Usability_Friend_Time, group_B$Usability_Friend_Time)

    data:  group_A$Usability_Friend_Time and group_B$Usability_Friend_Time
    t = 0.16709, df = 6.3042, p-value =
    0.8725
    alternative hypothesis: true difference in means is not equal to 0
    95 percent confidence interval:
    -35.93293  41.26626
    sample estimates:
    mean of x mean of y
    29.00000  26.33333

boxplot(Usability_Friend_Time~A_B, data=data, main="Comparison of Friends List Task Time", xlab="Interface Type", ylab="Time (in seconds)", names=c("A (List Layout)", "B (Carousel Layout)"), col=c("#E14C1E", "#1EB3E1"))
```

[x] Friend Error

```r

t.test(group_A$Usability_Friend_Error, group_B$Usability_Friend_Error)

    data:  group_A$Usability_Friend_Error and group_B$Usability_Friend_Error
    t = 1.2403, df = 9.4944, p-value = 0.2446
    alternative hypothesis: true difference in means is not equal to 0
    95 percent confidence interval:
    -0.5396234  1.8729567
    sample estimates:
    mean of x mean of y
    1.3333333 0.6666667

boxplot(Usability_Friend_Error~A_B, data=data, main="Friends List Task: Number of Errors", xlab="Interface Type", ylab="Number of Errors", names=c("A (List Layout)", "B (Carousel Layout)"), col=c("#E14C1E", "#1EB3E1"))
```

[x] Friend SR

```r

t.test(group_A$Usability_Friend_SR, group_B$Usability_Friend_SR)

    data:  group_A$Usability_Friend_SR and group_B$Usability_Friend_SR
    t = 1.6977, df = 7.8108, p-value =
    0.1289
    alternative hypothesis: true difference in means is not equal to 0
    95 percent confidence interval:
    -0.424689  2.758022
    sample estimates:
    mean of x mean of y
    5.333333  4.166667

boxplot(Usability_Friend_SR~A_B, data=data, main="Comparison of Friends List Self-Reported Scores", xlab="Interface Type", ylim=c(1,7), ylab="LIKERT Score (1 - 7)", names=c("A (List Layout)", "B (Carousel Layout)"), col=c("#E14C1E", "#1EB3E1"))
```

[ ] Friend Completion Rate

```r
sum(group_A$Usability_Friend_Complete==1) / length(group_A$Usability_Friend_Complete)
sum(group_B$Usability_Friend_Complete==1) / length(group_B$Usability_Friend_Complete)
```

Interest Selection:
A (Grid) vs B (List)

[x] Interest Time

### T-test Result & Boxplot

```r

t.test(group_A$Usability_Interest_Time, group_B$Usability_Interest_Time)

    data:  group_A$Usability_Interest_Time and group_B$Usability_Interest_Time
    t = -0.29799, df = 9.4091, p-value =
    0.7722
    alternative hypothesis: true difference in means is not equal to 0
    95 percent confidence interval:
    -12.812164   9.812164
    sample estimates:
    mean of x mean of y
    18.83333  20.33333

boxplot(Usability_Interest_Time~A_B, data=data, main="Comparison of Interest Selection Task Time", xlab="Interface Type", ylab="Time (in seconds)", names=c("A (Grid Layout)", "B (List Layout)"), col=c("#E14C1E", "#1EB3E1"))
```

[x] Interest Error

```r

t.test(group_A$Usability_Interest_Error, group_B$Usability_Interest_Error)

    data:  group_A$Usability_Interest_Error and group_B$Usability_Interest_Error
    t = -0.84515, df = 8.4483, p-value =
    0.4213
    alternative hypothesis: true difference in means is not equal to 0
    95 percent confidence interval:
    -1.2345015  0.5678349
    sample estimates:
    mean of x mean of y
    0.3333333 0.6666667

boxplot(Usability_Interest_Error~A_B, data=data, main="Interest Selection Task: Number of Errors", xlab="Interface Type", ylab="Number of Errors", names=c("A (Grid Layout)", "B (List Layout)"), col=c("#E14C1E", "#1EB3E1"))
```

[x] Interest SR

# Significant

```r

t.test(group_A$Usability_Interest_SR, group_B$Usability_Interest_SR)

    data:  group_A$Usability_Interest_SR and group_B$Usability_Interest_SR
    t = 4.0249, df = 8.8527, p-value =
    0.003099
    alternative hypothesis: true difference in means is not equal to 0
    95 percent confidence interval:
    0.6548005 2.3451995
    sample estimates:
    mean of x mean of y
    6.333333  4.833333


boxplot(Usability_Interest_SR~A_B, data=data, main="Comparison of Interest Selection Self-Reported Scores", xlab="Interface Type", ylim=c(1,7), ylab="LIKERT Score (1 - 7)", names=c("A (Grid Layout)", "B (List Layout)"), col=c("#E14C1E", "#1EB3E1"))
```

[x] Interest Completion Rate

```r
sum(group_A$Usability_Interest_Complete==1) / length(group_A$Usability_Interest_Complete)
sum(group_B$Usability_Interest_Complete==1) / length(group_B$Usability_Interest_Complete)
```

Final Task:
[ ] Final Task Time

```r
t.test(group_A$Final_Task_Time, group_B$Final_Task_Time)

	Welch Two Sample t-test

data:  group_A$Final_Task_Time and group_B$Final_Task_Time
t = 0.25644, df = 9.2702, p-value = 0.8032
alternative hypothesis: true difference in means is not equal to 0
95 percent confidence interval:
 -23.34681  29.34681
sample estimates:
mean of x mean of y
 55.16667  52.16667
```

[ ] Final Task Error

```r
t.test(group_A$Final_Task_Error, group_B$Final_Task_Error)

	Welch Two Sample t-test

data:  group_A$Final_Task_Error and group_B$Final_Task_Error
t = 1.1028, df = 6.5253, p-value = 0.3091
alternative hypothesis: true difference in means is not equal to 0
95 percent confidence interval:
 -0.588095  1.588095
sample estimates:
mean of x mean of y
1.3333333 0.8333333
```

[ ] Final Task Completion

```r
sum(group_A$Final_Task_Complete) / length(group_A$Final_Task_Complete)
sum(group_B$Final_Task_Complete) / length(group_B$Final_Task_Complete)
```

### Demographic Data

[x] Gender (Pie):

```r
> men = data[data$PAR_Gen==1,]
> women = data[data$PAR_Gen==0,]
> num_of_women = length(women$PAR_ID)
> num_of_men = length(men$PAR_ID)

# Pie Chart with Percentages
> slices <- c(num_of_women, num_of_men)
> lbls <- c("Female", "Male")
> pct <- round(slices/sum(slices)*100)
> lbls <- paste(lbls, pct) # add percents to labels
> lbls <- paste(lbls,"%",sep="") # add % to labels
> pie(slices,labels = lbls, col=c("#FFC3E1", "#b4f9ff"),
+     main="Participant Gender")
```

[x] Age (Histogram):

```r
ages = data$PAR_Age
hist(ages, main="Frequency of Participant Ages", xlab="Age (in years)", ylab="Frequency", col="#ACC3A6", ylim=c(0,5), breaks=5)
```

[x] Education (Pie):

```r
> # Pie Chart with Percentages
> hs = length(data[data$PAR_Edu==0,]$PAR_ID)
> bachelors = length(data[data$PAR_Edu==1,]$PAR_ID)
> masters = length(data[data$PAR_Edu==2,]$PAR_ID)
> phd = length(data[data$PAR_Edu==3,]$PAR_ID)
> slices <- c(hs, bachelors, masters, phd)
> lbls <- c("High School Diploma", "Bachelors Degree", "Masters Degree", "Doctorate")
> pct <- round(slices/sum(slices)*100)
> lbls <- paste(lbls, pct) # add percents to labels
> lbls <- paste(lbls,"%",sep="") # add % to labels
> pie(slices,labels = lbls, col=c("#545E75", "#304D6D", "#63ADF2", "#A7CCED"),
+ main="Participant Education Level")
```

[x] Race (Pie):

```r
> white = length(data[data$PAR_Race_Eth==0,]$PAR_ID)
> black = length(data[data$PAR_Race_Eth==1,]$PAR_ID)
> asian = length(data[data$PAR_Race_Eth==2,]$PAR_ID)
> hispanic = length(data[data$PAR_Race_Eth==3,]$PAR_ID)
> slices <- c(white, asian, black, hispanic)
> lbls <- c("White", "Asian", "Black", "Hispanic/Latino")
> pct <- round(slices/sum(slices)*100)
> lbls <- paste(lbls, pct) # add percents to labels
> lbls <- paste(lbls,"%",sep="") # add % to labels
> pie(slices,labels = lbls, col=c("#0E5E6F", "#3A8891", "#F2DEBA","#FFEFD6"),
+     main="Participant Race / Ethnicity")
```

[x] SUS Score

```r
> t.test(group_A$SUS_Score, group_B$SUS_Score)

	Welch Two Sample t-test

data:  group_A$SUS_Score and group_B$SUS_Score
t = 0.51407, df = 9.8364, p-value = 0.6186
alternative hypothesis: true difference in means is not equal to 0
95 percent confidence interval:
 -13.93367  22.26700
sample estimates:
mean of x mean of y
 71.66667  67.50000

boxplot(SUS_Score~A_B, data=data, main="Comparison of SUS Score", xlab="Interface Type", ylab="Score", ylim=c(30, 100), names=c("A", "B"), col=c("#E14C1E", "#1EB3E1"))

summary(data$SUS_Score)
Min. 1st Qu.  Median    Mean 3rd Qu.    Max.
  42.50   66.25   72.50   69.58   76.25   87.50
```
