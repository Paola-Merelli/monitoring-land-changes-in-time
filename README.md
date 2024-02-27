# monitoring-land-changes-in-time
The main objective is to analyze the relationship between beta-diversity and land cover changes in space and time. 
For this analysis Sorensen, Jaccard and Rao’s Q indices were used. 
This research has been based on satellite images, and the analysis has
been conducted with R programming language, obtaining a code applicable to any land cover map pair, 
representing different places or the same in different periods of time, 
giving as output a map that shows with a very inclusive palette the Beta diversity between the
starting two. 
All the project was based on this simple assumption. Environmental heterogeneity is one of
the main factors associated with a high degree of biological diversity, given that areas with
higher environmental heterogeneity can host more species due to the greater number of
available niches within them. Spatial variability in the remotely sensed signal, is expected to
be related to environmental heterogeneity and could therefore be used as a powerful proxy of species diversity.
For this research a dataset from Copernicus, an open access website, has been downloaded, the Corine Land cover dataset of 1992 and 2008. 
In this way we obtained 2 maps of all Europe classified for different land cover types.
The maps were then opened in Qgis, to clip different areas of interest and obtain a TIFF file for each area that could be easly opened in R. 
Then for each map the land cover classification was recreated. 
So, for each area of interest there were two maps, one of 1992 and one of 2008. 
Now everything was set for the analysis.
For each map pair the following analysis were conducted
- Sorensen index
- Sorensen Gain
- Sorensen Loss
- Jaccard index
- Jaccard Gain
- Jaccard Loss
- Rao’sQ index

For the analysis it was used the moving window approach that consist in selecting an odd
number, which will correspond to the length of the squared window. 
With this choice, we have a central entry in the window, which will be placed as a mask, in position (1, 1) over our raster. 
The index is therefore computed only with the values which the window covers.
The obtained index value is stored in position (1, 1) in the output raster. 
The following step is moving the window so that its central entry is over the entry (1, 2) of the raster. 
The index value computed is stored in the corresponding position of the output raster, that is, in (1, 2). 
We proceed in this way until the last entry of the output raster is filled.
By combining properly this approach to the specific line of code computing each index is
possible to obtain as output a map displaying with a proper color palette the value of the calculated index, for each pixel.
In conclusion, was developed a code that, starting from 2 input land cover maps, can calculate automatically for each pixel 
the beta diversity using Sorensen, Jaccard and Rao’s Q indices and gives as output a third map representing it. 
In this way is possible to have an idea of the different spatial variability of the 2 starting maps, that is related to the environmental heterogeneity.
