# GTS
[Grid Tagging Scheme for Aspect-oriented Fine-grained Opinion Extraction](https://arxiv.org/pdf/2010.04640.pdf). Zhen Wu, Chengcan Ying, Fei Zhao, Zhifang Fan, Xinyu Dai, Rui Xia. In Findings of EMNLP, 2020.

## Evaluation on ASOTE
We folk this repository from the [GTS repository](https://github.com/NJUNLP/GTS) and evaluate the [GTS model](https://arxiv.org/pdf/2010.04640.pdf) on the [ASOTE](https://arxiv.org/pdf/2103.15255.pdf) task.

### Supported datasets
res14, lap14, res15, res16

### LSTM
sh run.sh 4 src/NNModel/main.py --prefix data/ --model_dir GTS-ASOTE-model/ --task triplet --mode train --model bilstm --dataset res14 > bilstm.res14.log 2>&1 &
sh run.sh 4 src/NNModel/main.py --prefix data/ --model_dir GTS-ASOTE-model/ --task triplet --mode test --model bilstm --dataset res14 > bilstm.res14.log 2>&1 &

sh run.sh 5 src/NNModel/main.py --prefix data/ --model_dir GTS-ASOTE-model/ --task triplet --mode train --model bilstm --dataset lap14 > bilstm.lap14.log 2>&1 &
sh run.sh 5 src/NNModel/main.py --prefix data/ --model_dir GTS-ASOTE-model/ --task triplet --mode test --model bilstm --dataset lap14 > bilstm.lap14.log 2>&1 &

sh run.sh 4 src/NNModel/main.py --prefix data/ --model_dir GTS-ASOTE-model/ --task triplet --mode train --model bilstm --dataset res15 > bilstm.res15.log 2>&1 &
sh run.sh 4 src/NNModel/main.py --prefix data/ --model_dir GTS-ASOTE-model/ --task triplet --mode test --model bilstm --dataset res15 > bilstm.res15.log 2>&1 &

sh run.sh 5 src/NNModel/main.py --prefix data/ --model_dir GTS-ASOTE-model/ --task triplet --mode train --model bilstm --dataset res16 > bilstm.res16.log 2>&1 &
sh run.sh 5 src/NNModel/main.py --prefix data/ --model_dir GTS-ASOTE-model/ --task triplet --mode test --model bilstm --dataset res16 > bilstm.res16.log 2>&1 &


#### CNN
sh run.sh 6 src/NNModel/main.py --prefix data/ --model_dir GTS-ASOTE-model/ --task triplet --mode train --model cnn --dataset res14 > cnn.res14.log 2>&1 &
sh run.sh 6 src/NNModel/main.py --prefix data/ --model_dir GTS-ASOTE-model/ --task triplet --mode test --model cnn --dataset res14 > cnn.res14.log 2>&1 &

sh run.sh 7 src/NNModel/main.py --prefix data/ --model_dir GTS-ASOTE-model/ --task triplet --mode train --model cnn --dataset lap14 > cnn.lap14.log 2>&1 &
sh run.sh 7 src/NNModel/main.py --prefix data/ --model_dir GTS-ASOTE-model/ --task triplet --mode test --model cnn --dataset lap14 > cnn.lap14.log 2>&1 &

sh run.sh 6 src/NNModel/main.py --prefix data/ --model_dir GTS-ASOTE-model/ --task triplet --mode train --model cnn --dataset res15 > cnn.res15.log 2>&1 &
sh run.sh 6 src/NNModel/main.py --prefix data/ --model_dir GTS-ASOTE-model/ --task triplet --mode test --model cnn --dataset res15 > cnn.res15.log 2>&1 &

sh run.sh 7 src/NNModel/main.py --prefix data/ --model_dir GTS-ASOTE-model/ --task triplet --mode train --model cnn --dataset res16 > cnn.res16.log 2>&1 &
sh run.sh 7 src/NNModel/main.py --prefix data/ --model_dir GTS-ASOTE-model/ --task triplet --mode test --model cnn --dataset res16 > cnn.res16.log 2>&1 &


### BERT
sh run.sh 0 src/BertModel/main.py --prefix data/ --model_dir GTS-ASOTE-model/bert/ --task triplet --mode train --dataset res14 > bert.res14.log 2>&1 &
sh run.sh 0 src/BertModel/main.py --prefix data/ --model_dir GTS-ASOTE-model/bert/ --task triplet --mode test --dataset res14 > bert.res14.log 2>&1 &

sh run.sh 1 src/BertModel/main.py --prefix data/ --model_dir GTS-ASOTE-model/bert/ --task triplet --mode train --dataset lap14 > bert.lap14.log 2>&1 &
sh run.sh 1 src/BertModel/main.py --prefix data/ --model_dir GTS-ASOTE-model/bert/ --task triplet --mode test --dataset lap14 > bert.lap14.log 2>&1 &

sh run.sh 2 src/BertModel/main.py --prefix data/ --model_dir GTS-ASOTE-model/bert/ --task triplet --mode train --dataset res15 > bert.res15.log 2>&1 &
sh run.sh 2 src/BertModel/main.py --prefix data/ --model_dir GTS-ASOTE-model/bert/ --task triplet --mode test --dataset res15 > bert.res15.log 2>&1 &

sh run.sh 3 src/BertModel/main.py --prefix data/ --model_dir GTS-ASOTE-model/bert/ --task triplet --mode train --dataset res16 > bert.res16.log 2>&1 &
sh run.sh 3 src/BertModel/main.py --prefix data/ --model_dir GTS-ASOTE-model/bert/ --task triplet --mode test --dataset res16 > bert.res16.log 2>&1 &

## Data
[[Data](https://github.com/NJUNLP/GTS/tree/main/data)]   [[Pre-trained Model](https://drive.google.com/drive/folders/15HZun7FeObpNaJF1gwrJxn2H6e28LPZY?usp=sharing)(from huggingface)]. Data format descriptions are [here](https://github.com/NJUNLP/GTS/blob/main/data/datareadme.md).

**Note**: our opinion triplet datasets are from alignments of our previous work [TOWE](https://www.aclweb.org/anthology/N19-1259/) datasets and the original SemEval [2014](https://www.aclweb.org/anthology/S14-2004/), [2015](https://www.aclweb.org/anthology/S15-2082/), [2016](https://www.aclweb.org/anthology/S16-1002/) datasets.

## Requirements
See requirement.txt or Pipfile for details
* pytorch==1.7.1
* transformers==3.4.0
* python=3.6

## Usage
- ### Training
For example, you can use the folowing command to fine-tune Bert on the OPE task (the pre-trained Bert model is saved in the folder "pretrained/"):
```
python main.py --task pair --mode train --dataset res14
```
The best model will be saved in the folder "savemodel/".

- ### Testing
For example, you can use the folowing command to test Bert on the OPE task:
```
python main.py --task pair --mode test --dataset res14
```

**Note**: In our pre-experiments, a smaller batch size and learning rate can achieve better performance on certain datasets, while we use a general setting in our paper to save time instead of adopting grid search.

## Citation
If you used the datasets or code, please cite our paper:
```bibtex
@inproceedings{wu-etal-2020-grid,
    title = "Grid Tagging Scheme for Aspect-oriented Fine-grained Opinion Extraction",
    author = "Wu, Zhen  and
      Ying, Chengcan  and
      Zhao, Fei  and
      Fan, Zhifang  and
      Dai, Xinyu  and
      Xia, Rui",
    booktitle = "Findings of the Association for Computational Linguistics: EMNLP 2020",
    month = nov,
    year = "2020",
    address = "Online",
    publisher = "Association for Computational Linguistics",
    url = "https://www.aclweb.org/anthology/2020.findings-emnlp.234",
    doi = "10.18653/v1/2020.findings-emnlp.234",
    pages = "2576--2585",
}
```

## Reference
[1]. Zhen Wu, Chengcan Ying, Fei Zhao, Zhifang Fan, Xinyu Dai, Rui Xia. [Grid Tagging Scheme for Aspect-oriented Fine-grained Opinion Extraction](https://arxiv.org/pdf/2010.04640.pdf). In Findings of EMNLP, 2020.

[2]. Zhifang Fan, Zhen Wu, Xin-Yu Dai, Shujian Huang, Jiajun Chen. [Target-oriented Opinion Words Extraction with Target-fused Neural Sequence Labeling](https://www.aclweb.org/anthology/N19-1259.pdf). In Proceedings of NAACL, 2019.
