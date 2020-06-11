# Getting and Cleaning Data 

# Instructions for running the script

* Download and unzip data into your R working directory: https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip
* Download the script run_analysis.R 
* Execute the script which produces tidydata.txt and list_columns.txt

# Data description
From the datasets we get that these experiments have been carried out with a group of 30 volunteers within an age bracket of 19 to 48 years.Every person performed six activities like WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING wearing a smartphone i.e Samsung Galaxy S II on the waist. By Using its embedded accelerometer and gyroscope, we captured three-axial linear acceleration and three-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label  data manually. These obtained dataset has been randomly partitioned into two sets, where 70% of volunteers was selected for generating the training data and 30% of test data. 

The sensor signals  were preprocessed by applying noise filters and then sampled in the fixed width sliding windows of 2.56 sec  . The sensor acceleration signal has the gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only the low frequency components, therefore the filter with 0.3 Hz cutoff frequency was used. From every window, the vector of features was obtained by the  calculating variables from the time and frequency domain. Have a look on 'features_info.txt' for more details. 

For detail information: https://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

# Code description
These are the steps that are carried out in the script:

* Step 1: Read train, test and subject data into workspace. Then, combine these dataframes using rbind into their respective dataframes denoted by the subscript _total
* Step 2: Read text files containing feature and activity labels into workspace. Then, extract list with features containing only the mean- and stdev-variables. Use this list of features to subset x_total and remove redundant features from the dataframe
* Step 3: Apply the activity labels to the y_total dataframe
* Step 4: Apply feature labels to the x_total dataframe
* Step 5: rename final columns so that they all have the correct names. Then, combine x_total, y_total, and sub_total into to almost create the final dataframe. Final step here is to group by and average over subject_id and activity to create the dataframe final_mean.
* Step 6: Export final_mean to tidydata.txt
* Optional: create list of names of columns and export this one as well
