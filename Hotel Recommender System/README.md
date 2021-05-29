# Hotel Recommender Systems Project Overview 
* Explored the dataset with bar charts, wordclouds, various distribution plots and choropleth maps.
* Sentimental analysis based on the past reviews and ratings. Classified the reviews into two categories : 'Nicely Rated Hotels" or "Badly Rated Hotels".
* Classified with Multinomial Naive Bayes, Logistic Regressions and Support Vector Machines.
* Built both Collaborative-Filtering and Content-based recommender systems models to recommend the most suitable hotel rooms for people.
* To decide which recommender system is more suitable.
 
 ![](/images/hotel_page.jpg)
 
## *About The Dataset:*
* A dataset from Kaggle : https://www.kaggle.com/datafiniti/hotel-reviews provided by Datafiniti
* Dataset with large number of different hotels and their ratings and reviews.

## *Features*
* address : The address of the hotel
* categories : The types of hotel(Eg : Motel, Hotel, etc )
* city,country,province : which city,country and province does this hotel belongs to.
* latitude,longitude : The latitude and longitude of the hotel
* name : name of the hotel
* postalCode : postal code of the hotel
* reviews.date : Date when the online reviews was posted
* reviews.dateAdd : The date when the date was added to the database
* reviews.rating : The ratings that the past users gave to the hotel
* reviews.text, reviews.title : The title and the content of the review
* reviews.username : The username of the person who posted the reviews.
* reviews.userCity : The city where the user is residing
* reviews.userProvince : The province where the user is residing.
* reviews.id,reviews.doRecommend: These are Null columns.

## Section 1: Data Cleaning and Exploratory Data Analysis:
* Dropped unnecessary columns and null values
* Dropped outliers(ratings above 8 and hotels with reviews less than 10)
* Using base map and choropleth map, visualize the distributions of hotels in the US.
* Using bar plots to measure the total number of reviews and average rating in each provinces, cities and hotels.
* Box plots to visualize the ratings distribution.
* Wordclouds to discover the keywords in hotels with high ratings and low ratings
* Histograms to explore the frequency of title length and text length.
* Here are some highlights:

![](/images/hotel_province.jpg)
![](/images/hotel_cities.jpg)
![](/images/hotel_pro_rat.jpg.jpg)
![](/images/hotel_cit_rat.jpg.jpg)
![](/images/hotel_dist.jpg)
![](/images/hotel_hist1.jpg)
![](/images/hotel_dist2.jpg)
![](/images/hotel_heatmap.jpg)

![](/images/nice_hotels.jpg)
![](/images/bad_hotels.jpg)



## Section 2: Sentimental Analysis:
* Separate the hotels into two groups according to their review ratings : 0(bad) and 1(good).
* Hotels with ratings more than or equal to 4 considered as 1 and 0 for the hotels with less than 4.
* Text preprocessing using PorterStemmer and removed the punctuations.
* Convert the text into vectors by TfidfVectorizer.
* Using the classification Models( MultionomialNB, Logistic Regression and SVM) to classify the hotels into targets(0 or 1) based on their reviews.
* Here are some highlights :

![](/images/hotels_mnb.png) 
![](/images/hotel_lr.png)
![](/images/hotel_svm.png)


## Section 3: Recommender Systems:
* Built a Collaborative-Filtering Recommender system and Content-Based Recommender system.
* Collaborative-Filtering Recommender system :
    * Made a pivot table, index as the hotel names and columns as usernames to distinguish the ratings on the hotels by each user.
    * Convert the pivot table into a sparse matrix.
    * By using NearestNeighbors algorithm, searching for the hotels with the most similar hotels( hotels with the lowest distances)
    * For testing, selected a random hotel and recommended 10 most similar hotels.
* Content-Based Recommender System:
    * Merged the name, location, review texts and review title into one column as description.
    * Converted the description into vectors with TfidfVectorizer
    * By using linear kernel, calculated the similarities between the hotels.
    * For testing, selected a random hotel and recommended 10 most similar hotels.
    * Visualized the recommended hotels with word clouds in order to discover the similarities.
    

![](/images/collaborative.png)

![](/images/content_based.png)
    
## Conclusions:
* Higher number of reviews, longer text and title length does not gurantee higher ratings
* Classifying models are sensitive to the adjectives of the hotel(E.g: Good, Dirty, Great, etc...) when they are classifying the text's sentiments. This also affects the recommender system since the recommender system tends to recommend the hotels in the similar categories('Nicely Rated' or 'Badly Rated').
* The locations and the title of the hotel had crucial impacts on the recommendations.
* As the majority of recommended results from the content-based recommender system were solely based on the hotel's name, reviews, review title, and the locations. On the other hand, the collaborative-filtering recommender system gave the recommendations based on the ratings of the similar users. Therefore, the collaborative-filtering recommender system will be more suitable as the results from the content-based recommender system can be limited by the locations.
