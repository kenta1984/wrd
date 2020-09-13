# WRD implementaion for Japanese texts
This repository is a WRD(Word Rotator's Distance) implemenation for Japanese texts.
WRD is an improved algorithm of WMD(Word Mover's Distance) and achieves great performances in measuring textual similarities.
See the details in the [paper](https://arxiv.org/abs/2004.15003v1).

## Requirements
### Install Python modules
- [gensim](https://pypi.org/project/gensim/)
- [mecab-python3](https://pypi.org/project/mecab-python3/) with [MeCab](https://taku910.github.io/mecab/) and [Neologd dictionary](https://github.com/neologd/mecab-ipadic-neologd)
- [POT](https://pythonot.github.io/)

### Download pre-trained vectors for Word2vec
From [this site](https://github.com/singletongue/WikiEntVec/releases), download pre-trained vectors trained on Japanese Wikipedia and set it in `vecs` directory.
`jawiki.word_vectors.200d.txt.bz2` is recommended.

If you want, your original pre-trained vectors could be used.

## Usage
Just run the below command. `--mecab_dict_path` is an optional argument.

```
$ python main.py --mecab_dict_path /usr/local/lib/mecab/dic/mecab-ipadic-neologd/
```

The result is shown as below, if you succeed.
The value of the final line is WRD of the two sentences.
The smaller WRD, the more similar.
The larger WRD, the less similar.

```
大坂なおみ 逆転で2年ぶり2度目の全米OP優勝。3度目のグランドスラム制覇
大坂なおみが2年ぶり2回目のV　4大大会3勝目　全米テニス
0.31
```

```
大坂なおみ 逆転で2年ぶり2度目の全米OP優勝。3度目のグランドスラム制覇
大相撲秋場所 八角理事長「横綱不在 申し訳ない」
0.57
```

If you'd like to change the sentences to compare, edit the [main.py]() directly. 
