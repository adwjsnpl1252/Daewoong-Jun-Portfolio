# Hotel Recommender Systems Project Overview 
* Explored the dataset with bar charts, wordclouds, various distribution plots and choropleth maps.
* Built a Content-based recommender systems models to recommend the most suitable hotel rooms for the user.

 
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



## Section 2: Content-Based Recommender System:
* Merged the name, location, review texts and review title into one column as description.
* Text preprocessing using Lemmatizer,removed the punctuations, stopwords and symbols such as @.
* Convert the text into vectors by TfidfVectorizer.
* By using linear kernel, calculated the similarities between the hotels.
* For testing, selected a random hotel and recommended 10 most similar hotels.
* Visualized the recommended hotels with word clouds in order to discover the similarities.
        
## Conclusions:
* Higher number of reviews, longer text and title length does not gurantee higher ratings
* The adjectives of the hotel(E.g: Good, Dirty, Great, etc...) affect the recommender system since the recommender system tends to recommend the hotels in the similar categories('Nicely Rated' or 'Badly Rated').
* The locations and the title of the hotel had crucial impacts on the recommendations.
* As the majority of recommended results from the content-based recommender system were solely based on the hotel's name, reviews, review title, and the locations. 
