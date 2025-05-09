# CapstoneProject

A complete voice-based system that detects human emotions from speech and generates empathetic replies using OpenAI's GPT-3.5-turbo. It combines classical machine learning (XGBoost), deep learning (CNN), and a natural language chatbot into a user-friendly Streamlit interface.

---

## Features

- Upload `.wav` files and detect emotions
- Choose between **XGBoost** (flattened MFCC) and **CNN** (2D MFCC) models
- Generate empathetic responses using **GPT-3.5-turbo**
- Maintain chat memory and emotion context
- Deploy using **Streamlit**

---

## Project Structure

emotion-aware-chatbot/
├── data_preprocessing/ # Clean and label data
├── xgboost_pipeline/
│ ├── 2_feature_extraction_xgb.ipynb
│ ├── 4_train_xgb_model.ipynb
│ ├── 6_evaluate_xgb_model.ipynb
├── cnn_pipeline/
│ ├── 3_feature_extraction_cnn.ipynb
│ ├── 5_train_cnn_model.ipynb
│ ├── 6_evaluate_cnn_model.ipynb
├── 7_predict_and_chatbot.ipynb # Upload audio + predict + GPT reply
├── app.py # Streamlit interface
├── requirements.txt
├── README.md
