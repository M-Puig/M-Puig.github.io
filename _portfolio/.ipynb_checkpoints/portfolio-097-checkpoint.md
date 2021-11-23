---
title: "Seq2Seq Chatbot - 2021"
excerpt: "<img src='/images/chatbot.svg' width=100>"
collection: portfolio
---

A Seq2Seq neural network is a model that will peform sequence transformation, that is produce a sequence given an input sequence. It was first developed by google for machine translation, the input would be a text from the source language, and the output the translated version in the target language. It can however also be used to create a chatbot, the output sequence being a response to a chat line given as an input.

This is a relatively naive approach as the network will not be able to have any kind of memory, and thus can't produced continued conversation by keepng the context in mind. It is however able to produce very pertinent and convincing answers and can be quite fun!

The dataset I used to train the network is the [Cornell Movie-Dialogs Corpus](https://www.cs.cornell.edu/~cristian/Cornell_Movie-Dialogs_Corpus), that contains over 200 000 conversational exchanges between 10 000 pairs of movie characters form 9 000 movies. Using such a large unfiltered dataset from movie dialogs makes the bot quite dramatic, and also possibly inappropriate, it is an interesting demonstration of bias based on the training dataset for neural network. It echoes [microsoft's twitter chatbot Tay](https://www.theguardian.com/technology/2016/mar/24/tay-microsofts-ai-chatbot-gets-a-crash-course-in-racism-from-twitter?CMP=twt_a-technology_b-gdntech) that was launched in 2016, learning from the answers from users of the website, and who quickly started publishing inflamatory tweets based on those interactions. The nature and bias of the dataset are important things to look for when training a network!


The network contains and encoder and a decoder. The base element of both these parts is recurrent neural networks, here Gated Recurrent Units. For more details,  on seq2seq networks, using the basic method or upgrading it with the attention mecanism, you can check on [Lena Voita's website](https://lena-voita.github.io/nlp_course/seq2seq_and_attention).

Here is an example of a conversation with the upgraded version of the network, using attention, and doing a greedy search to produce an output sentence.

<img src='/images/skynet.png' height=1500>