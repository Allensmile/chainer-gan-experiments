# Chainer-GANs

Various GANs with Chainer
### Requirement
* Chainer==1.24.0
* OpenCV

### List
* DCGAN: [Unsupervised Representation Learning with Deep Convolutional Generative Adversarial Networks](https://arxiv.org/abs/1511.06434)
* ACGAN: [Conditional Image Synthesis With Auxiliary Classifier GANs](https://arxiv.org/abs/1610.09585)
* LSGAN: [Least Squares Generative Adversarial Networks](https://arxiv.org/abs/1611.04076)
* WGAN: [Wasserstein GAN](https://arxiv.org/abs/1701.07875)
* WGAN-GP: [Improved Training of Wasserstein GANs](https://arxiv.org/abs/1704.00028)
* DRAGAN: [How to Train Your DRAGAN](https://arxiv.org/abs/1705.07215)
* CramerGAN: [The Cramer Distance as a Solution to Biased Wasserstein Gradients](https://arxiv.org/abs/1705.10743)
* αGAN: [Variational Approaches for Auto-Encoding Generative Adversarial Networks](https://arxiv.org/abs/1706.04987)

By default, all models are tested on the CelabA dataset. You can find the training results in corresponding folders.

### Gradient Penalty

Most of recent GANs (WGAN-GP, CramerGAN, DRAGAN) contains the gradient norm regularization, this has been proved as a way to stabilize GAN training.

The current version of Chainer do not support high order derivatives, a solution is to manually implement the backward procedure with auto-differentiable chainer.functions. (Refer WGAN-GP codes for the details.)

* L.Linear, L.Convolution2D, L.Deconvolution2D, F.leaky_relu, F.relu, F.sigmoid, F.tanh, L.LayerNormalization is implemented.
* Some GAN papers suggest to use LayerNormalization instead on BatchNormalization in the discriminator in the case of gradient penalty.


**Special thanks to [mattya](https://github.com/mattya) for the idea and reference codes.**

### Samples

Some DRAGAN results:

![DRAGAN_2d_faces](https://raw.githubusercontent.com/Aixile/chainer-gan-experiments/master/dragan/results/2dcharafaces.jpg)

![DRAGAN_2d_Analogy](https://raw.githubusercontent.com/Aixile/chainer-gan-experiments/master/dragan/results/2dcharafaces_analogy.jpg)
