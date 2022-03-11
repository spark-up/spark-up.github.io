Base Featurization
==================
The first step Base Featurization takes the raw csv and extracts features needed from the csv including descriptive statistics (figure 2) and 5 sample values. 
These extracted features are then used to train ML models to infer feature types from columns in a new "unseen" csv file 

.. figure:: images/descriptive_stats.png
   :scale: 100 %

   All the descriptive stats used for base featurization. (Recreation of Table 6 from Shah et al.)