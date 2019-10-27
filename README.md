# UFC-fighting-styles
A clustering approach to analyze the fighting styles of mma fighter  


## Background about the project
[![Product Name Screen Shot][product-screenshot]](https://example.com)

![MMA 'Fighting Styles'](https://legendsmma.net/wp-content/uploads/2018/08/Legends-MMA-Infographics.jpg)

As a longtime martial artist and an MMA fun, I saw the progression of th sport known as mixed martial arts from a competion between two fighting styles to a real sport , where competitors took what works from each martial art, tailored old fighting styles to their needs  to serve them best when facing other trained killers. 

From the first UFCs where fighters where strict boxer, wrestlers,BJJ practitionners or tough guys, the sport evolved to a mixed of styles. There was no more of a 'pure' kickboxer, 'pure' wrestler etc.. each martial artist now can kick, punch, shoot for a takedown or pass guard and submit. Nonetheless, before each fight, competitors are still presented as strikers, wrestler or grapplers, depending on their background, what they showed the last fight or what the annoucer thinks about the fighter.

As a data science enthousiast, this never sat right with me. I believe in a world view where assumptions and hypothesis must be tested to gauge their truthfullness.

So i found a [UFC DATASET](https://www.kaggle.com/calmdownkarm/ufcdataset) on kaggle and got to work :smile:

## Overview of the project

Now armed with the dataset :
* I first aggregated the data to have a dataframe of fighters and their mean 81 stats across all their fights( ex : mean body kick landed, mean takedown attempts ...)
* We have highly correlated features, so i dropped the features that are correlated more  than 0.9 ( could have used the p-value, something to try in the V2)
* I applied PCA  to the resulting dataframe 
* I applied K means on the PCA result (reduced the features to n-features =5) 
* Plotted the result of the clustering first in 2D (feature 1 and 2) than in 3D

### Result of the analysis
Well , well , well.

Let's see what we've got, did we get the stereotypical Wrestle-Boxer, the Pure striker ? 
The heatmap below, shows wich combination of original features explain the variability in the data, wich is really a really useful insight when trying to cluster fighter's styles    
![MMA 'Fighting Styles'](https://github.com/AmineDiro/UFC-fighting-styles/blob/master/PCA_result.png?raw=true)
 
1.CLuster 1 : 
* Top 5 features :
```
TIP_Control Time                             0.224394
Strikes_Ground Total Strikes_Attempts        0.212942
Strikes_Body Significant Strikes_Attempts    0.211967
TIP_Distance Time                            0.211406
Strikes_Kicks_Attempts                       0.205699
```
* Bottom 5 features
```
Grappling_Reversals_Landed                   0.053318
Strikes_Knock Down_Landed                    0.077610
Strikes_Ground Significant Kicks_Attempts    0.101966
Strikes_Ground Leg Strikes_Attempts          0.103285
TIP_Side Control Time                        0.105258
```

2.CLuster 2 : 
* Top 5 features :
```
TIP_Ground Control Time                  0.262890
TIP_Control Time                         0.233163
TIP_Ground Time                          0.220465
Strikes_Ground Total Strikes_Attempts    0.220360
TIP_Half Guard Control Time              0.200544
```
* Bottom 5 features
```
Grappling_Reversals_Landed                   0.053318
Strikes_Knock Down_Landed                    0.077610
Strikes_Ground Significant Kicks_Attempts    0.101966
Strikes_Ground Leg Strikes_Attempts          0.103285
TIP_Side Control Time                        0.105258
```

3.CLuster 3 : 
* Top 5 features :
```
Strikes_Clinch Head Strikes_Attempts         0.319705
Strikes_Body Significant Strikes_Attempts    0.301377
Strikes_Clinch Body Strikes_Attempts         0.278838
Strikes_Distance Head Strikes_Attempts       0.259668
Grappling_Standups_Landed                    0.259087
```
* Bottom 5 features
```
Strikes_Kicks_Attempts                        -0.214250
Strikes_Ground Significant Punches_Attempts   -0.206274
Strikes_Clinch Significant Kicks_Attempts     -0.188765
Strikes_Distance Leg Kicks_Attempts           -0.182671
Strikes_Distance Head Kicks_Attempts          -0.175149
```

4.CLuster 4 : 
* Top 5 features :
```
TIP_Mount Control Time            0.246223
Grappling_Submissions_Attempts    0.237841
Strikes_Knock Down_Landed         0.223450
TIP_Ground Time                   0.196941
TIP_Back Control Time             0.182116
```
* Bottom 5 features
```
Strikes_Clinch Leg Strikes_Attempts           -0.309975
Strikes_Clinch Body Strikes_Attempts          -0.281264
Strikes_Clinch Significant Kicks_Attempts     -0.271919
Strikes_Clinch Significant Punches_Attempts   -0.267636
Strikes_Ground Body Strikes_Attempts          -0.247264
```

5.CLuster 5 : 
* Top 5 features :
```
Strikes_Leg Total Strikes_Attempts           0.335641
Strikes_Clinch Leg Strikes_Attempts          0.319116
TIP_Mount Control Time                       0.267034
TIP_Clinch Time                              0.187386
Strikes_Clinch Significant Kicks_Attempts    0.187309
```
* Bottom 5 features
```
Strikes_Ground Significant Punches_Attempts   -0.356793
Strikes_Ground Significant Kicks_Attempts     -0.331809
Strikes_Ground Head Strikes_Attempts          -0.218538
Strikes_Ground Body Strikes_Attempts          -0.187797
TIP_Misc. Ground Control Time                 -0.184458
```


### V2. What's next ? 

