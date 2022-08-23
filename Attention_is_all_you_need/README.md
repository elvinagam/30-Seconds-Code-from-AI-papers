This is from Attention is All you need - Transformers paper

Encoding used there was Byte Pair algorithm - (which recently updated to be sentence piece, word piece). It’s used by a lot of Transformer models, including GPT, GPT-2, RoBERTa, BART, and DeBERTa.

One problem that Byte Pair encoding solves is to minimize the number of UNK characters in a set. When training NLP models, if a word was not existed in the training dataset, then this word was locked to be unknown to the model. However,
