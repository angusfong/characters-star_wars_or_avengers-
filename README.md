# AWESOME Character-level Neural Networks
A collection of references on character-level neural networks

## Contact
Angus Fong (Yale CPSC 677)
hoching.fong@yale.edu

## Summary
Character-level neural networks have risen in popularity in the last four years. Landmark papers have applied CNN's and LSTM's on character-level input to tasks including language modeling, text classification, neural machine translation, speech recognition, and question answering. Because a character-level model does not rely on a fixed vocabulary of words, it 1. provides a complete description of morphological inflexions for many languages, 2. reduces the number of parameters for model input, 3. utilizes subword-level information to model language, 4. addresses out-of-vocabulary words, including jargon and misspelled words, by estimating their semantics, and 5. requires no domain knowledge about language syntax and semantical hierarchy.

## Outline

- [Tutorial / Survey / Book](#tutorials)
- [Blogs](#blogs)
- [Papers](#papers)
  - [Theory](#theory)
  - [Language Modeling](#language-modeling)
  - [POS Tagging](#pos-tagging)
  - [Parsing](#parsing)
  - [Text Generation](#text-generation)
  - [Question Answering](#question-answering)
  - [Machine Translation](#machine-translation)
  - [Morphological Reasoning](#morphological-reasoning)
  - [Text Classification](#text-classification)
- [Datasets](#datasets)


## Tutorials
### Language modeling with RNN's
* Multi-layer Recurrent Neural Networks (LSTM, GRU, RNN) for character-level language models in Torch
[[Karpathy](https://github.com/karpathy/char-rnn)]

## Blog posts
* [The unreasonable effectiveness of recurrent neural networks](http://karpathy.github.io/2015/05/21/rnn-effectiveness/)
* [Character-level language model](https://towardsdatascience.com/character-level-language-model-1439f5dd87fe)

## Papers

###Theory
* Character-level Recurrent Neural Networks in Practice: Comparing Training and Sampling Schemes [[paper](https://arxiv.org/abs/1801.00632)]

###Language modeling
* Character-Aware Neural Language Models [[paper](https://arxiv.org/pdf/1508.06615.pdf)]
    + \underline{Highlight:} Word-level language models do not handle out-of-vocabulary (OOV) words, and their parameter count scales with the number of words. Kim et. al. remove the need of a vocabulary by using purely character-level inputs. It uses a CNN combined with a highway layer to obtain word embeddings, which is fed into a standard LSTM language model. Model perplexity on various datasets, especially in morphologically rich languages, were on par with state-of-the-art despite using much less parameters. 

* Character-Level Language Modeling with Hierarchical Recurrent Neural Networks (2016) [[paper](https://arxiv.org/abs/1609.03777)]

    + \underline{Highlight:} Hwang et. al. model language one letter at a time, but as informed by word-level contextual information. To do this, "hierarchical RNN's" are introduced in which an LSTM with a slower clock (word) resets an LSTM with a faster clock (character), allowing a confluence of information between short-term details and long-range dependencies to optimally predict a character sequence. This results in a much reduced parameter count, while model perplexity remains competitive. Applications for automatic speech recognition are discussed.

### POS tagging
* Learning Character-level Representations for Part-of-Speech Tagging (JMLR 2014) [[paper](http://proceedings.mlr.press/v32/santos14.pdf)]

### Parsing
* Improved Transition-Based Parsing by Modeling Characters instead of Words with LSTMs (EMNLP 2015) [[paper](https://arxiv.org/abs/1508.00657)]

### Text generation
* Generating Text with Recurrent Neural Networks (ICML 2011) [[paper](https://www.cs.utoronto.ca/~ilya/pubs/2011/LANG-RNN.pdf)]

* Generating Sequences With Recurrent Neural Networks [[paper](https://arxiv.org/abs/1308.0850)]

### Question answering
* Character-level Question Answering with Attention (EMNLP 2016)
[[paper](http://www.aclweb.org/anthology/D16-1166)]

### Machine translation
* Fully Character-Level Neural Machine Translation without Explicit Segmentation (TACL 2017) [[paper](https://arxiv.org/abs/1610.03017)]
    + \underline{Highlight:} By going to the character level, Lee et. al. address the need to remove a fixed-size vocabulary for machine translation, which is necessary for languages such as Czech and Turkish, which are built upon morphological inflexions. The need to segment text into word tokens is also removed. A new encoder-decoder with attention built on a CNN is proposed. This character-level model for both source comprehension and target generation outperforms strong subword- and word-level baselines. Multilingual translation outperformed bilingual translation, motivating future translation models to take a universal, crosslingual approach using character inputs.

* Character-based neural machine translation (ICLR 2016) [[paper](https://arxiv.org/abs/1511.04586)]

* Character-based neural machine translation (ACL 2016) [[paper](https://arxiv.org/pdf/1603.00810.pdf)]

### Morphological reasoning
* Character-based recurrent neural networks for morphological relational reasoning (ACL 2017) [[paper](http://www.aclweb.org/anthology/W17-4108)]

### Text classification
* Character-level Convolutional Networks for Text Classification (NIPS 2015) [[paper](https://arxiv.org/abs/1509.01626)]
    + \underline{Highlight:} This work attempts to understand text from scratch, without prior semantic or syntactical knowledge. An end-to-end CNN that reads input text character-by-character is trained to perform tasks such as sentiment and topic classification. Compared with previous word-level models, this CNN does better on larger datasets. Across a variety of tasks, fully character-level demonstrate discriminative text understanding.
