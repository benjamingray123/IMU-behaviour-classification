# IMU-behaviour-classification
*classification of dog behaviour based on inertial measurements (accelerometer and gyroscope) recorded by a wearable sensor*

*data available at data.mendeley.com/datasets/vxhx934tbn/2*

- executive summary
    - a decision tree classified an unseen subject (LOGOCV) with average 0.95 accuracy based on generic (selected) default features from tsfel
    - support vector classifier was comparatively slow and therefore might not be suitable for applications in low powered wearable devices
    - the use of custom features per Kumpulainen et al., (2021) did not significantly increase model performance over the default features extracted by tsfel. (NOTE - using the same n_features parameter) 
    - as observed by Kumpulainen et al. (2021), static behaviours were less accurately classified than dynamic behaviours. this was compounded by the class imbalance where samples of dynamic and static behaviours were not present in equal proportions. 
    - this work represents an initial benchmark pipeline for activity recognition in animals

- repo overview 
    - 1.0preprocessing.ipynb - aggregates 7+ behaviour labels into 3 summary labels. drops unnecessary features and rows to reduce computational load
    - 2.0transformation.ipynb - extraction of features specified by Kumpulainen et al., (2021)
    - 2.1.transformation.ipynb - extraction of all (~60) default features offered by tsfel 
    - 3.0features&models.ipynb - feature engineering & selection. EDA & visualisations. model building and evaluation with features from Kumpulainen et al., (2021)
    - 3.1.features&models.ipynb - feature engineering & selection. EDA & visualisations. model building and evaluation with all features from tsfel
    - DogMoveFeatures.json - feature config file for tsfel. selects rolling mean, ECDF percentiles, standard deviation & zero crossing rate 
    - DogBehaviorFeatures.json - feature config file for tsfel. selects only rolling mean 

- model selection and performance 
    - gaussian naive bayes, k-nearest neighbours, support vector classifier and decision tree classifiers were tested. performance was evaluated under random train_test_split and leave-one-group-out cross validation (LOGOCV) conditions. these algorithms were selected because they are straightforward to implement and pose a comparatively small computational burden. this would be critical for in-situ behavioural classificationon aboard a low powered wearable device. 
    - accuracy scores across all 4 models were very similar between feature sets (using identical n_features <= ~ 20)
    - using default features from tsfel is easier so LOGOCV evaluation was focused on in 3.1.features&models.ipynb 
    - average accuracy was consistenly lower when under LOGOCV conditions. Likely because variation between test and train group sizes is greater with LOGOCV than train_test_split
    - class imbalance influenced the confusion matrices as there were more dynamic behaviour samples 
    - confusion matrices were monitored, in addition to accuracy and f1 scores
    - f1 score is a robust summary metric, suitable for where class imbalances are present 

- optimisation and future perspectives   
    - trial signal filtering prior to feature extraction i.e butterworth or low-pass filter 
    - mitigating the class imbalance - oversampling the static behaviours, or undersampling dynamic behaviours
    - hyperparameter tuning for models, sliding window, featues, feature selection. automated with grid / random search 
    - refactor code into sklearn pipelines to prevent data leakage and increase usability 

