# MangrovesBardsley
The goal of this activity was to explore the possibility of using a methodology similar to one done in Mangroves challenge, 
but on the Bardsley data. In the challenge, Santinel 2 imagery was used as  as well as AGB values of specific points: 
there was a CSV file consisting of coordinates and an AGB for that location.  The same satellite data was used for the Bardsley. 
However, there was no AGB values but carbon values for a specific point.

To view the data, the CSV and the satellite image was loaded in QGIS. As we can see, 
there were some points outside of the polygon of interest. All of the points outside of AOI 
were clipped and not taken into account for further analysis.

It was necessary to find every band value for the pixels overlapping the points (carbon values) . 
For that task, a QGIS plug-in, Point Sampling Tool was used. 
So, for every point, a value of the band was  to a field in a CSV file.

The data was then loaded into Jupyter Notebook. Then, the values of bands were normalized. 
Calculations of different spectral indices were performed. Using that data, a correlation matrix was calculated.
Based on the results of the matrix, the indices and bands that correlate the most to carbon values were used as input to random forest regression algorithm.

The results of the algorithm were not promising. 
The algorithm was tried with different numbers of values and attributes as input,
with and without normalized pixel values,  as well as with and without outlier data. T
he XGBReggression was not performed.
