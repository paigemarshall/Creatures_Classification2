# Creature Classifications
An initial foray into machine learning and classification algorithms. 

I originally planned this to be a project using classification algorithms to predict creature types based on number of legs, number of wings (or lack thereof) length, height, and environment. I originally created the script and used hand keyed data. I then used the GaussianNB classifier from scikit-learn to predict creature types based on the data I provided. 

As a follow up, i then created a script that automates the data creation by taking the creature parameters: number of legs, numuber of wings, height, length, and environment and randomizing them to create several hundred samples of each classification: wyrm, wyvern, drake, dragon, serpent, and flying serpent. I then split that data set into a main set, and a test set, and then shuffled the data within them to avoid my ML model picking up on any unintended patterns. 

I then loaded those sets into my machine learning script for Naive Bayes, which is under creatures_ml.py. I used Pandas to clean and encode the data, using custom encodings I created so I could easily tell which samples belonged to which creature type, even when the classification was in numeric form. I also used custom encodings on the environment feature. After that, I used the train-test-split function from scikit-learn to train my model. I then used my random test set to see how well my model could do. Initially the model performed at about 80% accuracy. 

I then went back in and reworked the parameters for my data creation as there was quite a bit of overlap between different features for different creatures. I also tweaked the data creation scrpt to create two test sets instead of one. Once that was completed, I reran my main ML script using Gaussain Naive Bayes, and the model performed at 100% on both the training and the two test sets. 

I decided to also experiment with kmeans clustering on my main dataset, so I created a creatures_clustering.py script for that. I was able to clean the data using pandas and my custom encoding, and then I used matplotlib to plot comparisons between different features of my data and the final classification labels. The plots are located in the 'plots' folder. I then created a function to find the ideal number of clusters (k) for my data using the elbow method. I plotted my results and determined the best K for my data was 3. 

I then ran a kmeans model on my data, and plotted that out. I will need to explore this further, because though I could see centroids I could not see any gathering of my daa around the centroids. I am unsure if this was caused by overlaps in the data or perhaps because the data was more stacked as opposed to being continuous and spread out. Despite the woefulness of said model, I was able to build my Python skills, learn a little bit more about Naive Bayes classification, and I was also able to test the accuracy of my models. Feel free to clone the repo and use it for your own ML experiments!

UPDATE 4/10/20: The code for the Kmeans script now uses four clusters instead of three. After some tweaks I was able to see four very clear clusters of data. My previous code for plotting the different clusters was incorrect, and that is why I previously was unable to see the clusters. I think the model is pretty set. I did some more reading about Kmeans, and learned that I was not thinking about the model in the right way. It is not meant for predictions or classification in the same sense that the NaiveBayesGaussian was. It's meant to help identify trends within data without the aid of labels. There is no "training" or predictions, per se. With that understanding I realized that the way I planned to plot my results and evaluate them was not efficient. I made some adjustments, and the code should be set now. 
