
### 1. [(2015 ACL) Hierarchical Recurrent Neural Network for Document Modeling](http://www.aclweb.org/anthology/D15-1106)
* 使用了两个RNN， 一个用于句子层次的编码，一个用于词层次的解码
* 句子层次的编码RNN的输入是句子的BoW特征
* 词层次的解码RNN输入包含前一句的sent_RNN的结果，隐状态，和前一时刻的输入

### 2. [(2015) A Hierarchical Neural Autoencoder for Paragraphs and Documents](https://arxiv.org/pdf/1506.01057.pdf)
* 是一个autoencoder模型， encoder-decoder结构
* 提出了 
* * 1）普通seq2seq model
* * 2）Hierarchical seq2seq Model
* * 3）Hierarchical seq2seq Model with Attention: 好像只有句子级别的attention， 需要仔细再读

### 3. [(2016) Building End-To-End Dialogue Systems Using Generative Hierarchical Neural Network Models](https://arxiv.org/pdf/1507.04808.pdf)

### 4. [(2016) Hierarchical Attention Networks for Document Classification](https://www.cs.cmu.edu/~hovy/papers/16HLT-hierarchical-attention-networks.pdf)

### 5. [(2016) Contextual LSTM (CLSTM) models for Large scale NLP tasks](https://arxiv.org/pdf/1602.06291.pdf)

### 6. [(2018 ACL) Sentence-State LSTM for Text Representation](http://aclweb.org/anthology/P18-1030)
