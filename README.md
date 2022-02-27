# Song Classifier based on Language

## Executive Summary
The aim of our project was to create a song recommender model that is able to recommend songs based on the songs audio features as well as depending on whether the language of the songs matter to you or not (you can adjust weight accordingly). In other words, you could increase the alpha if you care about the recommended songs to be of the same language as your other songs or decrease it otherwise and based on that information, you are able to create a playlist of a length of your choice.

This playlist is created using K Nearest Neighbors (playlist length is the number of neighbors you specify) and essentially you will have a playlist with songs of similar audio features and of same/different languages depending on your preference. Our graph in the results section displays the difference of the k nearest neighbors song results when the weight of language is 0 versus when you increase the weight of the language which moves away the other languages and moves the sample size language songs closer.

For example, the first song we picked was in English and you are able to visually see all the non-english songs moving away from the sample point and all the english songs moving towards it because the KNN model is gathering songs of same features as well as same language (discussed and displayed further in results section).

## Introduction
Spotify currently has no way to filter or recommend songs by language. This means that a user cannot use language as a feature when searching for songs to listen to. Our goal with this project is to create a model that when given a small selection of songs, can recommend new songs to listen to based on both Spotify's built in features and using information about the language of the given songs.

In our project, we created a dataset of songs on Spotify, enhanced with the values of Spotify's built in features for each given song and percentages of all of the different languages present on a line-by-line basis in each song. This dataset was made up of 1000 songs, taken from the top 200 trending from five countries -- India, Argentina, Morocco, France, and the US. We plan on using this data to create a classifier that will recommend songs based on both Spotify's built-in song features and languages present in a song.

## Data Description
Web scraped the top 200 songs from 5 different markets (India, Argentina, Morocco, France, US) using the Spotify

![](./img/spotify.png)

## Method
The main ML tool we intended to use was a K-nearest Neighbors classifier. We intended to model our implementation off of Sci-Kit Learn.

The goal of our project was to try to classify songs that are most similar to a specified language or features. Since the purpose of a KNN model is to find the K most similar objects to a given value, this makes this technique a good model for our task at hand. For example, if K = 2, it would return the two nearest vectors (or songs in this case) which represent the closest songs to the language and features in the given song.

How we intended to use this technique was to have all of the songs in a database act as individual vectors, where each feature is a value in the vector. All the songs would be represented in the vector space. The KNN would take a given song with its own vector feature values and locate the K-nearest neigbors using Euclidean distance. There are markdowns throughout the report to help guide the thought process behind each of the method steps and the steps to fix particular problems.

All limitations/pitfalls have been discussed further in the discussion section.

### Method Steps

1. Scale Normalization: to ensure all our features are scaled appropriately amongst all features to be able to compare them correctly
2. Weighting features: function to weight a specific feature group more over the other based on a specific alpha valuue
3. Euclidean distance function: to calculate the distance between points and then define the similarity between them
4. K-Nearest Neighbors: use a database in which the data points are separated into several columns to predict the classification of new sample points

## Results

**Witnessing the role of language features in the recommendation of similar songs**\
Choose a sample
Generate k-nearest neighbors with the audio features
Plot the sample and it's recommendation with the sample as the origin and the recommendation rotate over it with the radius being it's euclidean distance
Do step 2 and 3 with the audio and language features together
