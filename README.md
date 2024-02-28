# Mammography

BREAST CANCER PREDICTION  

  

Breanna Moore, Amy McCaughan, Kenny VanGemert  

  
1. Problem Statement  

The problem we are trying to solve is detecting breast cancer from screening mammogram images. We want a low F1 score meaning that we were accurate in classifying     breast cancer in patients who had it and did not have too many false positives or negatives. Having too many false positives or false negatives is bad for this problem because that can have drastic emotional and financial consequences on patients. The data consists of mammogram images taken during regular screenings that patients have.   

2. Data and Exploratory Analysis  

The data we are using is extremely large, the data is extremely clean with only the BIRADS column showing missing information. Based on this and the rest of the data, it can be assumed there was no reason for a follow up with that patient and that they do not have breast cancer. There are no outliers or impurities in the data set. We used the pydicom, os, and matplotlib libraries to print the images to the screen to better see what the images were showing. We used the tntech OnDemand access to the cluster to get the data on our computers. This is because the data is 314GB and we could not download it on our personal computers. Through OnDemand we can see the data in a shared folder as well as each of us have a personal folder to connect to Jupyter Notebook in and write the code for our models. We also have Git to push and pull the data and our models too so that we can stay organized.   

3. Methods  

The methods we are using are a SVM and if time allows a CNN as well. We chose these methods because we are dealing with many images and these models handle them well. For this same reason we ruled out using a regression model since we do not have only numeric data.  

4. Tools  

In order to download and view the entire dataset, we utilized Tennessee Tech’s Open Ondemand web interface to access the high performance computing services provided to us. We are using this because this was where we were able to store all of our data to utilize it through jupyter notebook which is embedded in the ondemand site. We tried using deepnote but we were only able to download 5GB of the 314GB of data into the notebook.  

The link to the kaggle dataset we are using: 
https://www.kaggle.com/competitions/rsna-breast-cancer-detection/data
