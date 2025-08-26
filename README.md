Motivation

This implementation follows the original Vision Transformer paper (Dosovitskiy et al., 2020), which demonstrates that:

Transformers can achieve state-of-the-art results in computer vision without convolutional networks
Pure transformer architectures applied to image patches compete with CNNs when properly pre-trained
The approach requires fewer computational resources than comparable CNNs at scale
Key Features

Patch-Based Processing:
Divides images into fixed-size patches (typically 16×16)
Treats patches as sequence tokens (analogous to words in NLP)
Linear Projection:
Flattens patches into 1D vectors
Projects to a latent space using trainable linear layers
Transformer Architecture:
Uses standard Transformer Encoder blocks
Maintains the same architecture as NLP transformers
Implementation Notes

This educational implementation:

Strictly follows the original paper's specifications
Focuses on clarity over optimization
Uses PyTorch's built-in modules where possible
Includes dimension assertions to verify correct shapes
Why Vision Transformers?

As noted in the paper introduction:

"We show that this reliance on CNNs is not necessary and a pure transformer applied directly to sequences of image patches can perform very well on image classification tasks."
The success of ViT suggests that:

The inductive biases in CNNs (translation equivariance, locality) can be learned
Global attention mechanisms may be more efficient than local receptive fields
The same architecture can handle both visual and linguistic tasks


Note: For the implementation of the ViT paper, I also applied the transfer learning technique for two main reasons.
First, training the entire network from scratch would be computationally expensive and impractical on my laptop, so I opted to train only a single linear layer instead.
Second, since the ViT model in PyTorch is pretrained on a large-scale dataset while my dataset is relatively small, using transfer learning allows the model to leverage learned representations and achieve better results — specifically, higher accuracy and lower loss values



the sources I used :
1.PyTorch official webpage - https://pytorch.org
2.Vit paper:https://arxiv.org/pdf/2010.11929
3.Zero to Mastery Learn PyTorch for Deep Learning:https://www.learnpytorch.io