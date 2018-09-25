
### 2018 [The Best of Both Worlds: Combining Recent Advances in Neural Machine Translation](http://aclweb.org/anthology/P18-1008)

深度探索了目前比较流行的RNN Seq2Seq model, ConvSeq2Seq model 以及Transformer 三种模型，讨论了其中的优化技巧和模型构架。
贡献有三点： 
1. 量化比较了几种模型改进： multi-head attention， layer normalization， 和优化技巧，比如 synchronous replica training和label smoothing， 这些技巧可以适用于不同的模型
2. 将这些技巧应用与RNMT模型， 和ConvS2S, Transformer进行了量化对比
3. 提出了一种新的模型结构

#### RNMT
* 通常包含一组RNN encoder， 有一个或多个双向RNN层； 一组单向RNN的decoder；通常使用LSTM或GRU；层之间使用residual or highway connection
* 基于Google-NMT, encoder包含一个双向LSTM层，跟着7个单向LSTM层； decoder由一个attention network 和 8个单向LSTM层； 使用residual skip connections

#### ConvS2S
* encoder decoder 都是卷积层， 每层包好1-dimensional convolutions 和 GLU
* scale gradients of encoder to stabilize training
* residual connections
* Positional embeddings
* weight normalization

#### Transformer
* 不同于RNMT, 与ConvS2S类似， 全并行
* 使用self-attention解决ConvS2S感受野受限（limited receptive field）的问题
* 模型中非常重要的细节： 1） transformer的每一层都按照一个严格的计算顺序（normalize -> transform -> dropout -> residual-add）； 2）除了每层的normalization， 最终的encoder output又　normalize了一下，避免 blow up （？）

#### 一些理论理解
* RNN的表示能力很强，但是面临可训练性和表达能力的两难困境
* CNN擅长捕捉局部信息， 需要通过增加层数（比如15层）来扩展感受野， 扩大层数需要训练技巧，比如初始化和正则化技巧
* Transformer 的感受野较大， 但是由于缺少记忆机制，削弱了其作为一个序列模型的能力， 需要额外的positional信息 （例如 sinusoidal positional encodings）


#### RNMT+
* 模型结构： 
* * encoder: 6个双向LSTM层， with dropout and residual-add，最后一层的结果经过一个projection layer
* * multi-head attention: 基于encoder的最后一层经过一个projection layer的结果以及decoder的第一个单向LSTM， attention context vector is fed into the rest of the decoder layers and the softmax layer
* * 8个单向LSTM层
* 正则化手段
* * Dropout： embedding layer and each LSTM layer output, attention dropout (?)
* * Label Smoothing: Label Smoothing 对于Transformer和RNMT+都非常有用，特别是RNMT+ with multi-head attention， 另外一个发现是， 对于在训练中使用label smoothing的模型，在解码时使用大一点的beam size（16， 20）会有帮助
* * Weight Decay： l2 1e-5， 在小数据集 WMT' 14 En->De 上使用了
* Optimizer： Adam (0.9, 0.999, 1e-6) 学习率采用 先上升， 再保持， 在decay的方式

#### 优化技巧结论
* label smoothing: 有效，可以提升RNMT+和transformer
* Multi-head Attention: 非常有效
* layer normalization: 对于稳定训练过程非常必要
* Synchronous training: 比较有用， 必须配合learning rate warmup


