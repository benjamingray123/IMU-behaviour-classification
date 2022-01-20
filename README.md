# IMU-behaviour-classification
classification of dog behaviour based on inertial measurements (accelerometer and gyroscope) recorded by a wearable sensor 


- executive summary
    - fill this in! 
    - what is the 'business impact' of the analysis and model?
    - relevant to chordata! baseline figures for activity recognition based on inertial measurements. 
    - relatively straightforward algorithms are a smaller computational load which would be critical for in-situ behavioural classification in a low-powered wearable 

feature extraction, engineering, encoding, scaling
explore the data with summary stats and plots
build classification model with 3 classes: lying, sitting, moving 
assess model performance, justify algorithm choice, suggest improvements and future perspectives 

- repo overview 
    - 1.preprocessing.ipynb - 
    - 2.transformation.ipynb - 
    - 2.1.transformation.ipynb - 
    - 3.features&models.ipynb - 
    - 3.1.features&models.ipynb - 

- model selection and performance 
    - monitored confusion matrices, accuracy scores and f1 scores
    - f1 score is a robust summary metric, suitable for where there exists as class imbalance  

- optimisation and future perspectives 
    - performance of model largely dictated by the features fed into it
    - high quality features, i.e MCR etc    
    - signal filtering prior to feature extraction i.e butterworth or low-pass filter 
    - class imbalance in data - many more examples of dynamic behaviours. potential solutions could be oversampling the static behaviours, or undersampling dynamic behaviours. 
    - hyperparameter tuning: in the models, also the sliding window parameters 
    - feature engineering and extraction not required for neural networks?
    - refactor code into sklearn pipelines to ensure no data leakage occurs 

