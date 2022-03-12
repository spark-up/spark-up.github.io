Scalability Experiment
======================

To verify our proof of concept implementation, we test the preprocessing time on Spark at a variety of scales.

To do this, we take an input data file and convert it into the Parquet format for storage on HDFS.
We then derive a series of scaled inputs from this, doubling the filesize row-wise with each increase, up to cluster limits.
We do this nine times.
In this way, we convert a ~1.25 GB dataset with 6 million rows into one with just over 3 *billion* rows.

Due to the in-memory nature of Spark, we find that this task scales nearly linearly with respect to the input data.


.. toctree::
   :maxdepth: 3

   experiment/dataset
   experiment/cluster
   experiment/results