# enas_nni
## Description
>>ENAS is a algorithm for neural network search. It could learn neural network architecture via reinforcement learning. And it is much faster than NAS, designed by google.  
>>nni is an open source AutoML toolkit for neural architecture search and hyper-parameter tuning.  
>>This code is for running ENAS on nni.   


# nni: An open source AutoML toolkit for neural architecture search and hyper-parameter tuning. 
>link:  https://github.com/Microsoft/nni  

# ENAS: Efficient Neural Architecture Search via Parameter Sharing
>link:  https://github.com/melodyguan/enas   
>Paper: https://arxiv.org/abs/1802.03268  

# How to run

## 1. Install dependency  
>>Need to install nni first.  
>>link:https://github.com/Microsoft/nni You need to choose the dev-enas branch.  
>>run command:   
>>`python3 -m pip install --user --upgrade nni`  
>>`source ~/.bashrc`  

## 2. Modify the codedir
>>  Rnn architecture search(ptb_search):
>>>    Modify the codeDir at enas_nni/nni/examples/trials/enas/ptb_config.yml.   
      
>>  Cnn architecture search(cifar10_search):
>>>   macro search:  Modify the codeDir at  enas_nni/nni/examples/trials/enas/cifar10_macro_config.yml.        
>>>   micro search:   Modify the codeDir at enas_nni/nni/examples/trials/enas/cifar10_micro_config.yml.    
        
## 3. Download the dataset
  
>> rnn architecture search(ptb_search):    the dataset are at enas_nni/nni/examples/trials/enas/data/ptb
    
>>  cnn architecture search:  You need to download the cifar10 data at https://www.cs.toronto.edu/~kriz/cifar.html (python version).   
And put data at  enas_nni/nni/examples/trials/enas/data and rename the cifar-10-batches-py as cifar10 .   
Or you could just run the script/download.sh at script folder.

## 4. Start run
`cd ./enas_nni/nni/examples/trials/enas`
>>ptb_search:
`
>>    nnictl create --config ptb_config.yml  
`

>>micro_search:
`
>>    nnictl create --config cifar10_micro_config.yml  
`
  
>>macro_search:
`
>>    nnictl create --config cifar10_macro_config.yml  
`

# Future work
>>We have one controller running on nni tuner and we could run multiple trials to update the controller. But we do not share the weight of each trial. Next step we will support that. 

