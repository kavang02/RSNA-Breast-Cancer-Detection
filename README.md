# Mammography

BREAST CANCER PREDICTION  

  

Breanna Moore, Amy McCaughan, Kenny VanGemert  

  
1. Problem Statement  

The problem we are trying to solve is detecting breast cancer from screening mammogram images. We want a low F1 score meaning that we were accurate in classifying breast cancer in patients who had it and did not have too many false positives or negatives. Having too many false positives or false negatives is bad for this problem because that can have drastic emotional and financial consequences on patients. The data consists of mammogram images taken during regular screenings that patients have.   

2. Data and Exploratory Analysis  

The data we are using is extremely large, the data is extremely clean with only the BIRADS column showing missing information. Based on this and the rest of the data, it can be assumed there was no reason for a follow up with that patient and that they do not have breast cancer. One other thing about this data is that the pictures are actual mammography's stored in a dcm file, which is what mammograms are stored in. These files are what’s extraordinarily large, too large for us to work with directly without much stronger hardware. Therefore, the size of the images must be slimmed down, they currently range anywhere from (~2000, ~2000) to (~5500, ~2000), therefore they will need to drop in size to around (128, 128) for us to comfortably work with them There are no outliers or impurities in the data set. We used the pydicom, os, and matplotlib libraries to print the images to the screen to better see what the images were showing. We used the TN Tech OnDemand access to the cluster to get the data on our computers. This is because the data is 314GB and we could not download it on our personal computers. Through OnDemand we can see the data in a shared folder as well as each of us have a personal folder to connect to Jupyter Notebook in and write the code for our models. We also have Git to push and pull the data and our models too so that we can stay organized. Other libraries that are used are pandas for working with the .csv files, torch for using the gpu and creating a tensor out of the data, NumPy for working with the data and sklearn and its different modules for the svm and results. 

//Resize object for images 

resize_transform = Resize((128, 128))  

//Converts imgs to pixel_array 

image = ds.pixel_array.astype(float) 
                     
//Convert the image to a PyTorch tensor on GPU 

//Removing .to(device) will not use GPU 

image_tensor = torch.tensor(image).unsqueeze(0).to(device) 
                     
//Resize the image 

image_tensor = resize_transform(image_tensor) 

3. Methods  

The methods we are using are an SVM and if time allows, CNN as well. We chose these methods because we are dealing with many images and these models handle them well. For this same reason we ruled out using a regression model since we do not have only numeric data. The SVM will allow us to use a bit of a simpler model at first to almost use it as a baseline for determining how necessary the CNN may be. If the SVM does not turn out to be a great choice, even after tuning, or the SVM provides good results and we want to see if there are better options, then a CNN will be used.  

4. Tools  

To download and view the entire dataset, we utilized Tennessee Tech’s Open OnDemand web interface to access the high-performance computing services provided to us. We are using this because this was where we were able to store all our data to utilize it through jupyter notebook which is embedded in the OnDemand site. We tried using deepnote but we were only able to download 5GB of the 314GB of data into the notebook.

The link to the kaggle dataset we are using: 
https://www.kaggle.com/competitions/rsna-breast-cancer-detection/data
