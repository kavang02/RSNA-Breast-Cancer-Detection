# Mammography

BREAST CANCER PREDICTION  

  

Breanna Moore, Amy McCaughan, Kenny VanGemert  

  

1. Problem Statement  

   

The problem we are trying to solve is detecting breast cancer from screening mammogram images. We want a low F1 score meaning that we were accurate in classifying breast cancer in patients who had it and did not have too many false positives or negatives. Having too many false positives or false negatives is bad for this problem because that can have drastic emotional and financial consequences on patients. The data consists of mammogram images taken during regular screenings that patients have.  

  

2. Data and Exploratory Analysis  

 

We got the data from Kaggle (https://www.kaggle.com/competitions/rsna-breast-cancer-detection/data) where the mammograms are in dicom format. There are normally 4 images per patient, but that is not always the case in the data.  

   

The data we are using is extremely large, the data is extremely clean with only the BIRADS column showing missing information. Based on this and the rest of the data, it can be assumed there was no reason for a follow up with that patient and that they do not have breast cancer.  

 

One other thing about this data is that the pictures are actual mammography's stored in a dcm file, which is what mammograms are stored in. These files are what is extraordinarily large, too large for us to work with directly without much stronger hardware. Therefore, the size of the images must be slimmed down, they currently range anywhere from (~2000, ~2000) to (~5500, ~2000), therefore they will need to drop in size to around (128, 128) for us to comfortably work with them.  

 

There are no outliers or impurities in the data set. We used the pydicom, os, and matplotlib libraries to print the images to the screen to better see what the images were showing. We used the TN Tech OnDemand access to the cluster to get the data on our computers. This is because the data is 314GB and we could not download it on our personal computers. Through OnDemand we can see the data in a shared folder as well as each of us have a personal folder to connect to Jupyter Notebook in and write the code for our models.  

 

We also have Git to push and pull the data and our models too so that we can stay organized. Other libraries that are used are pandas for working with the .csv files, torch for using the gpu and creating a tensor out of the data, NumPy for working with the data and sklearn and its different modules for the svm and results. 

 

Below are a few images showcasing how the mammogram images appear. Some have been pre-labeled stating the view of the breast directly on the image, whereas most of them do not, showing just the breast alone. 

 

 

As can be seen, the mammogram images that are of patient 10011 have been pre-labeled directly on the image, showing R for right, and MLO for mediolateral oblique view. Most images do not contain this; however, it is worth noting that some do. 

 

3. Methods  

  

The methods we are using are an SVM and if time allows, CNN as well. We chose these methods because we are dealing with many images and these models handle them well. For this same reason we ruled out using a regression model since we do not have only numeric data.  

 

The SVM will allow us to use a bit of a simpler model at first to almost use it as a baseline for determining how necessary the CNN may be. If the SVM does not turn out to be a smart choice, even after tuning, or the SVM provides satisfactory results and we want to see if there are better options, then a CNN will be used.  

 

We discovered that an SVM would not work well for our data because the other variables like machine id, and views were not working great with this type of model. In a neural network, these get assigned weights based on importance, however for the SVM, it would try and use those variables as a predictor. These variables, particularly the views, are somewhat important when looking at breast cancer since one breast may contain cancer whilst the other does not, meaning the SVM would not have a great time working with this data. 

 

CNN is one of the best choices for this data since instead of having to work around different variables like BIRADS, machine id, views, etc., we can just feed all the raw data into the CNN and have it learn on cancer recognition. This makes it not only more simplistic in terms of the work needing to be done, but also faster since we do not need to worry about separating out data and removing variables since the CNN will do that for us by applying the weights to the variables, choosing what is most important and what is not. CNNs are also one of the best choices when it comes to working with images, so to not use it would hinder the potential performance of any model that we create, since a CNN in this instance will tend to always be more accurate than any other model. Finally, a CNN is also a great choice because due to the potential accuracy that we can get, having a model that can truly understand and learn what it is we are training it on is the important thing, this may not be possible to do with say an SVM since the CNN can assign importance with more accuracy. 

 

GAN (generative adversarial network) could also be used to predict if a breast has cancer or not. GAN works by creating more synthetic data to train on so that it can get a high accuracy without overfitting the data. GAN consists of a generator and a discriminator. The generator learns to generate realistic-looking images of breast cancer tissue, while the discriminator learns to distinguish between real and synthetic images.  

  
   

4. Tools  

  

To download and view the entire dataset, we utilized Tennessee Tech’s Open OnDemand web interface to access the high-performance computing services provided to us. We are using this because this was where we were able to store all our data to utilize it through Jupyter notebook with python which is embedded in the OnDemand site.  

 

We installed the libraries pandas, TensorFlow, and NumPy for the code so that we could run the models. We tried using deepnote but we were only able to download 5GB of the 314GB of data into the notebook.  


7. Appendix  

The link to our GitHub is:
https://github.com/fivefootbot/Mammography  


The link to the kaggle dataset we are using: 
https://www.kaggle.com/competitions/rsna-breast-cancer-detection/data
