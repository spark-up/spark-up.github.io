PySpark
=======
To scale the base featurization step, we reimplement the SortingHat base featurization algorithm in PySpark. Like the
Python code, we assume that the input PySpark DataFrame is read with initial datatype inference. In Pandas, this is
done by default; in PySpark, the inferSchema argument of DataFrameReader.csv() must be set to true.
Unfortunately, the PySpark DataFrame’s data model does not support efficient sampling, as operations crossing
the Python/JVM barrier incur significant overhead. As such, we step down to the lower level RDD abstraction, which
allows for mapping across partitions, reducing this overhead from 𝑂(𝑁𝑀)to 𝑂(𝑀), where 𝑁 and 𝑀 are respectively
the number of rows per partition and the number of partitions.
With our implementation we perform two full scans of the dataframe. The first scan acquires all the descriptive statis-
tics (figure 2). We use a dictionary to loop through and extract descriptive statistic features using 𝑝𝑦𝑠𝑝𝑎𝑟𝑘.𝑠𝑞𝑙.𝑓𝑢𝑛𝑐𝑡𝑖𝑜𝑛𝑠.
This is done while simultaneously iterating through the entire dataset. The second scan obtains the 5 sample values.
This scan will iterate through the dataset and obtain 5 distinct values to use as our sample values.