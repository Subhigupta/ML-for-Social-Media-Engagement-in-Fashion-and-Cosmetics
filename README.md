## Objective of the Project
- The objective of the project is to employ unsupervised learning algorithms on a dataset obtained from UCI Machine Learning Repository.
- The aim will be to identify cluster patterns from the dataset, to help the fashion and cosmetic companies in increasing impressions (maximize the visibility of the posts and reach to a wider audience) and hence increase customer engagement on their  facebook page.
- To explore the variations in engagements on hourly and yearly basis.

## Terminologies
1. ### Customer Segmentation or Clustering
Segmentation, involves dividing a large customer base into specific groups or segments based on shared characteristics, behaviors, or preferences. 

2. ### Customer Engagement
Customer engagement refers to the level of interaction and involvement that a customer has with a brand or company.

## About the Dataset
- [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/488/facebook+live+sellers+in+thailand)
- The dataset contains data from facebook pages of 10 Thai fashion and cosmetics retail sellers, selling their products online through facebook. 
- The posts on their pages are of a different nature such as video, photos, statuses, and links. 
- User interaction is quantified using various engagement metrics such as comments, shares, and reactions.

## Methodology
1. <font color="blue">**Exploratory Data Analysis**</font>
    - **Situation**
         - The initial steps in any data science project are data cleaning and data preprocessing.
         - After that EDA is employed.
    - **Behaviour**
        - In data cleaning step, duplicate entries were deleted, null values were checked and the unnecessary columns were removed.
        - In data preprocessing step, categorical columns were converted into numerical columns, string Date time columns were             converted into Python Date time object and year, month, weekday and hour attributes were extracted.
        - For understanding the data's characteristics and patterns, the data was first divided into two datasets before2015 and           after2015 and then an attempt was made to understand whether the user interacted with video or photo more. Heat maps             too were utilized for understanding the correlation between the features.
    - **Impact**
      - For data before 2015 we can observe following things:
         - Since the total number of likes and reactions are exactly equal for each status type, the corrleation coefficient is            one, which indicates a a perfect positive linear relationship between two variables. This means that as one variable            increases, the other variable also increases in a consistent manner.  
        - Shares and comments have strong correlation, i.e corrleation coefficient is 0.83.

      - For data after 2015 we can observe following things:
         - Since the total number of likes and reactions are almost equal for each status type, the corrleation coefficient is              0.99, which indicates a a strong positive linear relationship between two variables.   
        - Loves and shares have strong correlation.
        - Reactions and loves have a good corrleation, i.e corrleation coefficient is 0.65.
        - Shares and comments have a good correlation, i.e corrleation coefficient is 0.63.
        
2. <font color="blue">**Observe the variations in engagements on yearly basis**</font>
    - **Situation**
        - One of the objective of the project was to explore the users engagement pattern on yearly basis. The idea was to get             some valuable information about user interactions by examining yearly data in order to strategize and optimize the               approach when aiming for increase in user engagement posts.
    - **Behaviour**
        - Before2015 dataset having entries for 2012-2015 years was utilized first to understand the yearly growth of                     engagements on different type of posts for that duration.
        - Then after2015 dataset having entries for 2016-2018 was utilized to understand the yearly growth of                               engagements on different type of posts for that duration.
    - **Impact**
        - Before 2015
            - We observed that before 2015 the features like num_loves,num_wows,num_hahas,num_sads and num_angrys were not                     available.
            - Num lkes and num reactions were always more than num shares and num comments.
            - If we see as a whole, from 2012 to 2015 the user interactions have shown an increase for each type of engagement                 that were available. 
            - If we see for each kind of post then following can be concluded:
                - Users interacted highy with video contents before 2014, but during 2014-2015, the user interactions with video
                  content seems to decline for some reasons.
                - Vice versa happened with photo type content, during 2014-2015 the user interactions with photo type contents                     increased steeply. 
                - User interactions with links and status type content showed similiar behaviour as of photo content.
        - After 2015
            - If we see as a whole, from 2016 to 2018 the user interactions have shown an increase for each type of engagement.                that were available. 
            - From 2016 to 2018 users interacted more by using the comments compared to other available features.
            - If we see for each kind of post then following can be concluded:
                - The users interacted with video content using comments feature.
                - The users interacted with photo content using reactions and likes features. The users interactions using                         comments declined in year 2017-2018.
                - The users highly interacted with status type content using likes and reactions feature.
                - For link type content the users interactions using likes and reactions declined in year 2017-2018.
                
3. <font color="blue">**Observe the variations in engagements on hourly basis**</font>
    - **Situation**
        - One of the objective of the project was also to explore the users engagement pattern on hourly basis. The idea was to           get some valuable information about user interactions by examining hourly data in order to strategize and optimize the           approach when aiming for increase in user engagement posts.
    - **Behaviour**
        - Before2015 dataset having entries for 2012-2015 years for 0-23 hrs was utilized first to understand the hourly growth           of engagements on different type of posts.
        - Then after2015 dataset having entries for 2016-2018 for 0-23 hrs was utilized to understand the hourly growth of                 engagements on different type of posts.
    - **Impact**
        - Before 2015
            - If we see as a whole then users interact heavily using features such as num lkes and num reactions in the                       timeframe 12 am to 10 am. 
            - If we see for each kind of post then following can be concluded:
                - Users interact with video using number of likes and and number of reactions in good number from 12 am to                         around 8 am and user interaction start to increase slowly again after 20 pm.
                - Similiar trend can be seen for photo, link, and status content.
        - After 2015
            -  If we see as a whole then users interact heavily using all features heavily around 1 am, 8 am and 10 am and user                interaction start to increase slowly after 20 pm. Users interact with number of comments feature more as                        compared to other engagement metrics.
            - If we see for each kind of post then following can be concluded:
                - Video content: The video content has more number of comments and shows three peaks at around 1 am, 8 am and                     10 am and start to increase after 20 pm.
                - Photo content: The number of reactions and likes are in good number before 10 am and then increase after 18                     pm.
                - Status content: The number of reactions and likes are in good number before 10 am and then increase after 20                     pm.
                - Link content: The number of reactions and likes are in good number around 4 am, 8 am and 20 pm.

4. <font color="blue">**Employ K-Means for observing clusters**</font>
    - Situation
        - Since one of the objective was to identify cluster patterns from the dataset, employing an unsupervised algorithm such           as K-Means seemed to fulfill the aim.
    - Behaviour
        - K-Means was called and was fitted on both the datasets.
        - The data was scaled using standard scaler before employing K-Means algorithm  
    - Impact
        - Using K-Means without using dimensionality reduction technique prior resulted in poor clustering.

5. <font color="blue">**Employ PCA for dimensionality reduction**</font>
    - Situation
        - Since no proper clustering was observed, so employing PCA, a dimensionality reduction algorithm seemed to be a viable                 option.
    - Behaviour
        - Employed PCA for both before2015 and after2015 datasets to get the optimal principal components for both scenarios.
        - The data was scaled using standard scaler before employing PCA on both the datsets.
    - Impact
         - For before 2015 dataset, the optimal principal components obtained were two. These two principal components if used              will carry 95% of the original information.
         - For after 2015 dataset, the optimal principal components obtained were seven. These seven principal components if                used will carry 95% of the original information.
6. <font color="blue">**Employ combined PCA and K-Means**</font>
    - Situation
        - After obtaining optimal principal components for both the datasets, the next step was to obtain the optimal value of k          i.e number of clusters for both the datasets. The optimal value of k was found using both elbow mehod and silhouette 
          score.
    - Behaviour
        - First obtained the transformed datasets after employing PCA on both the datsets.
        - Then used the transformed datasets to K-Means algorithm.
        - Utlized elbow method and silhouette score to find optimal values of k.
        - Then visualized the clusters.
    - Impact
        - Using dimensionality reduction prior to K-Means helped in seeing visible clustering.
        - For both datasets after 2015 and before 2015, the optimal number of clusters came out to be 3.