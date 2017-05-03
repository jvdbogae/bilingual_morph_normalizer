# Bilingual morph normalizer

Normalize the source language with respect to the
target language by merging source words that have
a similar distribution over target words p(e|f)
using an entropy-based criterion.

In the source file, words are represented as a
sequence of one lemma, one PoS and tags, separated
by space. Each word representation is separated
by tabs. Ex.:

src: `je Pron Sg Ps1 -	 normaliser Vb Sg Ps1 Pres`
trg: `I normalize`

USAGE
-----

`python3 train_bmn.py -s file.tags.src -t file.words.trg -a file.ali`

This outputs a normalization model in the pickle file `norm_model.pkl`.
Using the `-use-mean` argument is recommended for better runtime and performance.

Apply the model to the data, given that the model is located in the working directory:

`python3 normalize_morph.py -i file.tags.src -o file.normalized.src`

PUBLICATION
-----------

Franck Burlot and François Yvon. Learning Morphological Normalization for Translation from and into Morphologically Rich Languages, European Association for Machine Translation (EAMT), 2017