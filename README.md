## MicroNet_ImageNet_Lv_DQ
## Introduction
This repo contains the code for the model compression chanllenge Hosted at [NeurIPS 2019](https://micronet-challenge.github.io/scoring_and_submission.html) regarding the ImageNet classification track.

## Backbone model and compression methods
The compression method is mainly based on the paper [NES](https://openreview.net/forum?id=HyxjOyrKvr) where we apply the transformation on the fully connected 1x1 convolution layers with a compression ratio of 2x. Besides, we also apply group convolution on SE blocks to further reduce the parameter number and the computation complexity. During the whole quantization process, no quantization is performed and no specialized hardware support is needed.

The resulting model specification is as below:

Parameter number: 3.92M
FLOPs: 460M

As a result, we are eligible to use the free 16-bit quantization gift and thus the model parameter number is reduded to 1.55M and the FLOPs is reduced to 460M * 0.75 as all the multiplications are as quantized to 16 bits also.

Thus, the total score is calculated as 1.96M/6.9M + 345M/1170M = 0.578
