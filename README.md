# AI---ML-based-Healthcare-System-Healify-
This project aims to develop a comprehensive healthcare system to aid healthcare professionals. While also providing knowledge to patients. It uses a LLM and traditional Machine Learning (ML) to provide in-depth answers to medical health condition queries and can predict diseases based on patient symptoms.
The system consists of two main Modules:

Disease Prediction Model
HealifyLLM - Q&A Language Model
# Data Collection, Cleaning, Preprocessing
Healify-LLM model:
Engineered brand new LLM Corpus Dataset of size 6800 samples from scratch. Started with scraping based on [healthline.com](https://www.healthline.com/directory/topics)
To enhance the corpus for user experience, Sample addition was done with my python script. Enabling it to provide detailed and accurate answers to a wide range of user questioning styles.
Disease Model:
The model was trained on a kaggle dataset from Disease-Symptom Knowledge Database, a database with over hundreds of patient records at the New York Presbyterian Hospital, USA.
Covering 135 Categories of important common but also rare diseases/health conditions.
From a total of 400 Symptoms.

Disease dataset was processed to clean the noisy symptoms, UMLScode etc.
LLM dataset processing required data seperation, sample addition.
The scraping can be found in scraper folder.
All final datasets stored in datasets folder.
All cleaning and processing found in notebooks folder.

# Model Training:
Healify-LLM model:
Hyperparameters: We used a batch size of 8. And learning rate was set dynamically using Fast.ai's learning rate finder at every stage for Fine-Tuning.

Training Procedures: We used HuggingFace for the model and imported Fast.ai for hyperparameter tuing

RoBERTa model has been used because the QA dataset is complex.
Training was done using ULMFiT Research Paper's 3-stage training policy.
The model was fine-tuned with 6800 samples around 98% accuracy in 12 epochs. The model was tracked to avoid overfitting observing loss. The model was trained using NVIDIA T4 GPU. With good sample ratio, as total 6800 samples for just 135 diseases.
Disease Model:
Model was trained with sklearn's ensemble random forest algorithm leveraging mutiple decision tree algorithms. This model predicts potential diseases based on the symptoms input.

# Model Deployment
A Gradio App was coded to deploy the LLM model in HuggingFace. This live huggingfaces API is later integrated in the Back-End. The Gradio implementation can be found in deployment_hf folder and online here

# Live Website Deployment
Deployed a Flask App, built to provide user interface to users. Check the flask-deployment github branch. The website is live here
