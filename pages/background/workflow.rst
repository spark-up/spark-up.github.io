AutoML feature type inference Workflow
======================================
Figure 1 shows the entire workflow of ML-based feature type inference. 
The first step $Base Featurization$ takes the raw csv and extracts features needed from the csv including descriptive statistics (figure 2) and 5 sample values. 
These extracted features are then used to train ML models to infer feature types from columns in a new "unseen" csv file 

.. figure:: images/full_workflow.png
   :scale: 100 %

   Workflow showing how our data is used for ML-based feature type inference. (Recreation of Figure 4 from Shah et al.)

.. figure:: images/descriptive_stats.png
   :scale: 100 %

   All the descriptive stats used for base featurization. (Recreation of Table 6 from Shah et al.)