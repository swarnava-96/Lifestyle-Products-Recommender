# Lifestyle-Products-Recommender

### Goal: The goal of this project is to create a lifestyle products ecommerce store as a POC that uses reverse image search.
Here the end user will have to upload an image of the fashion product he or she is looking for and the model in turn will recommend similar products.

### About the data set: 
1. The dataset contains images of dresses, watches, shoes, and other such lifestyle/fashion products.
2. The dataset [here](https://www.kaggle.com/paramaggarwal/fashion-product-images-dataset) is the original dataset, which is of 16GB.
But, in this project I have used this [dataset](https://www.kaggle.com/paramaggarwal/fashion-product-images-small),which is
of 572MB. Both the datasets contains the same number of images ie, 44k, just the difference is that in the original dataset
the image resolutions are higher compared to the smaller dataset.
3. Using the smaller dataset is some what advantgeous as either way we have to scale down the pixel size of images for providing it as an input
to our model. It also saves computational power as I have limited system resources.  

### Project Outline:
1. The code written for this project is a generic code that can be applied to similar other such datasets.
2. The first step that I took is to import the Transfer Learning model. I have used ResNet50 for this project.
3. I have not trained the model as ResNet model is alredy trained on imagenet. I have used the model for extracting the features of the images.
Feature by feature extraction was performed for each image.
4. Finally, for the recommendation part, I have used Scikit Learn's Nearest Neighbors algorithm which will give the five most nearest vectors/neighbors
based on Euclidean distance.
5. I have used streamlit to create an application out of it and deployed locally(localhost:8501)

### Installation:
The Code is written in Python 3.7.3 If you don't have Python installed you can find it [here](https://www.python.org/downloads/). If you are using a lower version of Python you can upgrade using the pip package, ensuring you have the latest version of pip. To install the required packages and libraries, run this command in the project directory after [cloning](https://www.howtogeek.com/451360/how-to-clone-a-github-repository/) the repository:

##### 1. First create a virtual environment by using this command:
```bash
conda create -n myenv python=3.7
```
##### 2. Activate the environment using the below command:
```bash
conda activate myenv
```
##### 3. Then install all the packages by using the following command
```bash
pip install -r requirements.txt
```
##### 4. Download the dataset folder from [here](https://www.kaggle.com/paramaggarwal/fashion-product-images-small) and place it in the same working directory.

##### 5. Download the model files from [here](https://drive.google.com/drive/folders/1iSlD4KMTGsSY_r-RGGTwd4DtOtmXG_yK?usp=sharing) and put it in the same working directory as of the other files like app.py and the dataset folder.

##### 6. Then, in cmd or Anaconda prompt write the following code:
```bash
streamlit run app.py
```
##### Make sure to change the directory to the root folder.  

### A glimpse of the application:
![Screenshot (184)](https://user-images.githubusercontent.com/75041273/135233035-a07eef75-8b44-474b-b6a1-825d6df4b7bd.png)
![Screenshot (182)](https://user-images.githubusercontent.com/75041273/135233402-cf211550-7385-4fc5-930b-2de0bfcf53e1.png)
![Screenshot (183)](https://user-images.githubusercontent.com/75041273/135233241-9fa6f13f-1d3e-4b8b-9a14-4b5b64b6f70f.png)

### Further Changes to be Done
- [ ]  The project is not complete. I have thought some more things like:
      1. Scraping data from ecommerce websites like Amazon, Flipkart rather than relying totally on kaggle dataset.
      2. Storing the data set of images in some cloud storage platforms like Amazon S3 instead of local machine.
      3. Using python to create a connection with the S3 for using the data.
      4. Using Annoy, a library from Spotify for recommendation insted of Scikit-Learn's Nearest Neighbors. This will optimize the code and make it faster for 
         larger datasets. 

- [ ] Deploying the Web Application on Cloud.
     - [ ] Google Cloud 
     - [ ] Azure
     - [ ] AWS EC2
     - [ ] Heroku
