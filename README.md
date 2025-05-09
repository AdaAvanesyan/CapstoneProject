# CapstoneProject

A complete voice-based system that detects human emotions from speech and generates empathetic replies using OpenAI's GPT-3.5-turbo. It combines classical machine learning (XGBoost), deep learning (CNN), and a natural language chatbot into a user-friendly Streamlit interface.

## Running the Final&Complete Capstone Codes.ipnyb
- Install all the required packages
- First just download the zip.folders of 2 datasets crema.zip, Ravdess.zip
- Adjust the path and just run the cells in order it is provided.

---

## Features

- Upload `.wav` files and detect emotions
- Choose between **XGBoost** (flattened MFCC) and **CNN** (2D MFCC) models
- Generate empathetic responses using **GPT-3.5-turbo**
- Maintain chat memory and emotion context
- Deploy using **Streamlit**

---

## 📁 Project Structure

```
emotion-aware-chatbot/
├── data_preprocessing/             # Clean and label data
├── xgboost_pipeline/
│   ├── feature_extraction_xgb.ipynb
│   ├── train_xgb_model.ipynb
│   ├── evaluate_xgb_model.ipynb
├── cnn_pipeline/
│   ├── feature_extraction_cnn.ipynb
│   ├── train_cnn_model.ipynb
│   ├── evaluate_cnn_model.ipynb
├── predict_and_chatbot.ipynb     # Upload audio + predict + GPT reply
├── app.py                          # Streamlit interface
├── requirements.txt
├── README.md
```
## Running the Final&Complete Capstone Codes.ipnyb
- Install all the required packages
- First just download the zip.folders of 2 datasets crema.zip, Ravdess.zip
- Adjust the path and just run the cells in order it is provided.
  
## Running the seperated ipnyb files provided with XGBoost and CNN zipped folders

##  Run data_preprocessing.ipynb
- Mount Google Drive
- Extract both datasets
- Label and clean files
- Output:
- /content/drive/MyDrive/capstone_data/combined_clean_metadata.csv

## Run feature_extraction_xgb.ipynb for XGBoost
- Output:
- x_xgb_features.npy
- y_xgb_labels.npy
- label_encoder.pkl
- 
## Run feature_extraction_cnn.ipynb for CNN
- Output:
- x_cnn_features.npy
- y_cnn_labels.npy
- label_encoder.pkl

## Run train_xgboost.ipynb for XGBoost
- Output:
- xgb_model.joblib

## Run train_cnn.ipynb for CNN
- Output:
- cnn_model.h5

## Run evaluate_xgb_model.ipynb
- Loads xgb_model.joblib
- Prints classification report and confusion matrix

## Run evaluate_cnn_model.ipynb
- Loads cnn_model.h5
- Prints classification report and confusion matrix
## Chatbot UI 
- install required packages
```
pip install openai==0.28
pip install streamlit streamlit-webrtc librosa scikit-learn xgboost speechrecognition pyngrok
from pyngrok import ngrok

# Replace with ngrok token
ngrok.set_auth_token("key")

! pip install streamlit -q
!wget -q -O - ipv4.icanhazip.com
! streamlit run app.py & npx localtunnel --port 8501
```
- Create the app.py in your google colab environment (there are used private api keys for ngrok and openai usage)
- Using the tunnel numbers provided by Streamlit go to the given UI
