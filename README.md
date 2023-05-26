# Stroke Prediction Machine Learning Model

## Project Description

Stroke is a serious medical condition that occurs when the blood supply to part of the brain is interrupted or reduced, leading to brain damage and potential long-term disability or death. The risk of stroke is affected by a wide range of factors, including age, gender, hypertension, heart disease, obesity, and smoking. 

Detecting a stroke in its early stages brings numerous advantages, including timely medical intervention, reduced brain damage, prevention of long-term disabilities, identification of underlying causes, and the facilitation of swift medical decision-making to optimize patient outcomes.

For this project, our objective is to create a machine learning model for early stroke detection, focusing on various causative factors. This model aims to assist clinical teams in predicting or assessing the risk of stroke occurrence, enabling timely medical intervention, minimizing brain damage, preventing long-term disabilities, identifying underlying causes, and facilitating quick medical decision-making to optimize patient outcomes.

##  Data Overview

The [stroke dataset](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset?select=healthcare-dataset-stroke-data.csv) comprises a compilation of patients' medical records. It encompasses a wide range of information, including patient demographics, medical history, lifestyle factors, and the presence or absence of a stroke for each patient.

Here is a snippet of the dataset: 
![image](https://github.com/yeyanwang/stroke_classifier/assets/120543690/7502f72d-72be-43a2-8c5c-eb2c1668f1df)

## Built With 
- Python and Packages (eg. scikit-learn, matplotlib, searborn, pickle, etc.)
- Flask
- HTML
- CSS

## Getting Started 
**Prerequisites**

Make sure you have installed all of the following prerequisites on your development machine:
- Git
- Python and set up your virtual environment
- `pip install flask` globally
- Your favoriate code editor (e.g. VScode, etc.)
- Your favoriate browser (e.g. Google Chrome, etc.)

**Installation**

1. Clone this repo and save it in your local directory, to clone with URL run the following code in terminal
  
     `https://github.com/MeerKar/stroke_classifier`
  
2. Start Flask app by running the following code in terminal

     `python app.py`
  
3. Visit [localhost: 5000](http://localhost:5000/) in your browser and enjoy!

## Machine Learning Pipline
1. **Data Collection** 
   
   Data was collected from [Kaggle](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset)
   
2. **Model Selection** 

   The **Random Forest Classifier** was selected for this problem due to its reputation for achieving high accuracy in classification tasks. 
   It is a popular choice in the healthcare and medical industry, where precise and reliable predictions are crucial.
   
3. **Exploratory Data Analysis (EDA)** 

   The below snippets are some interesting observations we discovered: 
   - **Data Distribution with Histogram Analysis**
   
     ![image](https://github.com/yeyanwang/stroke_classifier/assets/120543690/efacd65c-d4c2-4060-a508-e7ef2be771f8)
     
   - **Closer Examination on Target Variable** 
   
     ![image](https://github.com/yeyanwang/stroke_classifier/assets/120543690/7ed0adda-b624-4699-8546-021602894d69)
     
   - **Missing Values on 'bmi' column**
   
     ![image](https://github.com/yeyanwang/stroke_classifier/assets/120543690/6e6ad77a-8086-4b70-8910-a92c0a0cfef7)
     
     **Filled in Missing Values with Imputed values**
     
     ![image](https://github.com/yeyanwang/stroke_classifier/assets/120543690/65da8d6e-f563-4fcb-a8f9-7763ea5aa9fc)
     
   - **Singleton Record on 'gender' column**
   
     ![image](https://github.com/yeyanwang/stroke_classifier/assets/120543690/8ed61800-b292-4080-b882-2d37240c243f)
     
     **Dropped Singleton Record**
     
     ![image](https://github.com/yeyanwang/stroke_classifier/assets/120543690/51b3de32-cf32-4cb5-8519-cd5c8c2c82fc)
     
   - **Uneven Distribution 'bmi' values**
    
     ![image](https://github.com/yeyanwang/stroke_classifier/assets/120543690/dda914f3-391f-4bcf-92c8-1c239ee1e157)
     
     **Binning 'bmi' values** ([Model 3](https://github.com/yeyanwang/stroke_classifier/blob/main/stroke_classifier_optimization_1.ipynb) only)
     ![image](https://github.com/yeyanwang/stroke_classifier/assets/120543690/742d74c4-c14c-4a72-a78b-a154d0092eeb)
     
     ![image](https://github.com/yeyanwang/stroke_classifier/assets/120543690/cca8c744-b3fc-4fe6-98ae-20da5b87f464)
     
4. **Data Preprocessing** 

   Data was cleaned and prepared for further analysis. This includes: 
   - Applied oversampling methods to handle imbalanced data
   - Apllied encoding to categorical varibales
   - Applied feature scaling to transform numerical features into a consistent range
   - Divided data into training and testing sets using `train_test_split` module
5. **Modeling Training**

   Trained 3 models using different resampling methods  
   - **Model 1** used oversampled data with the `RandomOverSampler` technique
   - **Model 2** used oversampled data with the `SMOTE` technique
   - **Model 3** used oversampled data with `RandomOverSampler` and applied additional binning to the 'bmi' column

6. **Evaluation**
   - Utilized accuracy scores, confusion matrix and classification reports to compare to access the performance of all 3 models
   - We ultimately selected **model 1** as the final model due to its overall superior performance. 
   
   Despite having a false positive rate of 1.82%, it is more advantageous in the context of predicting stroke occurrence to falsely identify patients as likely to have a stroke. This allows clinicians to allocate more attention and care to these patients. Conversely, a high false negative rate would be concerning, where patients who have a risk of stroke will not be intervened. In other words, it is preferable to mistakenly identify patients who are likely to have a stroke, rather than missing such cases. 
   
   See more detail about our [final model](https://github.com/yeyanwang/stroke_classifier/blob/main/stroke_classifier_final%20.ipynb)
7. **Model Deployment with Flask**
   - Implemented the model logic in our home route to handle incoming requests
   - Created Web-based UI with HTML and CSS
   
   Check out the snippets below:
   - **Landing Page:**
   
   ![Landing Page](https://github.com/yeyanwang/stroke_classifier/assets/120543690/93037122-c541-4cb0-9307-6937aa6f0252)
   
   - **Result Page**
   
   ![Result Page](https://github.com/yeyanwang/stroke_classifier/assets/120543690/1bd99269-90c2-49fe-b023-9f398b486b18)

## Credits 
- [Kevin Lee](https://github.com/kevinclee26)
- [Kaggle](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset?select=healthcare-dataset-stroke-data.csv)
- UC Berkely Extension Data Analytics Bootcamp
