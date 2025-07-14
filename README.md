# Online Payments Fraud Detection using IBM Watson

## Overview

This project demonstrates an end-to-end solution for detecting fraudulent online payment transactions using machine learning algorithms and IBM Watson. The web application enables users to input transaction details and receive instant predictions regarding the likelihood of fraud. Built primarily with Python (Flask web framework), the solution leverages a trained classification model to assess transaction risk.

## Project Objective

Online payment fraud is a critical issue for financial institutions and users. This project aims to predict fraudulent transactions based on various input parameters using supervised classification algorithms (Decision Tree, Random Forest, SVM, Extra Trees Classifier). The goal is to separate legitimate transactions from fraudulent ones and provide a user-friendly interface for real-time prediction.

## Features

- **Web-based User Interface**: Simple forms to submit transaction details and view results.
- **Multiple Classification Algorithms**: Trained and tested on various machine learning models for optimal accuracy.
- **Model Integration**: Uses a pre-trained model (payments.pkl) loaded via Flask for prediction.
- **Visualization and User Guidance**: Styled HTML templates for easy navigation and clear display of results.

## Code Structure

```
.
├── app.py                   # Main Flask application
├── payments.pkl             # Pre-trained ML model (pickle format)
├── templates/
│   ├── home.html            # Landing page template
│   ├── predict.html         # Form for user to input transaction data
│   └── submit.html          # Result page with prediction output
└── static/
    └── online_img.jpeg      # Background image used in templates
```

### app.py

- Loads the ML model (`payments.pkl`).
- Defines Flask routes:
  - `/` and `/home`: Landing page
  - `/predict`: Form for new prediction
  - `/pred`: Handles form submission and returns prediction
- Accepts user input, processes it into a feature vector, and uses the loaded model to predict fraud.

### templates/home.html

- Provides project description and navigation options (Home, Predict).

### templates/predict.html

- Form fields for transaction parameters:
  - Step (unit time)
  - Type (transaction type)
  - Amount
  - Old/New Balance (Originator and Destination)
- Submits data to `/pred` for prediction.

### templates/submit.html

- Displays the prediction result and navigation options.

## Setup Instructions

1. **Clone the repository**
   ```bash
   git clone https://github.com/smartinternz02/SPSGP-524569-Online-Payments-Fraud-Detection-using-IBM-watson.git
   cd SPSGP-524569-Online-Payments-Fraud-Detection-using-IBM-watson
   ```

2. **Install dependencies**
   ```bash
   pip install flask numpy pandas
   ```

3. **Ensure payments.pkl is present**
   - The model file (`payments.pkl`) must be available in the project root.

4. **Run the application**
   ```bash
   python app.py
   ```
   - The server will start on port 8000 by default.

5. **Open your browser**
   - Navigate to `http://localhost:8000` to access the app.

## Usage Guide

1. **Home Page**
   - Provides a brief overview and navigation.

2. **Predict Page**
   - Enter transaction details:
     - Time step, transaction type, amount, old/new balance (originator and destination).
   - Click "Predict" to submit.

3. **Result Page**
   - Displays whether the transaction is predicted as fraudulent or not.

## Model Details

- The model is trained using classification algorithms on historical transaction data.
- Input features are derived from transaction parameters entered in the form.
- The model outputs a categorical prediction indicating fraud status.

## Contributing

Feel free to fork and create pull requests for improvements or new features.

## License

This repository does not specify a license. Please contact the owner for usage permissions.

## Acknowledgements

- IBM Watson for ML support
- Scikit-learn for model training
- Flask for backend web development
