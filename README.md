# POS_tagger
The process of classifying words into their parts of speech and labeling them accordingly is known as part-of-speech tagging, or simply POS-tagging.
Network layout : Preprossing --> Vanilla RNN --> Word Embedding --> LSTM --> GRU --> Birectional RNN --> Model Evaluation
Library used : NLTK,gensim ( major one's_
Metrix used : Accurancy
Loss: 0.022716592997312546, Accuracy: 0.9937946796417236 (Best performance among all models mentioned here).The same was achieved by Birectional LSTM.
Code walk through : 
All necessary library imported.Three most commonly used corpus of NLTK combined and stored in tagged_sentences.This is a mapping of word with its corresponding POS.
This is standard Many to many RNN architecture ( input sequence and output sequence have same lenght),where each data point will have multiple words in a sentence.This will be treated as X and correspoing POS will be treated as Y.We have devided "tagged_sentences" into X and Y.
Simple Tokenization is also experimented before word embeddingd. In tokenization, each word in X is just given unique number and it has nothing to do with syntactic meaning like word embedding which creats a multidimentional vector for each word.
Since all input to neural network must have same length, we have used padding to make all sentence of same length.Here taken as 100.
for Y, we have simply used one hot encoding.
Data is now splitted into training, validation and test.
First model used is Vanilla RNN, where model architecture used is Sequential and over which different layers eg. Embedding,Simple RNN , dense , softmax layer put.
In similar way, we have used LSTM,GRU,Birectional RNN.
Since basic model developed is already out perperformed, we did not get significant improvement with LSTM , GRU or Birectionla RNN.
LSTM have performed quite well however,Bidirctional RNN out performed as expected but at the cost of increased training parameters/traing time.
