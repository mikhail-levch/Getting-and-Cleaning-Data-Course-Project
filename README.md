## Tyding and summarizing script

This file contains the script lines and the description of the process of data tyding and summarising.

##### Data downloading
Firstly, I downloaded data from the test and the train repos:

> stest <- read.table(file = "subject_test.txt")

> xtest <- read.table(file = "X_test.txt")

> ytest <- read.table(file = "y_test.txt")

> strain <- read.table(file = "subject_train.txt")

> xtrain <- read.table(file = "X_train.txt")

> ytrain <- read.table(file = "y_train.txt")

After that, I downloaded the variables names and the activity labels from the root repo of the data set:

> nvar <- read.table("features.txt")

> act <- read.table("activity_labels.txt")

##### Data merging

I merged data in the following order:

1.Adding the subject and activity variables:

> test <- cbind(stest,ytest,xtest)

> train <- cbind(strain,ytrain,xtrain)

2.Adding descriptive variable names:

> cnames <- c("subject","activity",nvar)

> colnames(test) <- cnames

> colnames(train) <- cnames

3.Merging the test and the training data sets:

> data <- rbind(test,train)

##### Selecting

I selected only the measurements on the mean and standard deviation for each measurement:

> data <- data[,grep("mean|std", colnames(data))]

##### Activities labelling

I replace numbers in activity column to their descriptive labels:

> data$activity <- factor(data$activity,labels=act$V2)

### Second data set             

I created the second data set with  the average of each variable for each activity and each subject. For this purpose I used *aggregate* function:

> data2 <- aggregate(. ~ data1$subject + data1$activity, data1[,-(1:2)], mean)
        
> colnames(data2)[1:2] <- c("subject","activity")           
             
##### Data sets files
> write.csv(x = data,file = "HumanActRec.csv",row.names = FALSE)
> write.csv(x = data2,file = "AverageValues.csv",row.names = FALSE)
             