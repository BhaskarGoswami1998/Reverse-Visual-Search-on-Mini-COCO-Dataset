This is the Assignment for Reseverse Visual Search for the Mini COCO Dataset for the class labeled person. We are using the Fast RCNN with ResNet50 backbone to get the bounding boxes of all the persons in the 13K images for mini coco dataset. After that we document them all along with the image details and bounding box details in the form of a JSON.
After that, we look into 5 random bounding boxes and try to find the 10 most similar bounding boxes that are not part of the same image as a part of this project.


In many domains we are interested in finding artifacts that are similar to a query artifact. In this assignment you are going to implement a system that can find artifacts when the queries are visual.

The type of queries you will test your system on are MS COCO dataset images.

4.1
We look into the COCO Dataset and look at all the images that have atleast one label of a person. We make a list of all the image names that have such labels and copy those images to a seperate folder names "train 2017 person". This folder was uploaded into Google Drive and used in the assignment.

4.2
We use a pretrained Faster RCNN with ResNet50 Backbone to get the bounding boxes of all the objects as detections and keep only those that have a lable 1 : "Person".
We keep the bounding box details (Top Left X, Top Left Y, Width and Height) along with image name, label, probability of that bounding box having a person.

4.3
To create the feature vectors of the bounding boxes we employ the following approach.
We iterate through the previously defined dataframe that has all the person bounding boxes and then preprocess them as we would an image which is being used as an input to the pretrained Faster RCNN. Then we use the transform function along with the backbone function. We extract the "pool" layer of the output feature vector, it contains the feature vector that we will be using to compare two images and comment about the magnitude of similarity between two images.

4.4
For the final question of the assignment we select 5 random bounding boxes( from the previously created dataset).
We iterate through the entire dataset and look at all the images that donot have the bounding box as a part and then compare their cosine similarity. We print the images and bounding box information of the 10 similar bounding box to each of the 5 randomly chosen ones.

This completes the Reverse Image Search Assignment for CS 634 007 NJIT.



