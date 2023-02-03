# Song Popularity Predicter
By Luis Estrada

Many music related businesses and services (e.g., Record Labels, Music Reviewers, Radio Stations, etc.) rely on music curation & playlist creation, to establish their presence in their respective music scene. Currently, it is becoming increasingly difficult for emerging music businesses to establish their presence as “taste makers” due to the over saturation of the industry, and inability to put songs in their playlists that have the possibility to become popular. 

To combat this issue,  I am looking to see if it is possible to create a song popularity prediction system, to help these businesses choose songs that have the best chance of becoming popular, to apply to their playlists to achieve maximum visibility and exposure. I will be basing song popularity on a few metrics : Genre, Energy, and Danceability!


![image]

## Business Understanding

**Business Stakeholder**
- Businesses involved in the music industry (e.g., Record Labels, Music Reviewers, Radio Stations, etc.)

**Business Problem**
- It is becoming increasingly difficult for emerging music businesses to establish their presence as “taste makers” due to the over saturation of the industry, and inability to put songs in their playlists that have the possibility to become popular.

**Benefits**
- Increased presence within a specific music scene
- Increased popularity of business
- Increased revenue

## Data Understanding
Businesses would require the latest spotify music data to being making their song popularity predictions. 
For this project, the data being used comes from a spotify dataset that includes over 232,000 songs from 2019. 
The data set was acquired from Kaggle.com : 
https://www.kaggle.com/datasets/zaheenhamidani/ultimate-spotify-tracks-db
https://www.kaggle.com/datasets/reach2ashish/top-100-spotify-songs-2019
https://www.kaggle.com/datasets/leonardopena/top50spotify2019

This Kaggle dataset is suitable as it contains a plethora of song data from Spotify. We will explore the data, build machine learning models, and evaluate the performance of the models. 

**Variables in dataset:**

- **genre**: Genre of the song
- **artist_name**: Name of the artist who owns the song
- **track_name**: Name of the song
- **track_id**: Song ID
- **popularity**: How popular a specific song is
- **acousticness**: How acoustic sounding the song is
- **danceability**:How danceable the song is
- **duration_ms**: How long the song is
- **energy**: How much energy a song has
- **instrumentalness**: How dense in instrumentation is a song
- **key**: What key a song is in
- **liveness**: Does the song sound like it can be played live
- **loudness**: How loud can a song be
- **mode**: What mode is the song in
- **speechiness**: How are the vocals delivered
- **tempo**: What is the tempo of the song
- **time_signature**: What is the time signature of the song
- **valence**: What is the song valence

**(Figure 1) Cancellations per Month**

!![image](https://user-images.githubusercontent.com/110120531/216507065-a64edf7a-e1db-41ae-8637-84c577ef9621.png)

- City Hotel’s cancellations were consistent throughout the year
- Resort Hotel faced higher cancellation percentages during the Summer months

**(Figure 2) Effect of Deposit Type on Cancellations**

![image](https://user-images.githubusercontent.com/110120531/216507550-1946545b-2628-47b2-b2e8-3278fc225af5.png)

- Bookings with a non-refundable deposit were almost always cancelled
- Bookings with refundable deposits were least likely to get cancelled

**(Figure 3) Effect of Lead Time on Cancellations**

![image](https://user-images.githubusercontent.com/110120531/216508891-1ea306d3-7060-4157-ba00-92fcba806279.png)

- Lead time has a strong positive correlation with our target variable (is canceled)
- As lead time increases, the chance of cancellation increases

**(Figure 4) Effect of Returning Guests on Cancellations**

![image](https://user-images.githubusercontent.com/110120531/216508921-e4024fe0-5418-4b01-a0a4-660a962bb2ee.png)

- Guests that have never been to the hotel are more likely to cancel their booking
- Returning guests are less likely to cancel their booking

## Modeling and Evaluation

The two models I used were Logistic Regression (baseline model) and Random Forest Classifier. The Random Forest Classifier was tuned using GridSearchCV.

The metrics I used to evaluate the model performance were accuracy score and recall score. 

**(Table 2) Model Performance**
| Model | Accuracy | Recall Score |
|-------|----------|----------------------------|
| Logistic Regression | 81% | 95% |
| Classified Random Forest | 95% | 99% |
| Classified Random Forest Tuned | 87% | 99% |

## Conclusion

**Final Model**
The Random Forest Classifier is the ideal model, as it has an accuracy of 95% and a recall score of 99%.

**Limitations**
The limitations of this dataset is that there may be more factors that affect cancellation, such as the hotel’s location, the number of hotels around the area, and the hotel's rating.

**Next Steps for Improvements**
By gathering more data with extra columns and from more hotels, we would expect our model to perform even better because random forest's performance enhances with a larger data.
Once we have a larger data, we can also implement even more advanced models such as neural network. 

## Repository Navigation

**An explanation of the repository organization**
- hotel_bookings.csv : raw dataset used
- notebook.ipynb : jupyter notebook for EDA, data cleaning, modeling and evaluation
- CapstonePresentation.pdf : final presentation slides

**Links to the final notebook and presentation**
- [notebook.ipynb](.//notebook.ipynb)
- [CapstonePresentation.pdf](.//CapstonePresentation.pdf)

**Reproduction instructions**
- Download the raw dataset from Kaggle. (https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand)
- Download [notebook.ipynb](.//notebook.ipynb) to run EDA, perform data cleaning, modeling, and evaluation.


