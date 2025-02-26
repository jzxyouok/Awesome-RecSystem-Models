# Implements of Awesome RecSystem Models with PyTorch


### 1. Relative DataSet
- ##### Criteo
    - This dataset Contains about 45 million records. There are 13 features taking integer values (mostly count features)
    and 26 categorical features.
    - The columns are tab separated with the following sechema: <label><int feat 1>...<int feat 13><cate feat 1>...<cate feat26>
    - The dataset is available at http://labs.criteo.com/2014/02/download-kaggle-display-advertising-challenge-dataset/
    - Put the downloaded 'train.txt' file in 'data/Criteo/' folder.
- ##### Movielens100K
    - MovieLens 100K movie ratings. Stable benchmark dataset for Recommendation System. 
    - This dataset contain 100,000 ratings from 1000 users on 1700 movies.
    - The details can be found at https://grouplens.org/datasets/movielens/100k/
    - This dataset have been downloaded and is available at 'data/Movielens100K' 
### 2. Implemented Models:
- ##### FM: Factorization Machine
    - The paper is available at: https://www.csie.ntu.edu.tw/~b97053/paper/Rendle2010FM.pdf
    - Tested dataset: Criteo
    - Split the data set by 9:1 for train and test.
    - How To Run:
    Run data/forOtherModels/dataProcess.py to pre-porcess the data, then run Model/FM_PyTorch.py
    - the result is AUC: 0.7805 
    - For Multi-Classification implements: 
        - Tested dataset: Movielens100K
        - Run FM_Multi_PyTorch.py
- ##### FFM: Field-aware Factorization Machine
    - The paper is available at: https://www.csie.ntu.edu.tw/~cjlin/papers/ffm.pdf
    - Tested dataset: Movielens100K
    - Support Multi-Classification
- ##### DeepFM: Factorization-Machine based Neural Network
    - The paper is available at: https://www.ijcai.org/proceedings/2017/0239.pdf
    - Tested dataset: Criteo
    - Split the data set by 9:1 for train and test.
    - How To Run:
    Run data/forOtherModels/dataProcess.py to pre-porcess the data, then run Model/DeepFM_PyTorch.py
    - After 3 Epoch, AUC: 0.795(The paper result is 0.801)
- ##### DCN: Deep&Cross Network
    - The paper is available at: https://arxiv.org/pdf/1708.05123.pdf
    - Tested dataset: Criteo
    - Run data/forDCN/DCN_dataProcess.py to pre-process the data. According to the paper, the dataset is split by 9:0.5:0.5 for train, test and valid
    - Split the data set by 9:0.5:0.5 for train, test and valid
    - Run Model/DeepCrossNetwork_PyTorch.py, and the results are as follows:
    
        |Epochs|AUC|LogLoss|
        |-----|---|-------|
        |1st|0.80157|0.45192|
        |2nd|0.80430|0.44922|
        |3rd|0.80546|0.44817|
        |4th|0.80639|0.44729|
        |5th|0.80696|0.44678|
- ##### xDeepFM: eXtreme Deep Factorization Machine
    - The Paper is available at: https://arxiv.org/pdf/1803.05170.pdf
    - Tested dataset: Criteo
    - Split the data set by 9:1 for train and test.
    - Run data/forXDeepFM/xDeepFM_dataProcess.py to pre-process the data. The pre-process of xDeepFM is identical with
     that of DeepFM.
    - Run Model/xDeepFM_PyTorch.py.
    - After 5 epochs, the result is AUC 0.80148, LogLoss 0.45104 (The paper result is AUC 0.8052).
- ##### PNN: Product-based Neural Network
    - Paper: https://arxiv.org/pdf/1611.00144.pdf
    - Tested dataset: Criteo
    - Split the data set by 9:1 for train and test.
    - How To Run:
    Run data/forOtherModels/dataProcess.py to pre-porcess the data, then run Model/ProductNeuralNetwork_PyTorch.py
    - After 3 epochs, the result of IPNN is AUC: 0.76585, LogLoss: 0.47766
    - After 3 epochs, the result of OPNN is AUC: 0.76592, LogLoss: 0.47748
    
