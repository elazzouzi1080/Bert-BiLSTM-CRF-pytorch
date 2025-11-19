# Bert-BiLSTM-CRF-pytorch
bert-bilstm-crf implemented in pytorch for named entity recognition.

```
python == 3.6
pytorch == 0.4.1
pytorch_pretrained_bert == 0.6.1
```

### Data
* 首先将数据处理成`BIO`格式，processed文件夹下存放的是医疗命名实体识别的数据，代码可参考`data_process.ipynb`
* 下载中文BERT预训练模型,来自`pytorch-pretrained-bert`

### 模型训练
```
python main.py -- n_epochs 100 --finetuning --top_rnns
```


### 模型预测
```
python crf_predict.py
```


## 🏗️ Architecture du framework
```
TracIA_Usecases/
├── 📄 heart_failure_clinical_records_dataset_with_row_id.csv
│ └── Dataset + identifiant unique (row_id)
│
├── ⚙️ manifest.json
│ └── Configuration centralisée (splits k=5, métriques, random_state)
│
├── 📊 train_ids_fold*.csv & test_ids_fold*.csv
│ └── Partitions fixes pour la validation croisée
│
├── 🐍 fixed_cv_binary_classification.py
│ └── Pipeline complet : 9 modèles ML + métriques + visualisations
│
└── 📘 02_run_binary_classification_pipeline.ipynb
└── Exécution interactive et reproductible
```
