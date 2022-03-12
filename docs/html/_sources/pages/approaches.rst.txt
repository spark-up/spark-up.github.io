Scaling Base Featurization
==========================

To scale AutoML feature type inference, we reimplemented the SortingHat's  
*Base Featurization* algorithm in PySpark. As with the original implementation, we 
assume that the input PySpark DataFrame is read with initial datatype inference.
In Pandas, this is the default. In PySpark, the `inferSchema` argument of 
`DataFrameReader.csv()` must be set to `True`.


