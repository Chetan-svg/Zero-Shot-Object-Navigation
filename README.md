# Zero-Shot Object Goal Visual Navigation

Qianfan Zhao, Lu Zhang, Bin He, Hong Qiao, and Zhiyong Liu

This implementation is modeified based on [MJOLNOR](https://github.com/cassieqiuyd/MJOLNIR) and [SAVN](https://github.com/allenai/savn).

## Setup

1. (Recommended) Create a virtual environment using virtualenv or conda:
```
virtualenv ZSON --python=python3.6
source ZSON/bin/activate
``` 
```
conda create -n ZSON python=3.6
conda activate ZSON
```

2. For the rest of dependencies, please run `pip install -r requirements.txt --ignore-installed`
3. Clone the repository as:
```
    git clone https://github.com/cassieqiuyd/MJOLNIR.git
```

## Data

The offline data can be found [here](https://drive.google.com/drive/folders/1i6V_t6TqaTpUdUFpOJT3y3KraJjak-sa?usp=sharing).

"data.zip" (~5 GB) contains everything needed for evalution. Please unzip it and put it into the MJOLNIR folder.

For training, please also download "train.zip" (~9 GB), and put all "Floorplan" folders into `MJOLNIR/data/thor_v1_offline_data`

## Evaluation

Note: if you are not using gpu, you can remove the argument `--gpu-ids 0`

### Evaluate our model under 18/4 class split

```bash
python main.py --eval \
    --test_or_val test \
    --episode_type TestValEpisode \
    --load_model pretrained_models/SelfAttention_test.dat \
    --model SelfAttention_test \
    --gpu-ids 0 \
    --zsd 1 \
    --split 18/4
```

### Evaluate our model under 14/8 class split

```bash
python main.py --eval \
    --test_or_val test \
    --episode_type TestValEpisode \
    --load_model pretrained_models/SelfAttention_test.dat \
    --model SelfAttention_test \
    --gpu-ids 0 \
    --zsd 1 \
    --split 14/8
```
