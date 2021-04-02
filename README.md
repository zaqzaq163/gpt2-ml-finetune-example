# **GPT2-ML finetune-example**

#### Requirements
1. python(3.6 - 3.8)
2. tensorflow-gpu==1.15.4
3. cuda 10.0 and cudnn 7.4

#### Finetune
``` shell script
#请自行下载预训练模型,DEMO中使用的模型为( ~30G corpus, 22w steps )
cd dataset
python3 prepare_data.py -input_fn ../data
cd ../train
python3 train_tpu.py --input_file=../dataset/train.tfrecord --output_dir=../finetune_model --init_checkpoint=../models/mega/model.ckpt-220000 --config_file=../configs/mega.json --train_batch_size=1 --num_train_steps=230000
#请将train.tfrecord重命名为生成文件实际名称
```

#### Reference

https://github.com/imcaspar/gpt2-ml \
https://github.com/wind91725/gpt2-ml-finetune-