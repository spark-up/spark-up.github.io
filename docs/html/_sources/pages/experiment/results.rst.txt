Results
=======
Looking at figure 2 and figure 3 we can see that the experiment graphs appear
relatively linear. 

.. figure:: images/heterodyneclusterrelative.png
   :scale: 35 %

   **Figure 2**

.. figure:: images/heterodyneclusterscaling.png
   :scale: 35 %

   **Figure 3**

Indeed, fitting a linear model between relative size and relative runtime returns 
a slope of **0.0815**. That is for every unit increase in input size, the relative 
runtime increases by approximately 8 percentage points. We also find a Pearson 
correlation coefficient of **0.998972** and **r\ :sup:`2` = 0.997945**. Thus, we can conclude 
that runtime scales linearly with input size: only neglible amount of variation in 
runtime is unexplained by variation in input size.

Further inspection of Spark stage and job logs in Figure 4 and Figure 5 reveal that the 
current implementation's bottleneck lies in **toPandas** calls; this is due to lazy evalutaion.
That said, the relative distribution of runtimes in Figure 4 indicates that the bottleneck
actually lies with "Simple" features, with 

.. figure:: images/sample_chart.png
   :scale: 35 %

   **Figure 4**

.. figure:: images/sample_chart2.png
   :scale: 35 %

   **Figure 5**

Finally, it's worth noting that these results only appear for in-memory analytics, and likely
will not scale beyond that data across regime. Large numbers of high cardinality input
features may cause pathological worst-case behavior. However, we are confident that this
proof of concept implementation will scale well into the terabytes with sufficient memory.





