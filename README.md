# Data Engineering with Spotify Data 
# I310D Assignment 7, Spring 2023

## Table of Contents 
1. Introduction 
2. Project Goals
3. Documentation
4. Authorization Flow
5. Project Directory
6. Data

## Introduction
This project was completed as coursework for I310D: Introduction to Human-Centered Data Science at the University of Texas at Austin. The assignment required students to construct a dataset through extraction and processing, analyze the data set, and visualize some aspect of the data set in an open and reproducible manner. This project was completed in the Spring 2023 semester. 

## Project Goals
The goals of this project were as follows
- Access and extract playlist data on Spotify using Spotify Web API and Spotipy Python library
- Process data using data science libraries (Pandas, NumPy)
- Analyze and visualize data (SciPy, Matplotlib)
- Document all steps in research process properly
- Publish data in a reproducible and open format on data.world

## Documentation 
To complete this project, several APIs and Python libraries were used. Documentation for each library used is linked below
- [Spotify Web API](https://developer.spotify.com/documentation/web-api/)
- [Spotipy](https://spotipy.readthedocs.io/en/latest/)
- [Pandas](https://pandas.pydata.org/docs/)
- [NumPy](https://numpy.org/doc/stable/)
- [SciPy](https://docs.scipy.org/doc/scipy/)
- [Matplotlib](https://matplotlib.org/stable/#matplotlib-release-documentation)
    - [Pyplot](https://matplotlib.org/stable/tutorials/introductory/pyplot.html)
    
## Authorization Flow
To use the Spotify Web API and Spotipy, the environment and access tokens must be set up properly. This project utilized the Client Credentials authorization flow since the endpoints being accessed here do not involve user profile data. Determining the best authorization flow for a project can be done using [this](https://developer.spotify.com/documentation/general/guides/authorization/) information.

1. Sign up at Spotify for Developers at https://developer.spotify.com/ and select "Create an app". Write down your 'Client ID' and 'Client Secret'. While in the "Dashboard", select the "Edit settings" menu and in the "Redirect URIs" field fill the: http://localhost:7777/callback.
2. Open Spotify_Data_Manipulation_Python.ipynb and in the Authorization Flow code block, insert your Spotify username, Client ID, Client Secret and Redirect URI as cid, secret, redirect_uri and username, respectively.
3. Execute it. The first time Spotipy will need user authentication and will open a webpage, asking you to log in with your Spotify account and accept the permissions. After doing so, it will redirect you to a link. Copy the 'Redirect URI' and paste in the field that will appear in the Notebook. Hit 'enter'.
4. Now, you are connected to the Spotify API and capable to get your playlists ID, song IDs and use them to extract the features.

## Project Directory
[TaylorSwift_CompleteData.csv](https://github.com/sanjnasanand/Assignment_7_Data_Curation/blob/41c76fbab5ad68bb037f2f3cdf202e622be97bb6/TaylorSwift_CompleteData.csv) is the processed and cleaned data set 
[LICENSE.md](https://github.com/sanjnasanand/Assignment_7_Data_Curation/blob/41c76fbab5ad68bb037f2f3cdf202e622be97bb6/LICENSE) is the license for this project 
[Data_ETL_Analysis.ipynb](https://github.com/sanjnasanand/Assignment_7_Data_Curation/blob/41c76fbab5ad68bb037f2f3cdf202e622be97bb6/Data_ETL_Analysis.ipynb) is a documentation of all extraction, processing, and analysis performed in this project


## Data 
### Data Sources 
Data for this project was sourced from one public Spotify playlist, "Taylor Swift Complete Collection", created by Taylor Swift. This data was retrieved and tabulates using the Spotify Web API and Python data science libraries (see Documentation). This data does not carry a specific license but usage of the Spotify Web API must comply with this [policy](https://developer.spotify.com/policy/) and these [terms](https://developer.spotify.com/terms/). 

### Attributes
The data set [TaylorSwift_CompleteData.csv](https://github.com/sanjnasanand/Assignment_7_Data_Curation/blob/41c76fbab5ad68bb037f2f3cdf202e622be97bb6/TaylorSwift_CompleteData.csv) contains the following

| Attribute | Type | Description|
|:----------|:-----|:-----------|
| <no column title> | integer | Index of track in playlist |
| artist | string | Artist of track |
| album | string | Album track is located on |
| track_name | string | Name of track | 
| track_id | string | Unique Spotify ID for track | 
| danceability | float | Describes how suitable a track is for dancing based on a combination of musical elements including tempo, rhythm stability, beat strength, and overall regularity. A value of 0.0 is least danceable and 1.0 is most danceable.| 
| energy | float | A measure from 0.0 to 1.0 and represents a perceptual measure of intensity and activity. Features contributing to this attribute include dynamic range, perceived loudness, timbre, onset rate, and general entropy |
| valence | float | A measure from 0.0 to 1.0 describing the musical positiveness conveyed by a track. Tracks with high valence sound more positive (e.g. happy, cheerful, euphoric), while tracks with low valence sound more negative (e.g. sad, depressed, angry) |
| tempo | float | The overall estimated tempo of a track in beats per minute (BPM). In musical terminology, tempo is the speed or pace of a given piece and derives directly from the average beat duration. |
| duration_ms | integer | Duration of the track in milliseconds |
    
### Issues 
Possible issues with the data set include bias when the dataset was created. The data set may not be comprehensive of every song artist Taylor Swift has released on Spotify. Additionally, some of the columns were dropped during processing at the creator's discretion of usefuleness, some of which may have carried important data to consider in analysis. 