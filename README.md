# Project:  Forest Cover Type Prediction

Authors: Tao Ouyang, Xi Zheng

Proposed as a half-semester data science project

## Motivation

Today, with global warming problem becoming more and more serious, protecting forests to defence against the loss of forests becomes a significant way to solve this problem. In our project, we use a dataset to find the relationships between a few features and different forest cover types. Making predication of forest cover types is a meaningful project for both ecological environmental protection and economic development. In terms of ecology, a specific tree cover type could provide habitat for some unique wildlife. Thus learning the forest cover types leads to a deeper understanding of an entire ecosystem in a region, which is also helpful for solving more environmental problems like forest fire prevention and pet control. Forests also provides plenty of economic resources for human-beings, for example, different forest types produce distinct marketable timber, or building an recreational park for commercial use in a forest with a specific cover type. Hence, forest cover type prediction could be seen as an insightful topic that is worth exploiting.

Forest cover type prediction is to predict what kind of trees might grow in a particular area using available information like slope, sunlight, hydrology and soil. However, it’s difficult for humans to identify forest cover type (the predominant kind of tree cover) manually. Usually the area we have identified is only a small percentage of the entire land area. Thus, we need to apply machine learning techniques to gain as much information from labeled data as possible and predict cover type in a larger area more accurately. Our goal is to gain best multi-class classification accuracy on testing set. And this project is designed to be a **half-semester** data science project.

## Dataset Overview

The dataset contains 54 predictor variables, both categorical and numerical variables. There are no missing values in the dataset. A total of twelve cartographic measures were utilized as independent variables in the predictive models, while seven major forest cover types were used as dependent variables. 

Data is in raw form (not scaled) and contains binary (0 or 1) columns of data for qualitative independent variables (wilderness areas and soil types). 12 measures, but 54 columns of data (10 quantitative variables, 4 binary wilderness areas and 40 binary soil type variables).
This study area includes four wilderness areas located in the Roosevelt National Forest of northern Colorado. These areas represent forests with minimal human-caused disturbances, so that existing forest cover types are more a result of ecological processes rather than forest management practices.

Basically, it’s multi-classification problem for predicting forest cover type. The training set (15120 observations) contains both features and the cover type. The test set (565892 observations) contains only the features. Each observation is a 30m x 30m patch region. 

## Proposed plan of research

First of all, we will apply data visualization and exploratory data analysis to discover relationships between predictor variables and dependent variable. We may explore the class imbalance in the dataset. Then we will do some processing to the raw data to better reveal useful information for cover type prediction.

We may apply feature selection to remove noise in the data and focus on more important independent variables. We may apply feature engineering to construct new variable using original variables with higher importance found in the exploratory data analysis. 

As for predictive methods, we plan to use traditional ml models like Decision Trees, Extremely Randomized Trees, bagging (Random Forest), boosting (Gradient Boosting) and Neural Network. We may compare the predictive power of neural networks and discriminant analysis and explore their strengths and weaknesses. We may build multiple classifiers and combine them to create a stronger classifier. We will also review the design of our models and propose some ideas about future work on the project.

## Preliminary results

The forest cover in the dataset has 7 categories in total. Each category contains 2160 data samples. We try to focus on finding some facts of how the predictor variables influence the forest cover type variable.

First, we consider the horizontal and vertical distances to hydrology.

<p align="center">
  <img src="https://github.com/vbienridy/DS5500-Spring2020-Forest-CoverType/blob/master/proposal_images/figure1.png">
</p>
<p align="center">
Figure 1: Distribution of distance to hydrology w.r.t. cover type
</p>

Figure 1 above shows that generally, with larger horizontal and vertical distances to hydrology, cover type 1, cover type 2 and cover type 7 are more likely to appear in the regions. The other forest cover types are usually appearing in regions that are near hydrology.

The binary variables, soil types, are also important variables that might influence the relationship between the forest cover type and distance to hydrology. We randomly selected two different soil types to see if the existence of a specific type of soil affects distribution of distances to hydrology and cover type. The results are shown below:

<p align="center">
  <img src="https://github.com/vbienridy/DS5500-Spring2020-Forest-CoverType/blob/master/proposal_images/figure2.png">
</p>
<p align="center">
Figure 2: Distribution of cover type and distance to hydrology w.r.t. Soil_Type3
 ( Left Figure: Soil_Type3 = 0,  Right Figure: Soil_Type3 = 1 )
</p>
<p align="center">
  <img src="https://github.com/vbienridy/DS5500-Spring2020-Forest-CoverType/blob/master/proposal_images/figure3.png">
</p>
<p align="center">
Figure 3: Distribution of cover type and distance to hydrology w.r.t. Soil_Type23
( Left Figure: Soil_Type23 = 0,  Right Figure: Soil_Type23 = 1 )
</p>

Figure 2 shows that if a region has soil type 3, it always has forest type 3 or forest type 4 covering the region no matter how far the region is from hydrology. But regions with or without soil type 23 show different patterns. Figure 3 shows that only cover type 1 or cover type 2 appear in the region far away from hydrology while cover type 7 only exists in a region that is horizontally or vertically near hydrology (surface water).

## References
[1] Project Github Repository: https://github.com/vbienridy/DS5500-Spring2020-Forest-CoverType

[2] Bache, K. & Lichman, M. (2013). UCI Machine Learning Repository. Irvine, CA: University of California, School of Information and Computer Science. Source of dataset: https://archive.ics.uci.edu/ml/datasets/Covertype

[3] The National Atlas. The maps of national forest cover types. Forest Resources of the United States.

[4] Geurts, Pierre, Damien Ernst, and Louis Wehenkel. "Extremely randomized trees." Machine learning 63.1 (2006): 3-42.

[5] Zoran Obradovic and Slobodan Vucetic. Challenges in Scientific Data Mining: Heterogeneous, Biased, and Large Samples. Center for Information Science and Technology Temple University.

[6] Blackard, Jock A. and Denis J. Dean. 2000. "Comparative Accuracies of Artificial Neural Networks and Discriminant Analysis in Predicting Forest Cover Types from Cartographic Variables." Computers and Electronics in Agriculture 24(3):131-151.

[7] Burrough, P. A. and McDonell, R.A., 1998. Principles of Geographical Information Systems (Oxford University Press, New York), p. 190.

[8] Hillshade: http://resources.esri.com/help/9.3/arcgisdesktop/com/gp_toolref/spatial_analyst_tools/how_hillshade_works.htm
