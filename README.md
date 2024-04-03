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

## Introduction
This dataset we found from Kaggle represents an extensive amount of musical data, comprising approximately 90,000 individual tracks along with their associated Spotify metadata. This metadata encapsulates a variety of attributes, ranging from rudimentary identifiers such as unique track IDs and artist names to more intricate features including time signature and genre classifications. The dataset contains over 125 distinct genres, cataloged within a structured CSV format.

## Link
For access to the dataset, refer to the following link: 
https://www.kaggle.com/datasets/maharshipandya/-spotify-tracks-dataset/download?datasetVersionNumber=1

## About the Data
Similar to the Canvas page , we advocate for a 60/20/20 allocation ratio for training, validation, and testing, respectively. This allocation scheme serves to mitigate the risk of inadvertently testing on songs already present within the training data, thereby strengthening the integrity of our evaluation process. The execution of this partitioning methodology will be conducted via a randomized distribution protocol, upholding a proportional representation of songs from each genre across all stages. This approach aims to preemptively neutralize any biases stemming from the over or underrepresentation of specific genres during the training phase, thus ensuring a more equitable learning trajectory.

The dataset comprises a vast array of nearly 90,000 unique musical compositions, spanning an expansive spectrum of over 125 distinct genres, each characterized by varying quantities of individual tracks. These attributes encompass foundational descriptors such as track IDs, artist identities, album titles, and track names, in addition to more nuanced features including popularity metrics, temporal durations, explicit content indicators, danceability scores, energy levels, musical keys, dynamic loudness profiles, modalities, vocal speechiness measures, acoustic signatures, instrumental propensities, live performance inclinations, emotional valences, rhythmic tempos, and time signature delineations. Numerical attributes such as danceability and energy exert a dominant presence within the dataset, while non-numeric attributes such as artist names and track titles simply help in the identification of each song.

## Sample of the data
Here are a few exemplar snippets from our expansive dataset:
[Download sample CSV file](sample.csv)

# First Solution and Validation Accuracy

## Introduction

Diving into music genre classification through deep learning reveals both challenges and opportunities. When attempting to distinguish between rock and classical music just by looking at the data, it becomes apparent it's not just about the beats per minute or the presence of electric guitars but understanding the essence of what makes a genre unique. This is where a Multilayer Perceptron (MLP) comes into play. MLPs are adept at deciphering the complex, layered information within music tracks, from the song's time signature to its ‘danceability’, making them an ideal candidate for this task of classifying songs by interpreted genre.

## Neural Network Architecture Justification

### Why a Multilayer Perceptron (MLP) neural network?

- **Deciphering Complex Patterns**: Music genres are a complex mix of rhythms, tempos, and harmonies. MLPs shine in picking apart these intricate details, learning to identify the subtle differences that our ears might miss.

- **Straightforward and Powerful**: An MLP's structure is relatively simple—input, hidden layers, output, making its implementation relatively simple. Although simple, MLPs have the power to model the boundaries that separate genres, no matter how blended or nuanced.

- **Scalability for Songs**: With the vast amount of music available, any model we use needs to handle big datasets. Again, MLPs are perfect for this, especially when trained with efficient algorithms like Adam, ensuring they can learn from as many tracks as possible.

- **Integrating Musical Features**: Whether it's the tempo or the instrumentalness, MLPs can take in a wide range of musical features and learn their importance for genre classification, making accurate predictions based on the data.

## Input Layer

The dimensionality of the input layer directly corresponds to the number of features extracted from the music tracks. These features are crucial as they encapsulate the essence of the audio signal, including acousticness, tempo, danceability, energy, and speechiness. Selecting a comprehensive set of features is most important to enable the network to discern the nuanced differences between genres.

In the present configuration of our model, we've opted to utilize the full spectrum of features available from Spotify (each one transformable into a numerical float) to guide the classification of songs into their respective genres. Yet, the true ambition of our endeavor extends beyond the breadth of data at our disposal. Our vision zeroes in on achieving genre classification with a minimalist approach, to refine the essence of genre identification to the leanest possible set of musical features. This pursuit not only promises a model that's sleek and efficient but also challenges us to uncover which attributes are truly pivotal in distinguishing one genre from another, marking a step towards a more refined and focused application of deep learning in music analysis.

## Hidden Layers

The architecture includes two densely connected hidden layers with 256 and 128 neurons, respectively. This configuration has been selected to strike a balance between model complexity and computational efficiency.

- **ReLU Activation**: The Rectified Linear Unit (ReLU) function is chosen for its ability to introduce non-linearity without affecting the gradients significantly, which helps in alleviating the vanishing gradient problem.

- **Batch Normalization**: This technique normalizes the input to each layer to have a mean of zero and a variance of one. It stabilizes the learning process and has been shown to accelerate convergence.

- **Dropout**: A dropout rate of 0.2 helps prevent overfitting by randomly dropping units (along with their connections) during the training phase. This forces the network to learn redundant representations and improves generalization.

## Output Layer and Loss Function

The softmax function in the output layer provides a probability distribution over the genre classes, allowing for a direct interpretation of the model's predictions as confidence scores. Cross-Entropy Loss is adept at comparing the predicted probability distribution with the true distribution, making it a natural fit for classification tasks.

## Optimization Algorithm

Adam is selected for its adaptive learning rate properties, which adjust the learning rate for each parameter based on estimations of the first and second moments of the gradients. This adaptability makes Adam highly efficient for tasks with large and high-dimensional datasets.

## Classification Accuracy and Performance Metrics

The progression of training and validation accuracy over epochs illustrates the model's ability to learn effectively from the dataset. A notable achievement is the model's validation accuracy, which outperforms the training accuracy in the later epochs. This unusual pattern suggests a well-generalizing model, possibly due to effective regularization strategies like dropout and batch normalization.

The F1 score, chosen for its sensitivity to the balance between precision and recall, further validates the model's performance. Given the imbalanced nature of music datasets, where some genres may be more prevalent than others, the F1 score provides a more accurate reflection of the model's effectiveness across all genres.

## Observations and Improvement Ideas

Despite our model's achievements, there's always scope for refinement in the realm of machine learning projects. The observed discrepancy between training and validation performance metrics hints at potential overfitting issues, even with our current preventive strategies. Notably, our model's medal accuracy plateauing at 82% is far from ideal, underscoring the necessity for further optimization and adjustment. This gap between our expectations and the current performance not only highlights the challenges inherent in achieving high accuracy with minimal features but also serves as a motivator for exploring innovative strategies to enhance model efficacy and generalizability.

- **Exploring Architectures**: Additional layers or different setups could reveal patterns we're currently missing.

- **Enhanced Regularization**: Tweaking dropout rates or integrating L2 regularization might tighten the model's focus, reducing overfitting.

- **Optimization Tweaks**: Fine-tuning Adam's settings or exploring new algorithms could refine the learning process.

## Conclusion

This deep dive into using an MLP for music genre classification has highlighted the architecture's suitability and the potential for further refinement. The journey from input to output layer, through the challenges of learning and generalization, showcases the balance struck between model complexity and performance. Future improvements, rooted in data augmentation, architectural adjustments, and optimization tweaks, have the potential to enhance the model's accuracy and applicability, pushing the boundaries of what's possible in music information retrieval.

## Team Contributions

- **Conner Rauguth**: 
  - Implemented MusicData class.
  - Modified given ‘evaluate’ function.
  - Experimented with different optimizers and schedulers to improve model accuracy.
  - Wrote Introduction and Observation and Improvement Ideas sections.

- **Trent Delp**: 
  - Implemented MLP class.
  - Implemented f1 score calculation.
  - Modified given training loop.
  - Wrote Neural Network architecture justification and Conclusion sections.

(Note: Every implementation has been reviewed by the other with unmentioned features being implemented in collaboration)
