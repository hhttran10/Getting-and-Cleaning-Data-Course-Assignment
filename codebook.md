## Variables created to read the whole data sets
test.labels 
test.subjects 
test.data 
train.labels 
train.subjects 
train.data 

## Variables then put all under one variable, in the format of: subjects, labels, everything else
data

## Variable reads the features
features

## Variable retains features of mean and standard deviation
features.mean.std

## Variable selects only the means and standard deviations from data
data.mean.std 

## Variable reads the labels (activities)
labels

## Variable replaces labels in data with label names
data.mean.std$label 

## Variable first makes a list of the current column names and feature names
good.colnames

## then tidy that list
# by removing every non-alphabetic character and converting to lowercase
good.colnames 
# then use the list as column names for data
colnames(data.mean.std) <- good.colnames

## Variable find the mean for each combination of subject and label
aggr.data

## Write the data for course upload
write.table(format(aggr.data, scientific=T), "tidy_data.txt",
            row.names=F, col.names=F, quote=2)
