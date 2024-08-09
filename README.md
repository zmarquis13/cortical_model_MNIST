Project:
A neural network implemented in pytorch that aims to roughly simulate the way in which the brain recognizes symbols and determines when it's uncertain about what it's seeing. The network classifies digits in the MNIST dataset.

Overview:
The general idea of the program is to model how humans perform object recognition. Namely, the centralized processing of visual stimulus followed by the passing of that processed information to the inferior temporal cortex, which recognizes objects/symbols. This program simulates that with one network that then passes its output to five disconnected networks, each attempting to recognize a different digit. The output of the whole network is a 1x6 tensor, with outputs for the subnetworks for each of the five digits, and a variable inversely related to the combined output of all five networks. Essentially, if none of the five recognition modules have high output, then there will be high output for the "something else/I'm not sure" variable. This enables an uncertainty not present in traditional neural network classifiers, which have a tendency to confidently place unrelated items into buckets rather than being uncertain. 

Findings:
On MNIST, the network learns to accurately classify known numbers (0-4), and consistently gives the "I'm not sure" output for numbers outside this range and pure static, even though there's no static in its training data. However, after enough training, the network begins to overfit on numbers and starts "recognizing" static. 

Limitations and next steps:
This program extremely roughly estimates how human brains recognize symbols. It's not detailed and is more of a proof of concept than anything. Some next steps would be to try this approach on harder classification tasks and to more accurately simulate the human visual system, potentially by introducing other features and/or processes.

