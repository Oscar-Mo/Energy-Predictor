# 9417 Group Project
See the [official competition page](https://www.kaggle.com/competitions/ashrae-energy-prediction/overview).
Just to avoid confusion, please note that whilst the kaggle data has a test.csv file, we do not use it for validation as it is not labeled.

## Files
There is a .py and .ipynb version of each file. To run locally, .py is easiest, however .ipynb may be easier if you wish to use Google Colab.
- *generate_training_data.py* will take the kaggle data and apply some modifications before creating a new csv called categorical_train_set.csv to be fed into the next script. It assumes that all csv files from kaggle are in the /data directory.
- *energy_predictor.py* will take categorical_train_set.csv and train a model on the data
- *tuning_and_overfitting.py* runs some additional experiments using hyper parameters


## Instructions for running locally
#### First, ensure the data from kaggle is downloaded into a folder within your working directory called "/data".  It can be downloaded with:

	kaggle competitions download -c ashrae-energy-prediction

#### Then, execute:

	python3 generate_training_data.py
this will generate a new csv file in /data

#### Now we can train a model on the data with:

	python3 energy_predictor.py

#### To run the tuning and overfitting experiment, execute:

	python3 tuning_and_overfitting 1
This will print the accuracy of the hyper param tuning and plot the results.
If you only want to run the training process with a max_leaf value of 3 million, execute:
	
	python3 tuning_and_overfitting 0

	
