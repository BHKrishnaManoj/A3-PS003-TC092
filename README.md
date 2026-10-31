# AIORI-3-HACKATHON-PROJECTS
This repository will contain the code and resources for the AIORI-3 hackathon that will be developed during the AIORI-3

## Team Introduction Video
Youtube : https://www.youtube.com/watch?v=DMD5YzwQ1qg

## Team Prototype model:
https://colab.research.google.com/drive/15nghNwez58fry1ET-IIaxGQjd8jv6kKU#scrollTo=dZZX6k-jPHaz

  ## Project Workflow

The project implements an **Adaptive Federated Learning-based LSTM model for Traffic Speed Prediction**. It uses historical traffic data to train a global prediction model through multiple simulated clients.

### Workflow

1. **Dataset Collection:** Historical traffic data is collected and loaded into the Google Colab environment.

2. **Data Preprocessing:** The dataset is cleaned, missing values are handled, timestamps are processed, and relevant traffic sensor readings are selected.

3. **Feature Normalization:** Traffic data is normalized using training dataset statistics to ensure consistent input scaling.

4. **Time-Series Sequence Generation:** A sliding-window approach creates input sequences using the previous 12 time steps to predict traffic speed at the next time step.

5. **Client Distribution:** The training dataset is divided into three simulated clients, each representing a separate data source with its own local training and validation data.

6. **Local Model Training:** Each client independently trains an LSTM model using its local traffic data without sharing raw training records.

7. **Adaptive Federated Aggregation:** Local model weights are aggregated into a global model. An adaptive weighting mechanism considers both client data size and local validation loss to determine each client's contribution.

8. **Global Model Updating:** The aggregated weights update the global LSTM model. This process repeats over multiple communication rounds to improve prediction performance.

9. **Model Evaluation:** The trained global model is evaluated using unseen test data. Performance is measured using Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE).

10. **Model Saving and Prediction:** The final trained global model is saved for reuse. New traffic datasets with compatible input features and structure can be preprocessed using the original normalization parameters and passed to the model for traffic-speed prediction.

### Technology Stack

* **Programming Language:** Python
* **Environment:** Google Colab
* **Deep Learning:** TensorFlow / Keras
* **Model Architecture:** Long Short-Term Memory (LSTM)
* **Federated Learning:** Simulated multi-client Federated Averaging with adaptive aggregation
* **Data Processing:** Pandas, NumPy, Scikit-learn
* **Evaluation Metrics:** MAE and RMSE

### Expected Output

The implementation produces:

* A trained global Adaptive FedAvg-LSTM model.
* Local client training and validation results.
* Adaptive aggregation weights for each communication round.
* Global model performance metrics.
* A reusable saved model for prediction on compatible traffic datasets.

The final trained model is attached here in the files.
