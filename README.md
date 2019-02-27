# AutoScriptGeneration

In this project, I generate my own Seinfeld TV scripts using a recurrent neural network (RNN). The dataset used to train the network consists of scripts from 9 Seinfeld seasons. After training on the dataset, the RNN can create a new, "fake" TV script.

## Generated TV Script

jerry: what about me?

jerry: i don't have to wait.

kramer:(to the sales table)

elaine:(to jerry) hey, look at this, i'm a good doctor.

newman:(to elaine) you think i have no idea of this...

elaine: oh, you better take the phone, and he was a little nervous.

kramer:(to the phone) hey, hey, jerry, i don't want to be a little bit.(to kramer and jerry) you can't.

jerry: oh, yeah. i don't even know, i know.

jerry:(to the phone) oh, i know.

kramer:(laughing) you know...(to jerry) you don't know.

## Network Hyperparameters

I decided on the hyperparameters through intuition,test results and some browsing some codes.

sequence_lengths = Normally by seeing the output a line should contain some words so I took 15 for the words in each line.

batch_size = 128 is quite standard in many people's codes,so I went for it

epochs = I am training with 5 epochs.

learning_rate = 0.001 based on some research papers.

input_size = length of vocab_to_int size and extra one for just padding

output_size = same length of vocab_to_int size because output word may be any one of these.

embedding_dim = I thought embedding dim is the one which reduces multiplying with 0 so that should be small as possible.

hidden_dim = Large number didnt work well so I kept in smaller

n_layers = 2 worked fine for me

## Inference on the result

We can see that there are multiple characters that say (somewhat) complete sentences, but it doesn't have to be perfect! It takes quite a while to get good results, and often, we'll have to use a smaller vocabulary (and discard uncommon words), or get more data.  The Seinfeld dataset is about 3.4 MB, which is big enough for our purposes; for script generation we'll want more than 1 MB of text, generally. 
