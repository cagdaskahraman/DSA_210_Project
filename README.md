# DSA_210_Project

## Motivation 
I go to gym regularly and my performance may differ day from day. I always wonder what factors affect the performance. Of course I know eating, sleep affects but I wonder whether the music genre affects it or not. I use an app that saves the data of my workout details (eg. the weight that I lifted, the total volume of workout, the length of workout) named Hevy. The aim of the project is gain insights about how the music affects my performance and optimize my workout performance by listening proper music.

## Datasets

I will have two datasets. The first one is Hevy, I mentioned about it above. I will use the weight that I lifted and compare the workouts. The second one is Spotify. I will use the data restricted in workout times. I will collect the songs and their genres.

## Plan

I have a question and a clear purpose. So I know what data I should gather for my project. I am going to collect the datas, and ensure that datasets are reliable. After that, I'm going to clean the data(eg. perform necessary data type conversions...). After, I am going to conduct EDA, examine the statistical distribution, relationships, and general characteristics of the data, use visualization tools to identify trends, outliers, and patterns (e.g., histograms, scatter plots). Then, statistical models or machine learning algorithms going to be developed based on the analysis goals. Finally, I will have my results I achieved through data analysis, so I am planning to report my results.

# Report

## Data Overwiev

### Data Collection

The data for this analysis was collected from two primary sources:

Spotify: Information about songs, including genre, tempo, and energy levels, was exported from Spotify.

Hevy App: Workout logs, including exercise details, weights, repetitions, and timestamps, were exported from the Hevy application.

The datasets were combined to link music attributes with workout performance by matching timestamps.

### Data Exploration and Cleaning

Before the analysis, several data preparation steps were performed:

#### Handling Missing Values:

Entries with missing weights, reps, or timestamps were removed to ensure the integrity of calculations.

#### Outlier Removal:

Weight and repetition outliers were detected and filtered to prevent skewing the analysis.

#### Timestamp Processing:

Workout and music timestamps were converted to a consistent format.

Overlapping time intervals were identified to associate workout sessions with music attributes effectively.

#### Merging Datasets:

Both datasets were merged using strict interval matching to link each workout session with corresponding music data. Incomplete overlaps and mismatches were carefully handled to maximize dataset accuracy.

#### Translation Some Values:

For example, in the dataset of workout, the month names were in Turkish, and they were swapped with its English translations.

### Workout Data

The workout data included the following key metrics:

Exercise Title: The type of exercise performed.

Weight (kg): The weight lifted during each set.

Reps: The number of repetitions per set.

Total Weight: Calculated as weight_kg * reps.

Average Weight per Set: Derived as total_weight / reps.

### Music Data

The music data provided details about the songs played during workouts:

Genre: The genre of the music.

Tempo: Beats per minute (BPM) of the song.

Energy: A measure of the song's intensity and activity.

## Data Processing

Both datasets were merged based on timestamps to associate workout sessions with music attributes. During this process, overlapping time intervals between workout sessions and music playback were identified to link genres, tempo, and energy with specific workouts. Challenges included mismatched timestamps and missing data for certain sessions. Missing timestamps were handled by filtering out incomplete entries, and time overlaps were resolved using strict interval matching to ensure accurate associations.

All the data processing codes can be found in data_processing_and_visualization.ipynb file

## Key Findings

### Exploratory Data Analysis (EDA)

Before conducting statistical tests and modeling, the following exploratory data analysis steps were performed:

##### Distribution Visualizations: 
Histograms and boxplots were created for Tempo, Energy, and Average Weight per Set to identify data spread and potential outliers.

#### Correlation Analysis:
Scatter plots and correlation matrices were used to explore relationships between numerical variables (e.g., tempo, energy, and average weight per set).

#### Categorical Comparisons:
Bar plots compared performance metrics across different music genres and exercise types.

### Personal Preferences

Daily listening data and workout listening data is revealed and while in overall I listen every genre similary, I tend not to listen pop and classical music during workouts.

### Genre Impact

Analysis of average weight lifted per set revealed:

Phonk and Hip-Hop were associated with the highest average weight lifted per set.

Classical and Pop showed relatively lower performance impacts.

But there is no strong effect of genre on workout performance could be found based on visualized data as can be seen in data_processing_and_visualization.ipynb

### Tempo and Energy

Higher tempo songs were moderately correlated with increased weight lifting performance.

Energy levels showed a weaker, almost negligible correlation with performance.

### Statistical Analysis

Regression Analysis: Showed that tempo had a positive influence, while energy's impact was minimal.

## Machine Learning Model

### Linear Regression

A Linear Regression model provided additional interpretability:

Coefficient analysis confirmed the positive impact of tempo on performance and minimal influence of energy.

The codes related to this model can be found in "ml model using linear regression.ipynb".

## What Can Be Done

### Optimizing Workout Music

Incorporate high-tempo genres like Phonk and Hip-Hop to boost weightlifting performance.

Avoid low-energy or slow-tempo genres like Classical during high-intensity exercises.

### Model Improvements

Include additional features such as duration of music listening and user-specific preferences.

Experiment with advanced models (e.g., Gradient Boosting) for higher predictive accuracy.

## Conclusion

Music, particularly its tempo and genre, slightly impacts workout performance. By leveraging the insights from this analysis, individuals can optimize their music playlists to enhance their fitness outcomes. Further exploration of personalization and additional attributes can refine these findings.

## Limitations and Future Directions

### Limitations

#### Dataset Size and Scope:

The data collected was limited to specific users and a finite number of workout sessions, potentially reducing the generalizability of the findings.

Music preferences and workout styles vary significantly among individuals, which might not be fully captured in this dataset.

#### Music Attributes:

Only a subset of music attributes (genre, tempo, energy) was analyzed. Other factors like lyrics, mood, and volume could also influence performance.

#### Exercise Variability:

Different exercises may be affected differently by music attributes. For example, high-intensity exercises might benefit more from high-tempo music compared to steady-state exercises.

#### Model Limitations:

The Random Forest model, while effective, can be computationally intensive and may overfit smaller datasets. That is why it was not implemented. But if it was implemented succesfully, this model would be more accurate compared to linear regression model.

Linear Regression's simplicity might not fully capture complex relationships between features.

### Future Directions

#### Expanding the Dataset:

Collect data from a broader range of users with diverse demographics and fitness levels to improve generalizability.

#### Incorporating Additional Features:

Include more detailed music features like mood, lyrics sentiment, or user-defined preferences.

Analyze environmental factors such as gym noise or time of day.

### Improved Modeling Approaches:

Explore advanced machine learning models like Gradient Boosting or Neural Networks for higher accuracy.

Use time-series analysis to better understand how performance evolves during a workout session.

### Personalization:

Develop personalized models tailored to individual users based on their historical data and preferences.


