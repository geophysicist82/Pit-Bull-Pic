# Pit Bull Pic (Python Image Classification)
Problem Statement:
The purpose of my project is to use image classification to distinguish between photos of pit bulls and photos of other dogs.


Data Collection and EDA:
For my work using the Petpy API, I gathered data from two different locations using a 500 mile radius. For my first scrape, I got 9813 dogs that didn't have all null values for the photo columns.  For my second scrape I got 9713.  My resulting dataframes had 49 columns and initially I was able to drop 24 of those because they wouldn't be useful to me. I then sorted through the remaining columns only keeping those that mention id, breed and photo.  I decided to select the largest photo size which had a width of 600.  I then created a breed list containing the large photo, the breed and the id.  I created breed directories using the 'breed.primary' column that the photos would be sorted into, and a parent directory called breed_dirs for the breed directories to be stored in. I then used pool.map for downloading the images.
For the Stanford Dogs Data set I was able to just download 20,580 images from 120 different breeds.

Modeling:


Conclusion and future work:
I will keep adding photos to my model and I would like to expand my project to more breeds.


sources <p>
[Stanford Dogs Dataset](http://vision.stanford.edu/aditya86/ImageNetDogs/)

<a href="https://github.com/aschleg/petpy/tree/master/notebooks" target="_top">Aaron Schlegel's instructions on how to download 45,000 adoptable cat images with petpy</a>
