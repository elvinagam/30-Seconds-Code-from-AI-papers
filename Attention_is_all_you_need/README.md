This is from Attention is All you need - Transformers paper

Encoding used there was Byte Pair algorithm - (which recently updated to be sentence piece, word piece). It’s used by a lot of Transformer models, including GPT, GPT-2, RoBERTa, BART, and DeBERTa.

One problem that Byte Pair encoding solves is to minimize the number of UNK characters in a set. When training NLP models, if a word was not existed in the training dataset, then this word was locked to be unknown to the model. 

> Step 1: Compute the base vocabulary: Split words into letters and calculate their frequency.
> Step 2: Create a window and go through 2 consecutive letters
> Step 3: Calculate the frequency of 2 letters from previous step
> Step 4: Find the most frequency 2 letter pair
> Step 5: Add it to the vocabulary
> Step 6: Repeat untill you think you tokenized combinations such as est, er in words slow, slower, slowest.

Next level from Byte Pair Encoding is Sentence Piece, where we also calculate the score of each pair, and then decide based on score (not the frequency) whether to add the pair as our token or not. Pair score is calculated as 
`Frequency of pair/ (Frequency of first letter * Frequency of second letter)`
