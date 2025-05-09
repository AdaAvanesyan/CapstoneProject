# CapstoneProject

A complete voice-based system that detects human emotions from speech and generates empathetic replies using OpenAI's GPT-3.5-turbo. It combines classical machine learning (XGBoost), deep learning (CNN), and a natural language chatbot into a user-friendly Streamlit interface.

##  Setup and Install Dependencies

- Mount your Google Drive
- Install all required packages (Librosa, XGBoost, TensorFlow, OpenAI API, etc.)
- All files and outputs will be saved to your `/content/drive/MyDrive/capstone_data/` directory.

---

##  Upload & Extract the Datasets

- Upload two ZIP files to your Google Drive:
  - `archive.zip` → contains the RAVDESS dataset
  - `crema.zip` → contains the CREMA-D dataset
- Extract the audio files from these ZIPs into Colab (`/content/dataset/`)

---

##  Label and Clean the Metadata

- Read all `.wav` files from the RAVDESS and CREMA-D directories
- Parse the filenames to extract emotion labels (e.g., happy, sad, angry, neutral)
- Filter to only those 4 emotions
- Remove any invalid or unreadable files
- Save the cleaned metadata as `combined_clean_metadata.csv`

---

##  Extract Audio Features

- **XGBoost**: Extract 40 MFCCs, flatten them to 1D (size: 6960)
- **CNN**: Extract 2D MFCCs with shape `(40, 174, 1)`
- Encode emotion labels using `LabelEncoder`
- Save:
  - `x_xgb_features.npy`, `x_cnn_features.npy`
  - `y_encoded.npy`
  - `label_encoder.pkl`

---

##  Train Models

- **XGBoost**:
  - Use fixed best parameters: `max_depth=8`, `n_estimators=200`
  - Train on `x_xgb_features` and `y_encoded`
  - Save model as `xgb_model.joblib`

- **CNN**:
  - Build a Conv2D → MaxPool → Dense network
  - Train on `x_cnn_features` and `y_encoded` (categorical)
  - Save model as `cnn_model.h5`

---

##  Evaluate the Models

- **XGBoost**:
  - Load `xgb_model.joblib`
  - Generate classification report and confusion matrix

- **CNN**:
  - Load `cnn_model.h5`
  - Evaluate accuracy and generate confusion matrix

---

##  Upload & Predict New Audio

- Upload a `.wav` file
- Choose a model: XGBoost or CNN
- Predict the emotion of the voice recording
- Decode the label using `label_encoder.pkl`

---

##  GPT-Based Chatbot Response

- Based on the predicted emotion, construct a system prompt for GPT
- Ask the user for a message
- Use OpenAI's `gpt-3.5-turbo` to generate an empathetic reply
- Show the reply directly in the notebook

---
## Streamlit Employment
- Create the app.py in your google colab environment
- Using the tunnel numbers that will apear after running `! pip install streamlit -q
!wget -q -O - ipv4.icanhazip.com
! streamlit run app.py & npx localtunnel --port 8501`
- Swithch to UI web interface
