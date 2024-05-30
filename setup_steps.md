- Install conda, create a python3.8 environment
- use pip to install requirements.txt
- install cuda toolkit version 11.0 from [here](https://developer.nvidia.com/cuda-11.0-download-archive)
- install cuda-toolkit via conda (does this make the previous step obsolete?)
 ```conda install cudatoolkit=11.0```
- Install CUdnn 8.0 from [here](https://developer.nvidia.com/compute/machine-learning/cudnn/secure/8.0.5/11.0_20201106/cudnn-11.0-windows-x64-v8.0.5.39.zip)  and follow [these](https://docs.nvidia.com/deeplearning/cudnn/archives/cudnn-894/install-guide/index.html#install-windows) instructions
  
## Hyperparam tuning:
python hyperparameter_tuning.py ncp_objective ./training_data/ --n_trials 40 --timeout 64800 --batch_size 30 --save_pkl
Note: This had issues, which might not have happened with an even smaller batch size, but this is not certain. 

## Training:
python tf_data_training.py --model ncp --data_dir training_data --epochs 100 --seq_len 64 --data_stride 1 --data_shift 16