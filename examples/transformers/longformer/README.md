# Longformer Example
In this directory we provide implementations for Longformer model on Hetu.

## Dataset Preparing
We support Shakespeare and OpenWebText dataset for Longformer training, and support GLUE dataset for finetuning, including 
sst-2, cola, mrpc.

Shakespeare is a small dataset on which you can conduct simple model training. You may have to run the following scripts to prepare Shakespeare dataset.
```bash
python prepare.py
```

We also provide OpenWebText dataset for language model training. You can set the dataset to openwebtext in the command line and adjust the number of processes for data preparation.
```bash
python prepare.py --dataset openwebtext --num_proc 4
```

In order to finetune Longformer model by GLUE dataset, you may have to run the following scripts. 
```bash
python prepare_glue.py
```

Note: You can also use your own dataset, but you need to tokenize them firstly.

## Training Longformer model
All scripts for training Longformer model are in `./scripts` directory. Users are free to modify hyperparameters in shell file.

To train Hetu Longformer model, run:
```bash
sh ./scripts/train_hetu.sh     (1 GPU)
sh ./scripts/train_hetu_dp.sh  (4 GPUs)
```
To finetune Hetu Longformer model, run:
```bash
sh ./scripts/finetune_hetu.sh     (1 GPU)
```
