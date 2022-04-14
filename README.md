# U-Net-for-DRIVE

The goal of this project is to implement U-Net from scratch and apply it to [DRIVE Dataset](https://www.kaggle.com/datasets/andrewmvd/drive-digital-retinal-images-for-vessel-extraction) for Retinal Blood Vessel Segmentation. 

UNet was introduced in 2015, and is one of the popularly used approaches in [semantic segmentations](https://www.google.com/search?q=what+is+semantic+segmentation&sxsrf=APq-WBssmM-Xy-bnHF2CG1hPcDCx_ONyaQ%3A1649907722396&source=hp&ei=CphXYpWHFoaA-Aa18JOQAg&iflsig=AHkkrS4AAAAAYlemGvXuLKGubs2HhokOSwItoGr8WP0A&ved=0ahUKEwiVtNCd0ZL3AhUGAN4KHTX4BCIQ4dUDCAc&uact=5&oq=what+is+semantic+segmentation&gs_lcp=Cgdnd3Mtd2l6EAMyBQgAEIAEMgUIABCABDIFCAAQgAQyBQgAEIAEMgYIABAWEB4yBggAEBYQHjIGCAAQFhAeMgYIABAWEB5QAFgAYNgCaABwAHgAgAG7AYgBuwGSAQMwLjGYAQCgAQKgAQE&sclient=gws-wiz). The architecture has four main components. 

1. **Encoder :** Acts as the feature extractor and learns an abstract representation of the input image through a sequence of the encoder blocks.
2. **Skip connections :** Provides additional information that helps the decoder to generate better semantic features.
3. **Bridge :** Connects the encoder and the decoder network and completes the flow of information. It consists of two 3×3 convolutions, where each convolution is followed by a ReLU activation function.
4. **Decoder :** It is used to take the abstract representation and generate a semantic segmentation mask. The decoder block starts with a 2×2 transpose convolution.

Original paper : [U-Net: Convolutional Networks for Biomedical Image Segmentation](https://arxiv.org/abs/1505.04597)

![](https://i.imgur.com/KuBHBba.png)

### About the data
The dataset contains images and their corresponding masked versions of retinal blood vessels from patients with various conditions.
Here is an example:

| Image                                    | Mask                                 | 1st Manual                           |
| ---------------------------------------- | ------------------------------------ | ------------------------------------ |
| ![](https://i.imgur.com/VY8WIVX.png)     | ![](https://i.imgur.com/sEQrO4f.gif) | ![](https://i.imgur.com/n3Y1BiL.gif) |

The U-Net model is implemented in the file `model.py`

### Folder Structure 
```
E:.
├───DRIVE
│   ├───test
│   │   ├───images
│   │   └───mask
│   └───training
│       ├───1st_manual
│       ├───images
│       └───mask
├───results
└───saved_files
    ├───test
    │   ├───image
    │   └───mask
    └───train
        ├───image
        └───mask
```
## Results
![](https://i.imgur.com/sXylG1B.png)
![](https://i.imgur.com/XrQlhrm.png)
![](https://i.imgur.com/3XtyOJv.png)

More results can be found on `/results` folder. 
