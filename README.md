# Google Inception V3 for BLVC/Caffe

## Introduction
I've edited the train_val.prototxt and deploy.prototxt to make the network compatible with BVLC/caffe. I've tested it with both the master and windows branches of BVLC/caffe.

The original implementation is incompatible with BLCV/caffe because of the difference in implementation of the batch normalization layer in Nvidia/caffe and BVLC/caffe. I've added BVLC/caffe compliant batchnorm and scale layers and turned off global_stats while in the TEST phase and turned them on in the TRAIN phase

## Training on custom set

I have trained this model on custom subset of 12 categories for 24000 iterations using [BVLC/caffe](https://github.com/BVLC/caffe) :  

```
I0111 19:03:30.063627  2913 solver.cpp:337] Iteration 24000, Testing net (#0)
I0111 19:13:25.094672  2913 solver.cpp:404]     Test net output #0: acc/top-1 = 0.971833
I0111 19:13:25.094760  2913 solver.cpp:404]     Test net output #1: acc/top-5 = 0.995267
I0111 19:13:25.094769  2913 solver.cpp:404]     Test net output #2: loss = 0.115525 (* 1 = 0.115525 loss)

```
