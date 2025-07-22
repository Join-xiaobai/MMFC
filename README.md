## MMFC Project Description



## Overview 

The aim of this project is to predict drug-target interactions (DTI) through graph neural network (GNN) modeling. A heterogeneous graph data structure is used to represent the relationship between drugs and proteins, and feature learning is performed through multilayer perceptron (MLP), attention mechanisms, and graph convolution operations such as SAGEConv and GATConv. The code mainly consists of three parts, `crossTest.py`, `MMFC.py`, and `test.py`, which are used for the computation of cross-validation performance metrics, model training and testing, respectively.



## File structure

\- `crossTest.py`: Contains functions for calculating the average performance metrics and its standard deviation for 5-fold cross validation.

\- `MMFC.py`: The main script file containing the model definition, data loading, preprocessing and training process.

\- `test.py`: contains the code for testing the model performance.



## How to run



### Data preparation 

Ensure that there is a file in the `. /data/` directory:

\- `drug_feature.csv`

\- `protein_feature.csv`

\- `drug_protein.csv`



These files contain drug node features, protein node features, and drug-protein association information, respectively.



### Run the training script 

Execute the following commands to start training the model: 

\```bash 

python MMFC.py 

\``` 

The training process outputs the loss values and performance metrics such as validation set AUC and test set AUC for each round, and saves the best model to the specified path.



### Test Model 

You can use the `test.py` script to evaluate the performance of the trained model. Please modify the model path in the script to point to the location of your best model, and then execute: 

\```bash 

python test.py 

\```



## Notes

1. Make sure you have all necessary Python libraries installed, such as `pandas`, `torch`, `torch_geometric` etc.
2. adjust hyperparameters such as `batch_size`, `num_neighbors`, etc. for different environment configurations according to hardware conditions.
3. log files will be created and saved in `. /outputs/log.txt` to record the information of each training.



## Result Output 

After the training is finished, you can view the detailed information of the training process in the log file, including but not limited to the loss value, validation set AUC, test set AUC, etc. for each round. Meanwhile, the final best model will be saved in `. /bestModel/best_model.pt` path. 



## COVID-19 related research 

In particular, the framework of this project can also be applied to COVID-19 related research, which can be used to explore the discovery of anti-COVID-19 drugs by replacing the dataset with data containing SARS-CoV-2 viral targets and potential drugs. Adapting the input features and association relationships to fit the new dataset is a critical step.
