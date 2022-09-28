# tgcn-soil-moisture
Code for our AAAI 2023 paper:



#### 01_Gen_Clustering_Data
run `Data_input_hru.ipynb` and store numpy arrays of numeric hru features at location `data_path`
Reads: Region 02 data read from .hru output files and saved into numpy arrays. 
Parameters: `Clustering_feature_names` : Change the features used for clustering. 
Saves: monthly average over 38 years of the simulation (months, hrus, features) for each HRU. The output file is subbasin level 'subbasinid.num_hrus'

#### 02_Elbow_test
run `01_Gen_Clustering_Data` and have numpy arrays of hru clustering features data stored at location `data_path` 
Parameters: 
- `iterations` : number of subsampling iterations
- `sampled hrus` : number of hrus to subsample from total ~9k hrus
Output: Number of clusters $k$ for the kmeans clustering


#### 03_Clustering
Prerequisites:
- Run `01_Gen_Clustering_Data` and have numpy arrays of hru clustering features data stored at location `data_path`
- Run `02_Elbow_test` to identify the number of clusters

Parameters: 
- `normalization` : number of hrus to subsample from total ~9k hrus
- `max_iter` : number of max iterations for convergence of the clustering algorithm
Output:  saves hrus and t

#### 04_Gen_SMest_Data: 
Generates data for SM estimation code

#### 05_SingleStep_TGCN

#### 07_MultiStep_TCN

##### p.s. 
/path/ : refers to local path of data - replace with your local path
