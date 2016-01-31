This week, we wrapped up the linear regression topic by presenting projects in which we developed a model to predict a movie's success.  

For my project, I looked at movies "Based on a True Story" and collected data to determine which features are the most influential to the Worldwide Gross of movies belonging to this category.  

I used Beautiful Soup to scrape data from IMDB.com, BoxOfficeMojo.com, and TheNumbers.com, and found 10 features for movies Based on a True Story:  

1. MPAA Rating (G/PG/PG-13/R)  
2. Runtime  
3. IMDB Score  
4. Opening # Theaters (Domestic)  
5. Opening Gross (Domestic)  
6. Total # Theaters (Domestic)  
7. Total Gross (Domestic)  
8. Peak movie season (Categorical variable equal to 1 if released during summer/holidy season)  
9. Budget  
10. Genre (Action, Adventure, Biography, Comedy, Crime, Documentary, Drama, Family, History, Horror, Music, Mystery, Romance, Sport, Thriller, War, Western)  
</br>
</br>
</br>

In order to develop an accurate predictive model, I began by performing Ordinary Least Squares regression incorporating all of my feautures in the model, and iteratively removing features that showed a p-value higher than a certain threshold (0.100). The initial models were applied to a training set of 70% of the movie data, and the results below show the models performance on the test set.  
</br>
</br>
</br>

The final model showed that the most influential features were Total # Theaters, Total Gross, Budget, and the Romance genre:

![Final Model Summary](/images/final_model_summary.png)
</br>
</br>
</br>

This can be illustrated by the linear relationship between these feautures in the raw data as shown below:

![Raw Data Trends](/images/raw_data_trends.png)
</br>
</br>
</br>

The model predictions proved to be accurate overall, as can be seen by the Fit plot below (red = model prediction, blue = raw data, black = 95% confidence interval).

![Model Fit](/images/model_fit.png)
</br>
</br>
</br>

The residuals in this model increased in magnitude somewhat as the predicted Worldwide Gross increased, mainly because there was a lower density of data in this section for the model to predict. Additionally, it is always challenging to obtain accurate predictions for more extreme outcomes.

![Residuals](/images/residuals.png)
![Residuals2](/images/residuals2.png)
</br>
</br>
</br>

The results of the model imply the following conclusions for movies "Based on a True Story":  
-Domestic release (measured by Total Theaters and Total Domestic Gross) is key indicator of Worldwide Gross  
-Total Domestic Gross and Budget are linearly related to Worldwide Gross  
-Romance genre is the most highly correlated to Worldwide Gross  
