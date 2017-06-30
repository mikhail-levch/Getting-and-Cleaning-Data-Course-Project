## Code_book 
### Data source: 
Human Activity Recognition Using Smartphones Dataset
Version 1.0;
Jorge L. Reyes-Ortiz, Davide Anguita, Alessandro Ghio, Luca Oneto;
Smartlab - Non Linear Complex Systems Laboratory;
DITEN - Universit degli Studi di Genova;
Via Opera Pia 11A, I-16145, Genoa, Italy;
activityrecognition@smartlab.ws;
www.smartlab.ws.

### Data description from data supplier:
The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. 

The features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ. These time domain signals (prefix 't' to denote time) were captured at a constant rate of 50 Hz. Then they were filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise. Similarly, the acceleration signal was then separated into body and gravity acceleration signals (tBodyAcc-XYZ and tGravityAcc-XYZ) using another low pass Butterworth filter with a corner frequency of 0.3 Hz.

Subsequently, the body linear acceleration and angular velocity were derived in time to obtain Jerk signals (tBodyAccJerk-XYZ and tBodyGyroJerk-XYZ). Also the magnitude of these three-dimensional signals were calculated using the Euclidean norm (tBodyAccMag, tGravityAccMag, tBodyAccJerkMag, tBodyGyroMag, tBodyGyroJerkMag). 

Finally a Fast Fourier Transform (FFT) was applied to some of these signals producing fBodyAcc-XYZ, fBodyAccJerk-XYZ, fBodyGyro-XYZ, fBodyAccJerkMag, fBodyGyroMag, fBodyGyroJerkMag. (Note the 'f' to indicate frequency domain signals). 

These signals were used to estimate variables of the feature vector for each pattern:  
'-XYZ' is used to denote 3-axial signals in the X, Y and Z directions.

### Data transformations
For purpose of tyding following data transformations were made:

1. *test* and *train* data sets were merged;
2. *subject* and *activity* variables were added;
2. mean "mean()" and standard deviation "std()" variables were selected;

### Final list of variables:

- tBodyAcc-XYZ
- tGravityAcc-XYZ
- tBodyAccJerk-XYZ
- tBodyGyro-XYZ
- tBodyGyroJerk-XYZ
- tBodyAccMag
- tGravityAccMag
- tBodyAccJerkMag
- tBodyGyroMag
- tBodyGyroJerkMag
- fBodyAcc-XYZ
- fBodyAccJerk-XYZ
- fBodyGyro-XYZ
- fBodyAccMag
- fBodyAccJerkMag
- fBodyGyroMag
- fBodyGyroJerkMag

Each variable were presented as: 

- mean(): Mean value
- std(): Standard deviation value

### Second data set
Second, independent tidy data set were created. It contains the average values of each variable for each activity and each subject.

### Data files
- HumanActRec.csv - data set with the variables listed above (68 variables, 10299 observations)
- AverageValues.csv - data set with the average of each variable for each activity and each subject (68 variables, 180 observations)