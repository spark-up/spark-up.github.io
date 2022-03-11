AutoML feature type inference Workflow
======================================
.. figure:: images/full_workflow.png
   :scale: 100 %

   Workflow showing how our data is used for ML-based feature type inference. (Recreation of Figure 4 from Shah et al.)

The figure above shows the workflow for AutoML feature type inference. As seen above, the 
first step (Base Featurization) is to take the raw csv and extract specified features. Next,
these extracted features are then used to train ML models to infer feature types from columns.
Finally, the trained ML model is used to infer feature types on an "unseen" csv.

The first step or Base Featurization takes on average the longest amount of time during 
AutoML feature type inference and the whole workflow is bottlenecked at this step. 
This is because Base Featurization is the only step in the workflow that iterates through 
the whole dataframe including every row and column. Therefore, Base Featurization has a 
time complexity of O(Row*Column), while the actual inference (step 5) only has a 
time complexity of O(Column).  

