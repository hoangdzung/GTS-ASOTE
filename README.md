# GTS
[Grid Tagging Scheme for Aspect-oriented Fine-grained Opinion Extraction](https://arxiv.org/pdf/2010.04640.pdf). Zhen Wu, Chengcan Ying, Fei Zhao, Zhifang Fan, Xinyu Dai, Rui Xia. In Findings of EMNLP, 2020.

## Evaluation on ASOTE
We folk this repository from the [GTS repository](https://github.com/NJUNLP/GTS) and evaluate the [GTS model](https://arxiv.org/pdf/2010.04640.pdf) on the [ASOTE](https://arxiv.org/pdf/2103.15255.pdf) task.

### Supported datasets
res14, lap14, res15, res16

### LSTM
python main.py --task triplet --mode train --model bilstm --device cpu --dataset res14
python main.py --task triplet --mode test --model bilstm --device cpu --dataset res14

#### CNN
python main.py --task triplet --mode train --model cnn --device cpu --dataset res14
python main.py --task triplet --mode test --model cnn --device cpu --dataset res14

### BERT
python main.py --task triplet --mode train --device cpu --dataset res14
python main.py --task triplet --mode test --device cpu --dataset res14

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
