getting-and-cleaning-data-project
=================================
The run_analysis.R script reads data from the "Human Activity Recognition Using Smartphones Dataset Version 1.0" and produces a new - tidy - dataset which may be used for further analysis.
The data in the "Human Activity Recognition Using Smartphones Dataset Version 1.0" have been taken from experiments carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz data were captured. The experiments were video-recorded to label the data manually. The obtained dataset was randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. 

Steps to reproduce this project
=================================
1.	Download the data source (https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip)  and put into a folder on your local drive. 
2.	Put run_analysis.R in the same folder of your working directory.
3.	Run: source("run_analysis.R"), and it will generate a new file tidy_data.txt in your working directory.


A brief description of the script:
=================================
The run_analysis.R script merges data from a number of .txt files and produces a tidy data set which may be used for further analysis.
•	It reads all required .txt files and labels the datasets
•	Consquently the appropriate "activity_id"'s and "subject_id"'s are appended to the "test" and the "training" data, which are then combined into one single data frame.
•	Using the "grep" function, all the columns with mean() and std() values are extracted in order to create a new data frame with only the "activity_id", the "subject_id" and the mean() and std() columns, is created 
•	Using the "merge" function, descriptive activity names are merged with the mean/std values dataset, to get one dataset with descriptive activity names
•	Lastly, with the help of the "melt" and "dcast" functions of the "reshape2" package, the data is converted into a table containing mean values of all the included features, ordered by the activity name and the subject id, and the data is written to the "tidy _data.txt" file.
