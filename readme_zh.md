## 安装步骤
> git clone https://github.com/IT-YUNMENGZE/glove-python.git

> python -m venv ./glove-python

> source glove-python/bin/activate

> pip install glove_python_binary

> cd glove-python && python setup.py install


## 安装成功
![image](https://user-images.githubusercontent.com/46949136/120444899-aab11f00-c3ba-11eb-890e-92b40ac8f5b8.png)

## 数据集准备
将数据集目录文件放在`./examples`目录下

## 训练
`ipython -i -- examples/example.py -c examples/sample_txt/ -t 10 -p 4`

`t:Train the GloVe model with this number of epochs.`

`p:Number of parallel threads to use for training.`



![image](https://user-images.githubusercontent.com/46949136/120447153-e0ef9e00-c3bc-11eb-8905-c5d6aa92c6af.png)

训练完成后，得到两个model文件：`corpus.model` 和 `glove.model`

## 模型加载
`glove = Glove.load('glove.model')`

`corpus = Corpus.load('corpus.model')`

## 使用:求相似word或者paragraph
`glove.most_similar('sun', number=10)` 或者 `glove.most_similar_paragraph(paragraph, number=5, **kwargs)`

## 使用：词向量矩阵
//全部词向量矩阵
`glove.word_vectors`

//指定词条词向量
`glove.word_vectors[glove.dictionary['sun']]`

//导出全部词向量为npy文件
`numpy.save('words_vector.npy',glove.word_vectors) `

## 使用：共现矩阵
`corpus.matrix.todense().tolist()`