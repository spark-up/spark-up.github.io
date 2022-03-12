Dataset
=======
The csv we chose for our experiment was the members.csv. This data was 
collected from meetup.com API in December 2017 and includes a list of 
members from the site. The inital size of the csv is ~1.25 gbs and it 
has ~6 million rows and 14 columns. Therefore, for our experiment we 
doubled (*2x*) the rows of the input csv after each timed run until we reached 
our cluster's capacity (Table 1). Based on our current cluster configuration
the csv was scaled till it reached ~600 gbs.


.. figure:: images/membercsv.png
   :scale: 50 %

   **members.csv**