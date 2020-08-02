## tokuronReport

# Convolutional Radio Modulation Recognition Networks

## Purpose

The prupose of this task is to to implement deep learning in communication system. There are many approaches and also potential applications, and one of them is modulation recognition. Usually, to detect signal modulation, each demodulation is designed to a specific modulation. However, without any specific designs for a particular signal modulation, the neural network should be able to recognize the type of modulation.

## Task Overview

![task_overview](https://user-images.githubusercontent.com/48609334/89123500-ca618780-d50a-11ea-9bea-a82b58013c9e.PNG)

Basically, it’s quite similar with conventional communication system where the transmitter sends signals and the receiver will try to understand what the content of that signals is. But in this task, the transmitters send signals using different modulation methods, and the receiver, a single receiver should be able to classify what kind of modulation types they are. Here, the modulated signals that want to be used are created at GNU radio. The modulated signals also exposed to channel impairment, such as CFO, AWGN, selective fading.. The generated signals were packed so that they can be used easily in typical deep learning environment. And at the receiver end, a CNN model was used to classify the signals.

## Network Architecture
![osheas_model](https://user-images.githubusercontent.com/48609334/89123528-072d7e80-d50b-11ea-93c1-5f9f2fe03746.PNG)

Next is network architecture, this dataset was created by OShe’a, and he published a paper about neural network model using that dataset. When I tried to replicate one of his research, the result was not good. So, I tried several parameters and I selected this parameters to replace the old one. The parameters are also different with the referenced github code.

## Dataset 
![bpsk_data](https://user-images.githubusercontent.com/48609334/89123527-05fc5180-d50b-11ea-9d2a-4b01079eedbe.PNG)
Lets take a look at the dataset. The image up here is the example of modulated signals generated in GNU radio. It’s an open source software, but I’m not really familiar with it so I won’t be able to tell the details. So the version of dataset that I used was RADIOML 2016.10C. The modulated signals were generated at different SNR, starting from -20 until +18 dB. So, there are twenty variation of SNR for one type of modulation. The problem I had at the first time was, no detail about the dataset, only know about the vector representation of it. After carefully check the content, know it is become clear. For example in each SNR there I/Q signals, as we can here in the blue and red line.  And also, in each SNR, there are several examples. In BPSK, there are 1247 examples. What I show here is only one example.

Here is more information about the dataset
DEEPSIG DATASET: RADIOML 2016.04C (https://www.deepsig.ai/datasets)

## Output



