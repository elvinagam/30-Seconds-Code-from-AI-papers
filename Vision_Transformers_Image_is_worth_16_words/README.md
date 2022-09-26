ViT - [The State of the Art in Computer Vision](https://arxiv.org/abs/2010.11929)

While Transformers replaced RNNs in NLP right away, it tooks time for Computer Vision Applications to make place for multi-head attentions. In this paper, Google Research showed a way to remove the absolute reliance on CNNs in CV, by achieving the state-of-the-art performance on ImageNet as well with substantianlly fewer computational resources. 

Self-attention-based arhitectures, in other words, Tranformers: 1. pre-train on a large corpus, 2. fine-tune on a smaller task-spacific dataset.
Before this paper, there have been multiple works where CNN-like NNs have been combined with self-attention models, however, none had yet scaled efficiently on modern hardware accelerators. Therefore, classical ResNet was still leading before ViT.

Here, standard transformers approach is directly applied into images (encoder). Each image is divided into patches (patches + positional embeddings) and each patch is dealt just like tokens (words) in NLP transformers. 

Naive application of transformers into images would be each pixel attenting into the other one. However, this would have been extremely resource-cosnuming. Several approaches have been made such as applying attention into local neighbourhood only rather than globally. Another one is, extracting image patches (2x2, just like in ViT), and applying full attention in that. What Google adds is - Larger Scale Pre-training and also handling medium & higher resolution images.  

Tested on: ImageNet - 1k classes, 1.3M images; ImageNet21K - 21K classes, 14M images; JFT 18K classes, 303M images
Trained on: Adam optimizer; 4096 batch size, weight decay of 0.1
Regularization: dropout, weight-decay, label-smoothing (penalizing hard labels, leaving more space for soft labels to prevent over-confidence and make more generalizable.

Usually, vision transformers are better at millions of images. Therefore, if your dataset is not in the margin of millions, you still better stick to the regular ResNet or EfficientNet architectures.

