# BERT BoolQ

This repo contains code to train and evaluate the main results from the BoolQ
paper (https://arxiv.org/abs/1905.10044).

This repo is used a BERT implementation for the BoolQ task described in
https://github.com/google-research/language/tree/master/language/boolq.

## Installation

1. Use `requirements.txt` file in order to install all necessary libriaries.
2. Get the original BERT vocabulary file `vocab.txt` and paste it in the
`vocab/` folder (https://huggingface.co/bert-base-uncased/tree/main).
3. Get the original BERT configuration file `config.json` and paste it in the
`config/` folder (https://huggingface.co/bert-base-uncased/tree/main).

## Running

Use this command to run BERT algorithm training and evaluating processes
for the BoolQ task:
```
python -m run_boolq_bert \
--vocab_file vocab/vocab.txt \
--bert_config_file config/bert_config.json \
--init_checkpoint bert_model.ckpt \
--boolq_train_data_path /data/train.jsonl \
--boolq_dev_data_path /data/dev.jsonl \
--do_train --do_eval_dev --output_dir /output
```

If you run the algorthm first, you won't require to configure 
`--init_checkpoint` flag. The algorithm will create the checkpoint file
automatically.
