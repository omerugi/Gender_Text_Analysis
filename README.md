# Gender From Text Analysis
_Created by:_ Omer Rugi - [omerihay@gmail.com](mailto:omerihay@gmail.com)

## The drive behind the project
As part of my ongoing learning process in the field of ML\DL, I took this task to play around with NLP.
This is my first attempt in NLP and wanted to share what I did.

## The task
To better understand human behavior we can analyze texts that people have written and get some deeper knowledge of how they act based on a profile we build, there are many aspects that can contribute but here we will focus on one. 
In this project, the one aspect we will focus on is - determining the gender of the author based on the text they wrote!

We will use ML to do so, using a pipeline to preprocess the data and get features from text and then classify using ML models.
# Dataset
The dataset contains 754 samples were:
* ``gender`` - is the target column, represents the authors gender  ``m = men f=women``.
* ``story`` - the text the author wrote.

## Dataset analysis:
![image](https://user-images.githubusercontent.com/57361655/151162130-40e8de81-15da-4a9a-979b-03ce76113e1a.png)
![image](https://user-images.githubusercontent.com/57361655/151162204-acfd640c-5b7b-414b-baf8-be49731c57f8.png)

Lenght of text:

![image](https://user-images.githubusercontent.com/57361655/151162319-a31cb3cb-65c3-4b27-994f-e8ae3d8526b5.png)

# Preprocessing
1. Regex for text cleaning - used regex to find all digits, punctuation and double spaces, and remove them from each sample.
2. TD-iDF - with this method we can take a corpus of texts to get keywords as features based on their rarity in different samples, then count the number of occurrences of those features in each sample. From that we got 200 featuers.
3. Standard Scaler - to normelize our data.
4. PCA - with this method we are reducing the features to 80. 
5. Label Encoder - on the target featuer `` f = 0 m = 1``.
6. Over Sampling - due to the fact that we have a small number of females compared to men, we used oversampling. We duplicated female samples that are in the mid-average length of text.
7. Train Test Split - splitting the test samples into train and test - when 0.33 are test and we used stratify to get even amount of smaples in the splite.

# Models
For each model we have used `` Grid Search`` to find the best hyperparameters.
* KNN results:

![image](https://user-images.githubusercontent.com/57361655/151165405-58fe2716-596d-4cee-8b0d-a18c41eae94e.png)

* MLP results:

![image](https://user-images.githubusercontent.com/57361655/151165494-be08bfd9-5be9-479a-b3bc-62571d02bcaf.png)
