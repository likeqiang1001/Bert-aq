# Bert
本项目可以完整运行


按照input文件下的data_下的文件顺序去运行。


模型不想自己训练的可以去release自行下载。


# 跑的过程中发现的问题
1. 项目中指定的是cuda去跑，如果环境是cpu，改成cpu就可以了
2. 报错：TypeError: _tokenize() got an unexpected keyword argument 'truncate_first_se，原来我的torch版本是1.13.0+cpu，需要对接transforer为=2.0.0就可以了，2.1.1就报错
3. 报错：ImportError: cannot import name ‘WarmupLinearSchedule‘ from ‘transformers‘，transformers版本调整为2.2.1改为 pip install transformers==2.1.1



# 用法
下载项目后，数据都有，直接运行main函数就可以了

项目运行后，cpu大概4个小时
![image](https://github.com/likeqiang1001/Bert-aq/assets/12680223/0c104f57-a8a4-487b-a66f-fdb2ca9ace31)

ner_main的运行命令如下

python .\NER_main.py --data_dir=D:\\jpdir\\bert\\bert-aq\\Bert-master\\Bert-master\\input\\data_\\ner_data --vob_file=D:\\jpdir\\bert\\bertchinese\\vocab.txt --model_config=D:\\jpdir\\bert\\bertchinese\\config.json --output=D:\\jpdir\\bert\\bert-aq\\Bert-master\\Bert-master\\output --pre_train_model=D:\\jpdir\\bert\\bertchinese\\pytorch_model.bin --max_seq_length=64 --do_train=true --train_batch_size=32 --eval_batch_size=128 --gradient_accumulation_steps=4 --num_train_epochs=15

