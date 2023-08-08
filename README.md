# Image Super-Resolution Using ESRGAN


 <div align="center">
    <a href="https://colab.research.google.com/github/reshalfahsi/image-super-resolution/blob/master/ImageSuperResolution.ipynb"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="colab"></a>
    <br />
 </div>

Image super-resolution attempts to produce pixels within the image to fill the lack of information due to its low-resolution nature. Hence, it yields a higher-resolution image. One approach to this problem is via generative networks, e.g., ESRGAN (Enhanced Super-Resolution Generative Adversarial Network). This type of GAN is built explicitly for image super-resolution by considering several losses, i.e., contextual loss (focus on the distribution of the feature), perceptual loss (pixel-wise loss), and adversarial loss. These three losses are utilized for the generator loss. These three losses are utilized for the generator loss. On the contrary, the discriminator loss only takes into account the adversarial loss. There are two stages during training: (1) train only the generator on the perceptual loss, and (2) train the generator and discriminator based on those, as mentioned earlier. The model is trained and evaluated on the BSDS500 dataset. The final result of the predicted high-resolution image is subjected to the sharpening method by subtracting the image with the laplacian of the image.


## Experiment


This [link](https://github.com/reshalfahsi/image-super-resolution/blob/master/ImageSuperResolution.ipynb) provides the code for the experiments.


## Result

## Quantitative Result

Quantitatively, the performance of ESRGAN after training with 420 epochs is presented as follows:

Metrics | Test Dataset |
------------ | ------------- |
PSNR | 22.587 |
SSIM | 0.586 |
MAE | 0.049 |


## Evaluation Metrics Curve

<p align="center"> <img src="https://github.com/reshalfahsi/image-super-resolution/blob/master/assets/loss_curve.png" alt="loss_curve" > <br /> Generator and discriminator loss curves on the train setss. </p>

<p align="center"> <img src="https://github.com/reshalfahsi/image-super-resolution/blob/master/assets/psnr_curve.png" alt="psnr_curve" > <br /> PSNR curve on the train set and the validation set. </p>

<p align="center"> <img src="https://github.com/reshalfahsi/image-super-resolution/blob/master/assets/ssim_curve.png" alt="ssim_curve" > <br /> SSIM curve on the train set and the validation set. </p>

<p align="center"> <img src="https://github.com/reshalfahsi/image-super-resolution/blob/master/assets/mae_curve.png" alt="mae_curve" > <br /> MAE curve on the train set and the validation set. </p>


## Qualitative Result

The qualitative results of the model are shown below.

<p align="center"> <img src="https://github.com/reshalfahsi/image-super-resolution/blob/master/assets/hires_qualitative_00.png" alt="hires_qualitative_00" > <img src="https://github.com/reshalfahsi/image-super-resolution/blob/master/assets/bicubic_qualitative_00.png" alt="bicubic_qualitative_00" > <img src="https://github.com/reshalfahsi/image-super-resolution/blob/master/assets/esrgan_qualitative_00.png" alt="esrgan_qualitative_00" > <br /> <img src="https://github.com/reshalfahsi/image-super-resolution/blob/master/assets/hires_qualitative_01.png" alt="hires_qualitative_01" > <img src="https://github.com/reshalfahsi/image-super-resolution/blob/master/assets/bicubic_qualitative_01.png" alt="bicubic_qualitative_01" > <img src="https://github.com/reshalfahsi/image-super-resolution/blob/master/assets/esrgan_qualitative_01.png" alt="esrgan_qualitative_01" > <br /> <img src="https://github.com/reshalfahsi/image-super-resolution/blob/master/assets/hires_qualitative_02.png" alt="hires_qualitative_02" > <img src="https://github.com/reshalfahsi/image-super-resolution/blob/master/assets/bicubic_qualitative_02.png" alt="bicubic_qualitative_02" > <img src="https://github.com/reshalfahsi/image-super-resolution/blob/master/assets/esrgan_qualitative_02.png" alt="esrgan_qualitative_02" > <br /> Qualitative comparison between the reference high-resolution images (left column), high-resolution images via bicubic interpolation (middle column), and predicted high-resolution images through ESRGAN (right column). </p>


## Credit

- [ESRGAN: Enhanced Super-Resolution Generative Adversarial Networks](https://arxiv.org/pdf/1809.00219.pdf)
- [Berkeley Segmentation Data Set and Benchmarks 500 (BSDS500)](https://github.com/BIDS/BSDS500)
- [Image Super-Resolution using an Efficient Sub-Pixel CNN](https://keras.io/examples/vision/super_resolution_sub_pixel/)
- [PyTorch-GAN](https://github.com/eriklindernoren/PyTorch-GAN)
- [PyTorch Lightning](https://lightning.ai/docs/pytorch/latest/)
