# README: Pneumonia Detection System

## Overview
This notebook implements a Streamlit web application for detecting pneumonia from chest X-ray images. It leverages a deep learning model (Convolutional Neural Network) to classify X-ray images as 'Normal' or 'Pneumonia Detected'. The application provides a user-friendly interface for uploading images and viewing prediction results.

## Features
-   **AI Powered Analysis**: Utilizes a pre-trained CNN model for image classification.
-   **Fast Prediction**: Provides quick results after image upload.
-   **Medical Imaging**: Specifically designed for chest X-ray analysis.
-   **User Interface**: Interactive UI built with Streamlit for easy interaction.
-   **Public Access (Optional)**: Includes steps to expose the Streamlit app publicly using Cloudflare Tunnel.

## Setup and Dependencies
To run this notebook and the Streamlit application, ensure you have the following installed:
-   `streamlit`
-   `tensorflow`
-   `keras`
-   `Pillow` (PIL)
-   `numpy`
-   `cloudflared` (for public access)

You will also need a pre-trained Keras model file named `pneumonia_model.h5` in the same directory as this notebook.

## How to Run
1.  **Define `app.py`**: Run the cell that contains `%%writefile app.py` to create the Streamlit application file.
2.  **Start Streamlit**: Execute the command `!streamlit run app.py &` in a code cell to start the Streamlit server in the background on port `8501`.
3.  **Optional: Public Access with Cloudflare Tunnel**:
    -   Run the cells to download and install `cloudflared`.
    -   Execute the cell with `!cloudflared tunnel --url http://localhost:8501` to create a public URL for your Streamlit app. The URL will be displayed in the output.

## Usage
Once the Streamlit app is running (locally or via Cloudflare Tunnel):
1.  Navigate to the provided URL.
2.  Upload a Chest X-ray image (JPG, JPEG, or PNG format).
3.  Click the 'Predict' button.
4.  The system will display whether 'PNEUMONIA DETECTED' or 'NORMAL' along with a confidence score.

## Model Details
-   The core of the detection system is a Convolutional Neural Network (CNN).
-   The model `pneumonia_model.h5` is loaded using `tensorflow.keras.models.load_model`.
-   Input images are resized to 128x128 pixels and preprocessed before feeding into the model.

## Disclaimer
This project is developed for educational and demonstrative purposes only and should **not** be used for actual medical diagnosis. Always consult with a qualified medical professional for any health concerns.

## Resources
- [Kaggle Dataset: Chest X-Ray Images (Pneumonia)](https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia)
- [Streamlit Documentation](https://streamlit.io/docs/)
- [TensorFlow Keras Documentation](https://www.tensorflow.org/api_docs/python/tf/keras)
- [Cloudflare Tunnel Documentation](https://developers.cloudflare.com/cloudflare-one/connections/connect-apps/)
