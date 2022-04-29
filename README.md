# Next Speaker Prediction Via Neural Message Passing

This is the official repository for *Next Speaker Prediction Via Neural Message Passing* 

# Overview


For the purposes of this repository, we assume that the dataset is downloaded to `../SpeedDating/`

This repo is divided into the following sections:


* [Set up environment](#set-up-environment)
* [Training](#training)


## Set up Environment

```sh
pip install -r requirements.txt
```

## Training
To train a model from scratch, run the following script. Currently, 3 and 4 person settings are supported: 

### Next Speaker Prediction

```sh
#Ours
python train.py --task next_speaker --model_name Graph --group_num 3 --time_step 1 --role 1 --epochs 250 --init_seed 0 --cv_seed 0 

#Ours w/o Role Encoder 
python train.py --task next_speaker --model_name Graph --group_num 3 --time_step 1 --role 0 --epochs 250 --init_seed 0 --cv_seed 0 

#XGBoost
python train_xgboost.py --task next_speaker --group_num 3

```

### Next Speaker Identification

```sh
#Ours
python train.py --task identify_speaker --model_name Graph --group_num 3 --time_step 0 --role 1 --epochs 200 --init_seed 0 --cv_seed 0

#Ours w/o Role Encoder 
python train.py --task identify_speaker --model_name Graph --group_num 3 --time_step 0 --role 0 --epochs 200 --init_seed 0 --cv_seed 0 

#XGBoost
python train_xgboost.py --task identify_speaker --group_num 3
```
