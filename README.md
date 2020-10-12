# Pit Bull Pic <br>
<strong>(Python Image Classification)</strong>
<p> Problem Statement:
My goal is to use a Convolutional Neural Network (CNN) to create a model that’s able to distinguish between images of pit bulls and images of other breeds of dogs.
 <p>
<strong>Data Collection and EDA:</strong> <br>
For my work using the Petpy API, I gathered data from two different locations using a 500 mile radius. For my first scrape, I got 9813 dogs that didn't have all null values for the photo columns.  For my second scrape I got 9713.  My resulting dataframes had 49 columns and initially I was able to drop 24 of those because they wouldn't be useful to me. I then sorted through the remaining columns only keeping those that mention id, breed and photo.  I decided to select the largest photo size which had a width of 600.  I then created a breed list containing the large photo, the breed and the id.  I created breed directories using the 'breed.primary' column that the photos would be sorted into, and a parent directory called breed_dirs for the breed directories to be stored in. I then used pool.map for downloading the images. <br>
For the Stanford Dogs Data set I was able to just download 20,580 images from 120 different breeds.<p> Before data augmentation or modeling I manually cropped the images so that they were headshots with only slight angles to either side.<p>
<strong>Data Augmentation:</strong> <br>
Using Roboflow I was able to take 497 images and turn them into 1491. I created extra images by taking 25% of them and duplicating a black and white version. I also  created images by flipping them horizontally and changing the brightness.<p>
<strong>Modeling:</strong> <br> I used 4 2D pooling layers and three dropout layers in my model. I chose Binary Crossentropy as my loss function since there are only two label classes in my project, pit bull and non-pit bull.  For my validation data I used my testing dataset and I settled on a batch size of 16 after a lot of trial and error.
My testing accuracy is .651 <p>
<strong>Conclusion and future work:</strong> <br>
I will keep adding photos to my model and I would like to possibly expand my project to more breeds.  I would also like to figure out a way to utilize image labeling. With cvat you can actually create labels by tracing around any object in the image. So far I have only seen image labeling associated with object detection so I would like to do more research on that. I would also like to create a flask app to be able to upload images and run them through my model
