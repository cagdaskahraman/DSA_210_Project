# DSA_210_Project

## Motivation 
I go to gym regularly and my performance may differ day from day. I always wonder what factors affect the performance. Of course I know eating, sleep affects but I wonder whether the music genre affects it or not. I use an app that saves the data of my workout details (eg. the weight that I lifted, the total volume of workout, the length of workout) named Hevy. The aim of the project is gain insights about how the music affects my performance and optimize my workout performance by listening proper music.

## Datasets

I will have two datasets. The first one is Hevy, I mentioned about it above. I will use the weight that I lifted and compare the workouts. The second one is Spotify. I will use the data restricted in workout times. I will collect the songs and their genres.

## Plan

I have a question and a clear purpose. So I know what data I should gather for my project. I am going to collect the datas, and ensure that datasets are reliable. After that, I'm going to clean the data(eg. perform necessary data type conversions...). After, I am going to conduct EDA, examine the statistical distribution, relationships, and general characteristics of the data, use visualization tools to identify trends, outliers, and patterns (e.g., histograms, scatter plots). Then, statistical models or machine learning algorithms going to be developed based on the analysis goals. Finally, I will have my results I achieved through data analysis, so I am planning to report my results.

# Report

## Data Overwiev

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

## Key Findings

#### Genre Impact

Analysis of average weight lifted per set revealed:

Phonk and Hip-Hop were associated with the highest average weight lifted per set.

Classical and Pop showed relatively lower performance impacts.

#### Tempo and Energy

Higher tempo songs were moderately correlated with increased weight lifting performance.

Energy levels showed a weaker, almost negligible correlation with performance.

#### Statistical Analysis

ANOVA Test: Indicated significant differences in performance across genres (p < 0.05).

Regression Analysis: Showed that tempo had a positive influence, while energy's impact was minimal.
