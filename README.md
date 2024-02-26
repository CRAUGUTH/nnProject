# Music Genre Classification Project

Our project is aimed at developing a neural network capable of accurately classifying music based on its genre. The goal is to streamline the process of organizing Spotify songs by creating genre-specific playlists. To achieve this objective, we have structured our project into four primary stages, each comprising several sub-stages. 

## 1. Data Collection and Preparation

### 1.1 Data Sourcing:
We will begin by sourcing a dataset containing Spotify song statistics. This dataset will include essential features such as song-id, genre, danceability, loudness, and more. Our aim is to obtain a dataset that is both comprehensive and representative of various musical genres.

### 1.2 Data Cleaning and Preprocessing:
Upon acquiring the dataset, we will perform thorough cleaning and preprocessing to ensure data consistency and reliability. This step involves handling missing values, removing duplicates, and standardizing data formats. The goal is to prepare a clean and structured dataset ready for model training.

## 2. Integration with Personal Spotify Accounts

### 2.1 Utilizing Spotify API:
We will leverage the Spotify API to integrate our model with personal Spotify accounts. This integration will enable us to access users' liked songs playlists and retrieve additional song metadata and statistics directly from Spotify's database.

### 2.2 Playlist Management:
The integration will facilitate seamless playlist management, allowing users to create, update, and organize playlists based on their preferred genres. Users can easily sync their Spotify accounts with our system, streamlining the process of playlist curation.

## 3. Neural Network Development and Training

### 3.1 Identifying Genre Correlations:
In this phase, our objective is to develop a neural network capable of discerning correlations between Spotify statistics and music genres. For instance, songs characterized by high scores in metrics like loudness and energy may tend to belong to the "rock" genre, while those with elevated energy and danceability scores may align more closely with the "dance" genre.

### 3.2 Leveraging Song Statistics and Metadata:
Our approach involves utilizing both song statistics and metadata to enhance the model's classification accuracy. We will consider Spotify statistics such as tempo, danceability, and loudness as indicative features for genre classification. Additionally, we will incorporate metadata such as artist and album information as contextual cues, leveraging the tendency for artists to specialize in particular genres.

### 3.3 Training for Genre Discrimination:
Training the neural network entails exposing it to a diverse dataset encompassing songs from various genres. Through iterative training, the model learns to recognize and extract relevant features from the input data, refining its ability to accurately classify songs into their respective genres.

### 3.4 Evaluation and Validation:
Once trained, we will evaluate the model's performance in discriminating between different music genres. Utilizing evaluation metrics such as F1-score we will assess the model's effectiveness in generalizing genre classifications across a range of music samples. 

## 4. Creation of User-Friendly Interface

### 4.1 Interface Design and Prototyping:
We will design an intuitive and user-friendly interface to interact with our music genre classification system. The interface will feature responsive design principles, ensuring compatibility across various devices and screen sizes.

### 4.2 Integration with Backend Services:
The interface will be seamlessly integrated with the backend services, allowing real-time interaction with the classification model and Spotify API. Users can easily select playlists and initiate genre-based classification with minimal effort.

### 4.3 User Customization:
Users will have the option to select specific genres of playlists they want created, even further streamlining the process of organizing their personal playlists.

## Conclusion

Through the execution of these stages, we aim to create a comprehensive music genre classification system that streamlines playlist organization on Spotify.
(Intro/Conclusion, Stage 1, and Stage 2: Trent)
(Stage 3 and Stage 4: Conner)
(Formatting: ChatGPT)

# Data Collection

# Introduction
This dataset we found from Kaggle represents an extensive amount of musical data, comprising approximately 90,000 individual tracks along with their associated Spotify metadata. This metadata encapsulates a variety of attributes, ranging from rudimentary identifiers such as unique track IDs and artist names to more intricate features including time signature and genre classifications. The dataset contains over 125 distinct genres, cataloged within a structured CSV format.

# Link
For access to the dataset, refer to the following link: 
https://www.kaggle.com/datasets/maharshipandya/-spotify-tracks-dataset/download?datasetVersionNumber=1

# About the Data
Similar to the Canvas page , we advocate for a 60/20/20 allocation ratio for training, validation, and testing, respectively. This allocation scheme serves to mitigate the risk of inadvertently testing on songs already present within the training data, thereby strengthening the integrity of our evaluation process. The execution of this partitioning methodology will be conducted via a randomized distribution protocol, upholding a proportional representation of songs from each genre across all stages. This approach aims to preemptively neutralize any biases stemming from the over or underrepresentation of specific genres during the training phase, thus ensuring a more equitable learning trajectory.

The dataset comprises a vast array of nearly 90,000 unique musical compositions, spanning an expansive spectrum of over 125 distinct genres, each characterized by varying quantities of individual tracks. These attributes encompass foundational descriptors such as track IDs, artist identities, album titles, and track names, in addition to more nuanced features including popularity metrics, temporal durations, explicit content indicators, danceability scores, energy levels, musical keys, dynamic loudness profiles, modalities, vocal speechiness measures, acoustic signatures, instrumental propensities, live performance inclinations, emotional valences, rhythmic tempos, and time signature delineations. Numerical attributes such as danceability and energy exert a dominant presence within the dataset, while non-numeric attributes such as artist names and track titles simply help in the identification of each song.

# Sample of the data
Here are a few exemplar snippets from our expansive dataset:
[Download sample CSV file](sample.csv)
