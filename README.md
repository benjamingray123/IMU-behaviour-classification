# IMU-behaviour-classification
classification of dog behaviour based on inertial (acc, gyro) measurements from a wearable




feature extraction, engineering, encoding, scaling
explore the data with summary stats and plots
build classification model with 3 classes: lying, sitting, moving 
assess model performance, justify algorithm choice, suggest improvements and future perspectives 

- executive summary 
    - 1.preprocessing.ipynb - 
    - 2.transformation.ipynb - 
    - 3.features&models.ipynb - 

- assess model performance & justify choice of algorithm 

- improvements and future perspectives 
    - performance of model largely dictated by the features fed into it
        - high quality features, i.e MCR etc    
    - signal filtering prior to feature extraction i.e butterworth or low-pass filter 
    - class imbalance in data - many more examples of dynamic behaviours. potential solutions could be oversampling the static behaviours, or undersampling dynamic behaviours. 
    - hyperparameter tuning: in the models, also the sliding window parameters 




feature engineering and extraction not required for neural networks?

