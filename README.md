# hULMonA: tHe first Universal Language MOdel iN Arabic

Paper: https://www.aclweb.org/anthology/W19-4608

## Introduction

Recent state-of-the-art models in NLP (e.g., BERT, GPT, ULMFiT) utilize transfer learning by pre-training a language model on large curpos and then fine-tuning it on any downstream task. We developed the first Arabic specific universal language model, hULMonA, that can be fine-tuned for almost any Arabic text classification task. We evaluated hULMonA on Sentiment Analysis and achieved state-of-the-art on 4 Arabic datasets. hULMonA consists of three main stages:

## 1. General domain hULMonA pretraining
To capture the various properties of the Arabic language, we train the SOTA-ish language model AWD-LSTM on all Arabic Wikipedia.

<img src="https://user-images.githubusercontent.com/9033365/62253743-989d7880-b3ff-11e9-8c49-3906265dce6d.png" width="300" />

This step is time consuming, but it should be done only once. We publish our pre-trained model, and it is availabe in **models** directory. To check the implementation details, or to pre-train your own LM, check [build_arabic_language_model.ipynb](./build_arabic_language_model.ipynb)

## 2. Target task hULMonA fine-tuning
The target task data (e.g., Twitter) will likely come from a different distribution than the general-domain data (Wikipedia). Therefore, fine-tuning the pretrained general-domain LM on the target task data is necessary for the LM to adapt to the new textual properties (e.g., dialects).

<img src="https://user-images.githubusercontent.com/9033365/62254187-e9fa3780-b400-11e9-925d-fff82d057845.png" width="300" />

To fine-tune the pre-trained hULMonA on your own dataset, please check [fine_tune_LM.ipynb](./fine_tune_LM.ipynb)

## 3. Target task classification
Finally, for downstream task classification, we augment the fine-tuned hULMonA with two fully connected layers with ReLU and Softmax activations respectively. Implementatoin details can be found here: [fine_tune_LM.ipynb](./fine_tune_LM.ipynb)

<img src="https://user-images.githubusercontent.com/9033365/62254560-46aa2200-b402-11e9-8550-adadbd1561f8.png" width="300" />


## How do I cite hULMonA?
Please cite [this paper](https://www.aclweb.org/anthology/W19-4608):

```
@inproceedings{eljundi2019hulmona,
  title={hULMonA: The Universal Language Model in Arabic},
  author={ElJundi, Obeida and Antoun, Wissam and El Droubi, Nour and Hajj, Hazem and El-Hajj, Wassim and Shaban, Khaled},
  booktitle={Proceedings of the Fourth Arabic Natural Language Processing Workshop},
  pages={68--77},
  year={2019}
}
```

## Contact information
For help, issues, or personal communication related to using hULMonA, please contact Obeida ElJundi (`oae15@mail.aub.edu`), Wissam Antoun (`wfa07@mail.aub.edu`), or Nour El Droubi (`ngd02@mail.aub.edu`).
