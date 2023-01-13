---
title: "Lab 2 Homework"
author: Hugo Mahatdejkul
date: "2023-01-12"
output:
  html_document: 
    theme: spacelab
    keep_md: yes
---

## Instructions
Answer the following questions and complete the exercises in RMarkdown. Please embed all of your code and push your final work to your repository. Your final lab report should be organized, clean, and run free from errors. Remember, you must remove the `#` for the included code chunks to run. Be sure to add your name to the author header above.  

Make sure to use the formatting conventions of RMarkdown to make your report neat and clean!  

1. What is a vector in R?  
A list of variables
2. What is a data matrix in R?  
A collection of data thats in row and columns
3. Below are data collected by three scientists (Jill, Steve, Susan in order) measuring temperatures of eight hot springs. Run this code chunk to create the vectors.  

```r
spring_1 <- c(36.25, 35.40, 35.30)
spring_2 <- c(35.15, 35.35, 33.35)
spring_3 <- c(30.70, 29.65, 29.20)
spring_4 <- c(39.70, 40.05, 38.65)
spring_5 <- c(31.85, 31.40, 29.30)
spring_6 <- c(30.20, 30.65, 29.75)
spring_7 <- c(32.90, 32.50, 32.80)
spring_8 <- c(36.80, 36.45, 33.15)
```

4. Build a data matrix that has the springs as rows and the columns as scientists.  

```r
collected_data<-c(spring_1,spring_2,spring_3,spring_4,spring_5,spring_6,spring_7,spring_8)
data_matrix<-matrix(collected_data,nrow=8,byrow=T)
data_matrix
```

```
##       [,1]  [,2]  [,3]
## [1,] 36.25 35.40 35.30
## [2,] 35.15 35.35 33.35
## [3,] 30.70 29.65 29.20
## [4,] 39.70 40.05 38.65
## [5,] 31.85 31.40 29.30
## [6,] 30.20 30.65 29.75
## [7,] 32.90 32.50 32.80
## [8,] 36.80 36.45 33.15
```

5. The names of the springs are 1.Bluebell Spring, 2.Opal Spring, 3.Riverside Spring, 4.Too Hot Spring, 5.Mystery Spring, 6.Emerald Spring, 7.Black Spring, 8.Pearl Spring. Name the rows and columns in the data matrix. Start by making two new vectors with the names, then use `colnames()` and `rownames()` to name the columns and rows.

```r
scientists<-c("Jill","steve","susan")
colnames(data_matrix)<-scientists
springs<-c("BlueBell Spring","Opal Spring","Riverside Spring","Too Hot spring","mystery spring ","emerald spring ","black spring ","pearl spring")
rownames(data_matrix)<-springs
data_matrix
```

```
##                   Jill steve susan
## BlueBell Spring  36.25 35.40 35.30
## Opal Spring      35.15 35.35 33.35
## Riverside Spring 30.70 29.65 29.20
## Too Hot spring   39.70 40.05 38.65
## mystery spring   31.85 31.40 29.30
## emerald spring   30.20 30.65 29.75
## black spring     32.90 32.50 32.80
## pearl spring     36.80 36.45 33.15
```


6. Calculate the mean temperature of all eight springs.

```r
Mean_temp_row1<-mean(c(data_matrix[1],data_matrix[9],data_matrix[17]))
Mean_temp_row2<-mean(c(data_matrix[2],data_matrix[10],data_matrix[18]))
Mean_temp_row3<-mean(c(data_matrix[3],data_matrix[11],data_matrix[19]))
Mean_temp_row4<-mean(c(data_matrix[4],data_matrix[12],data_matrix[20]))
Mean_temp_row5<-mean(c(data_matrix[5],data_matrix[13],data_matrix[21]))
Mean_temp_row6<-mean(c(data_matrix[6],data_matrix[14],data_matrix[22]))
Mean_temp_row7<-mean(c(data_matrix[7],data_matrix[15],data_matrix[23]))
Mean_temp_row8<-mean(c(data_matrix[8],data_matrix[16],data_matrix[24]))
Mean_temp_row1
```

```
## [1] 35.65
```

```r
Mean_temp_row2
```

```
## [1] 34.61667
```

```r
Mean_temp_row3
```

```
## [1] 29.85
```

```r
Mean_temp_row4
```

```
## [1] 39.46667
```

```r
Mean_temp_row5
```

```
## [1] 30.85
```

```r
Mean_temp_row6
```

```
## [1] 30.2
```

```r
Mean_temp_row7
```

```
## [1] 32.73333
```

```r
Mean_temp_row8
```

```
## [1] 35.46667
```

```r
mean_Temps<-c(Mean_temp_row1,Mean_temp_row2,Mean_temp_row3,Mean_temp_row4,Mean_temp_row5,Mean_temp_row6,Mean_temp_row7,Mean_temp_row8)
```

7. Add this as a new column in the data matrix.  

```r
DataMAtrixWMean<-cbind(data_matrix,mean_Temps)
DataMAtrixWMean
```

```
##                   Jill steve susan mean_Temps
## BlueBell Spring  36.25 35.40 35.30   35.65000
## Opal Spring      35.15 35.35 33.35   34.61667
## Riverside Spring 30.70 29.65 29.20   29.85000
## Too Hot spring   39.70 40.05 38.65   39.46667
## mystery spring   31.85 31.40 29.30   30.85000
## emerald spring   30.20 30.65 29.75   30.20000
## black spring     32.90 32.50 32.80   32.73333
## pearl spring     36.80 36.45 33.15   35.46667
```

8. Show Susan's value for Opal Spring only.

```r
DataMAtrixWMean[18]
```

```
## [1] 33.35
```

9. Calculate the mean for Jill's column only.  

```r
Jill_values<-c(DataMAtrixWMean[1],DataMAtrixWMean[2],DataMAtrixWMean[3],DataMAtrixWMean[4],DataMAtrixWMean[5],DataMAtrixWMean[6],DataMAtrixWMean[7],DataMAtrixWMean[8])
Jill_mean<-mean(Jill_values)
Jill_mean
```

```
## [1] 34.19375
```

10. Use the data matrix to perform one calculation or operation of your interest.

```r
Total_Sum<-sum(data_matrix)
Total_Sum
```

```
## [1] 806.5
```

## Push your final code to GitHub!
Please be sure that you check the `keep md` file in the knit preferences.  
