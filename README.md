# Song Popularity Predicter
By Luis Estrada

Many music related businesses and services (e.g., Record Labels, Music Reviewers, Radio Stations, etc.) rely on music curation & playlist creation, to establish their presence in their respective music scene. Currently, it is becoming increasingly difficult for emerging music businesses to establish their presence as “taste makers” due to the over saturation of the industry, and inability to put songs in their playlists that have the possibility to become popular. 

To combat this issue,  I am looking to see if it is possible to create a song popularity prediction system, to help these businesses choose songs that have the best chance of becoming popular, to apply to their playlists to achieve maximum visibility and exposure. I will be basing song popularity on a few metrics : Genre, Energy, and Danceability!


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

## Data Preparation
### Data Cleaning: Scrubbing
#### Original song dataset contained duplicative information.
**Example 1**: The genre “Children’s Music” shows up twice in the data set. I had to merge the two “Children’s Music” values to achieve consistency
**Example 2**: There were a total of 55,951 duplicative song tracks in the dataset. I had to aggregate all of the duplicate songs into a single row
### Data Cleaning: One Hot Encoding
In order to pre-process most of the categorical features of my dataset for my machine learning models, I had to do some one hot encoding.
### Data Cleaning: Outlier Removal
- When viewing song popularity from the top 100 songs on Spotify from 2019, there were a big number of outliers, which would skew my results if I kept in.
- I performed an Interquartile Range method to remove my dataset of any statistical outliers

## Modeling and Evaluation

The two models I used were dummy classifer (baseline model) and Random Forest Classifier. 
The Random Forest Classifier was tuned using GridSearchCV.

The metrics I used to evaluate the model performance were accuracy score and recall score.

The models are available for view in the attached powerpoint

**Model Performance**
| Model | Accuracy | Recall Score |
|-------|----------|----------------------------|
| Dummy Classifier| 50% | 51% |
| Classified Random Forest | 93% | 97% |
| Classified Random Forest Tuned | 93% | 98% |

## Conclusion

**Final Model**
The Random Forest Classifier is the ideal model, as it has an accuracy of 93% and a recall score of 98%

**Limitations**
The limitations of this dataset may be that there are not enough song attributes, which may affect the integrity of this project slightly.

**Next Steps for Improvements**
The ideal next step for improvement, would be to gather more song data, from the latest year (2022), to have a more accurate assessment of what songs may be popular, since some genres/song types fade in popularity with time.

## Repository Navigation

**An explanation of the repository organization**
- Capstone Project Proposal.pdf : Capstone Proposal
- Official Final Project.ipynb : jupyter notebook for EDA, data cleaning, modeling and evaluation. NOTE: THIS IS THE MAIN NOTEBOOK, DO NOT USE THE ONE TITLED "Final Project.ipynb" - I was having difficulty deleting it.
- README.md : The readme that you are currently reading.
- SpotifyFeatures.csv: The main song data set I used
- danceability.jpg: A chart showing songs with high danceability
- energy.jpg: A chart showing songs with the highest energy
- genre-popular: A bar chart showing popular genres
- genre-unpopular: A bar chart showing unpopular genres
- spotify_top_100_2019.csv: A spotify dataset I used that has the top 100 songs for the year 2019
- top50.csv: Another spotify dataset I used that has the top 50 songs for the year 2019


**Reproduction instructions**
- Download the raw datasets from Kaggle:
- https://www.kaggle.com/datasets/zaheenhamidani/ultimate-spotify-tracks-db
- https://www.kaggle.com/datasets/reach2ashish/top-100-spotify-songs-2019
- https://www.kaggle.com/datasets/leonardopena/top50spotify2019
- 
- Download Official Final Project.ipynb notebook to run EDA, perform data cleaning, modeling, and evaluation.


