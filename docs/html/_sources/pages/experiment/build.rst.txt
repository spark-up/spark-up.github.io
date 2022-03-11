Build
=====
After confirming our implementation of PySpark for Base Featurization 
is indeed accurate, we then intend to study the preprocessing time for 
scalability. To do this we intend to time our implementation in seconds. 
To test for scalability we will use a range of sizes for the input csv 
starting around 1 GB then increasing till we reach >100 GB of data. 

The csv we chose for our experiment was the members.csv. This data was 
collected from meetup.com API in December 2017 and includes a list of 
members from the site. The inital size of the csv is ~1.25 gbs and it 
has ~6 million rows and 14 columns. Therefore, for our experiment we 
doubled the rows of the input csv after each timed run until we reached 
>100 gbs of data (Table 1).

To make sure we only time the function itself Spark.checkpoint directory 
is used to save the different csv sizes to memory. Also, it is made sure 
the same SparkSession is used throughout all runs. 
