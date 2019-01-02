# QUESTION ANSWERING USING MODIFIED QANET



1) A Tensorflow implementation of Google's [QANet](https://openreview.net/pdf?id=B14TlG-RW) 
   (Note: This is not an official implementation from the authors of the paper)

   Unofficial Implementation source: https://github.com/NLPLearn/QANet

2) List of modified files:
	a) prepro.py : Functions modified - get_embedding(),build_features()
		       Functions created - get_POS_one_hot_vector()

	b) model.py : Functions modified - forward()

	c) layers.py : Functions created - drnn(), bidirlstm(), bidirectional_dynamic_rnn()

	d) demo.py : Functions modified - answer() 

	e) config.py : Tuned hyperparameters

3) List of commands: 
	
To download and preprocess the data, run


## download SQuAD and Glove
a) sh download.sh


## preprocess the data
b) python config.py --mode prepro

hyper parameters are stored in config.py. To debug/train/test/demo, run

c) python config.py --mode debug/train/test/demo

d) The default directory for the tensorboard log file is `train/{model_name}/event`


## Tensorboard
Run tensorboard for visualisation.

$ tensorboard --logdir=./


4) List of requirements:
  * Python>=2.7
  * NumPy
  * tqdm
  * TensorFlow>=1.5
  * spacy==2.0.9
  * bottle (only for demo)
  * Cuda 10


## Dataset
The dataset used for this task is [Stanford Question Answering Dataset](https://rajpurkar.github.io/SQuAD-explorer/).
Pretrained [GloVe embeddings](https://nlp.stanford.edu/projects/glove/) obtained from common crawl with 840B tokens used for words.



