Scaling Base Featurization
==========================

To scale AutoML feature type inference, we reimplemented the SortingHat's  
*Base Featurization* algorithm in PySpark. As with the original implementation, we 
assume that the input PySpark DataFrame is read with initial datatype inference.
In Pandas, this is the default. In PySpark, the `inferSchema` argument of 
`DataFrameReader.csv()` must be set to `True`.

For our implementation we have divdied the computed features into two 
parts: "simple" features and "sample" features. Therefore, we do a two 
full scans of the dataset. The first scan computes the "simple" features 
by performing simple "aggregates" that are delegated to Spark SQL.
The second scan extracts five distinct values non-deterministically from 
each column and computes features from the sample values. If a column has less
than 5 distinct values then the first 3 values are chosen.



