## Github Projects

### 0. [Awesome Sentiment Analysis](https://github.com/laugustyniak/awesome-sentiment-analysis):
* laugustyniak 总结的情感分析相关的数据、系统和论文
* 可以参考

### 1. [Sentiment-Analysis-Twitter: by Ayush Pareek](https://github.com/ayushoriginal/Sentiment-Analysis-Twitter):

2016年左右的工作， 比较传统的NLP处理方法，包括：
* twitter预处理 (处理Hashtags, @, URLs, Emoticons, Punctuations, Repeating characters) + stemmer and lemmatization
* 特征提取（很复杂、很多的人工特征）
* 分类器（Naive bayes, Maximum Entropy, SVM ...）

* 同时给出了两个比较小的数据集： 几千条左右的样本
* 数据为二分类 或 三分类（加中性）

**预处理的代码可以参考， 一些特征也可以考虑**

### 2 [Sentiment Analysis on Tweets: by abdulfatir](https://github.com/abdulfatir/twitter-sentiment-analysis):

* 2017年左右的工作， 实现了许多模型，包括 NB, Maximum Entropy, Decision Tree, Random Forest, XGBoost, SVM, MLP, RNN, CNN等
还包括一个基于投票的融合算法

* 数据来源是[Kaggle CS5228 Project 2](https://www.kaggle.com/c/cs5228-project-2/)
* 该项目包含一个[项目报告文件](https://github.com/abdulfatir/twitter-sentiment-analysis/blob/master/docs/report.pdf)，介绍了其各个算法的性能，总体来说还是CNN和RNN性能最好。

### 3 [DeepMoji](https://github.com/bfelbo/DeepMoji):

* 之前看过的论文，利用emoji数据预训练句子向量表示
* 但是项目并没有公开大规模的twitter数据

## Dataset

### 1. [Kaggle twitter_sentiment](https://www.kaggle.com/ywang311/twitter-sentiment)
* 二分类数据： train 56MB (大约有150多万条样本， 好像来自 sentiment140)

### 2. [Kaggle twitter-sentiment-analysis2](https://www.kaggle.com/c/twitter-sentiment-analysis2/data)
* 二分类数据： 大概有10万条短文本训练数据 （8MB）

### 3. [Kaggle twitter-sentiment-analysis](https://www.kaggle.com/c/twitter-sentiment-analysis/data)
* 二分类数据， 数据量好像很大 （train: 100MB, test: 22MB）
* 无法下载

### 4. [Kaggle Twitter Analysis](https://www.kaggle.com/c/twitter-analysis/data)
* 二分类数据： train 40MB, test: 23MB
* 无法下载

### 5. [Kaggle CS5228 Project 2](https://www.kaggle.com/c/cs5228-project-2/data)
* 二分类数据： 上面的github project也提到过 train 65MB, test 16MB 左右
* 无法下载




