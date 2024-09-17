For this project, I was interested in seeing if there was a correlation between low income areas in Corpus Christi and environmental factors. Corpus Christi is a coastal city with industries including chemical and petroleum manufacturing. I was curious to determine if the residents of Corpus Christi living near these industrial areas were more likely to be low income, and if they were more likely to experience poor environmental factors. 

### Data
This data was obtained from the [EPA's EJScreen](https://www.epa.gov/ejscreen)  
Information pertaining to the data variables and their calculations can be found [here](https://19january2017snapshot.epa.gov/ejscreen/glossary-ejscreen-terms_.html).

The environmental factors I chose to examine were:  
- NO<sub>2</sub> concentrations (NO2)
- Hazardous waste proximity (PTSDF)
- Toxic releases to air (RSEI_AIR)
- Wastewater discharge (PWDIS)

These variables were compared to the census block groups in Nueces County that had a low income percentage of 34% or higher. I chose this value as my threshold because according to the EPA, the Texas average for low income is 34%. 

### Tools Used
I utilized ArcGis to load the EJScreen data and create a shapefile filtered to Nueces County. I loaded this shapefile into Python using Geopandas. I then created a dataframe from this data that included the socioeconomic and environmental data I was interested in, as well as the geometry which allowed me to geospatially analyze the data.

### Geospatial Analysis

![image](https://github.com/user-attachments/assets/08fc32e3-4a56-47e7-8846-3d796625c014)

![image](https://github.com/user-attachments/assets/d085b473-8334-4063-8f20-e7d2a06f7a36)

![image](https://github.com/user-attachments/assets/92531bea-9c93-4f93-bbd4-e8e6f5511bd6)

![image](https://github.com/user-attachments/assets/ddae173a-65ed-4ceb-9645-b6333000a61e)

#### Interpretation
From these maps, one can see the concentrations are highest in the North/Downtown area. This area is nearest the Port of Corpus Christi and down river from petroleum refineries.


#### Industry
Here, this map displays the locations of petroleum refineries in Corpus Christi including Flint Hills, Valero, Citgo, and Buckeye:
![image](https://github.com/user-attachments/assets/2f5627f1-1011-46f2-a5a2-46084e7b71c6)


### Exploratory Data Analysis
For the analysis, I performed a linear regression analysis to determine the relationship between low income percentage and different environmental factors. The regression line was then fit to a scatter plot to visualize the relationship.

![image](https://github.com/user-attachments/assets/849635b1-9945-402b-ab1a-3f03fe3e74b9)

![image](https://github.com/user-attachments/assets/1f60ef34-b2ae-4a29-82a7-99b27d2d6d7a)

![image](https://github.com/user-attachments/assets/d2723388-fe21-4e2e-9050-3a39d10ced3c)

![image](https://github.com/user-attachments/assets/b9f9cc9d-3511-4ebc-856b-423d480cb0d7)

- Wastewater discharge actually had a slightly negative relationship to low income percentage-- Intercept: 32.98400179972641, Coefficient for LOWINCPCT: -0.3239215737774859
- Toxic releases to air had the highest positive relation to low income percentage-- Intercept: 1432.4233098472423, Coefficient for LOWINCPCT: 91.56043154845773
- NO<sub>2</sub> was slightly positive-- Intercept: 8.682211610797932, Coefficient for LOWINCPCT: 0.03813796502379193
- Hazardous waste proximity was also slightly positive-- Intercept: 0.7483974050339415, Coefficient for LOWINCPCT: 0.021038328171622437

#### Correlation Matrix
I also generated a correlation matrix heatmap to visually represent the statistical correlations between the variables:

![image](https://github.com/user-attachments/assets/aebb8e50-ce30-42d1-b0f4-0a76f65fe826)

### Conclusions
Overall, the analysis revealed only slight correlations between the percentage of low income individuals and poor environmental factors. It appears that the highest concentrations of poor environmental quality are more closely related to geographic location and proximity to the sources of these factors. To better understand the effects and concentrations of environmental factors, future analyses should focus on land use data, water discharge data, or emissions data. Additionally, further research is needed to explore other potential correlations, such as the impact of low income on health outcomes such as cancer and respiratory illnesses, which could reveal more comprehensive connections between socioeconomic status and environmental hazards.
