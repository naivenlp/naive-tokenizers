# naive-tokenizers

![Python package](https://github.com/naivenlp/naive-tokenizers/workflows/Python%20package/badge.svg)
[![PyPI version](https://badge.fury.io/py/naive-tokenizers.svg)](https://badge.fury.io/py/naive-tokenizers)
[![Python](https://img.shields.io/pypi/pyversions/naive-tokenizers.svg?style=plastic)](https://badge.fury.io/py/naive-tokenizers)


Tokenizers for NLP tasks.

## Installation

```bash
pip install -U naive-tokenizers
```

## Usage

```bash
>>> from naive_tokenizers import JiebaTokenizer, TransformerTokenizer, BertTokenizer
>>> from naive_tokenizers import DefaultIntervener
>>> intervener = DefaultIntervener()
>>> jieba = JiebaTokenizer(vocab_file='testdata/vocab_chinese.txt', intervener=intervener)
Building prefix dict from the default dictionary ...
Loading model from cache /var/folders/vl/s79n468900g83fqc558bkkz80000gn/T/jieba.cache
Loading model cost 0.564 seconds.
Prefix dict has been built successfully.
>>> print(jieba.tokenize('高级javadeveloper'))
['高级', 'javadeveloper']
>>> 
>>> 
>>> intervener.add_split_token('javadeveloper', 'java developer')
>>> print(jieba.tokenize('高级javadeveloper'))
['高级', 'java', 'developer']
>>> 
>>> transformer = TransformerTokenizer(vocab_file='testdata/vocab_chinese.txt')
>>> print(transformer.tokenize('高级javadeveloper'))
['高', '级', 'java', '##de', '##vel', '##oper']
>>> 
>>> bert = BertTokenizer(vocab_file='testdata/vocab_chinese.txt')
>>> print(bert.tokenize('高级javadeveloper'))
['高', '级', 'java', '##de', '##vel', '##oper']
>>> 
>>> 

```
