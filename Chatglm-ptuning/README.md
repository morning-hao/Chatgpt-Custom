官方说明文档：https://github.com/THUDM/ChatGLM-6B/tree/main/ptuning

注意有一点就是模型的训练模型的路径，因为这个模型比较新，清华官方会更新对应的脚本，最好看huggingface上最新的同步一下，先自己下载下来然后加载，比如

```bash
PRE_SEQ_LEN=8
LR=1e-2

CUDA_VISIBLE_DEVICES=0 python3 main.py \
    --do_train \
    --train_file AdvertiseGen/train.json \
    --validation_file AdvertiseGen/dev.json \
    --prompt_column content \
    --response_column summary \
    --overwrite_cache \
    --model_name_or_path /home/hpn/down_model/chatglm6b_new \  # 这里可以改成自己下载后的路径
    --output_dir output/adgen-chatglm-6b-pt-$PRE_SEQ_LEN-$LR \
    --overwrite_output_dir \
    --max_source_length 64 \
    --max_target_length 64 \
    --per_device_train_batch_size 1 \
    --per_device_eval_batch_size 1 \
    --gradient_accumulation_steps 16 \
    --predict_with_generate \
    --max_steps 3000 \
    --logging_steps 10 \
    --save_steps 1000 \
    --learning_rate $LR \
    --pre_seq_len $PRE_SEQ_LEN \
    --quantization_bit 4

```

