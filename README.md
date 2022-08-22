# Hypercolumns for Semantic Segmentation

This project implements the hypercolumn idea for semantic segmentation. It uses two deep learning architectures and hypercolumns to classify pixels from images. For further information please see the pdf paper.


## Usage

There are three major stages that need to be run. First, extraction of initial hypercolumns to pre-train the classifier. Second, the pre-training of the classifier with the hypercolumns extracted in step 1. Third the complete training of the classifier with all pixels of every image. The cnn variable (value: 'vgg' or 'sqn') defines the CNN that will be used for obtaining the features. It has to be the same for the three stages. 
To use the run_model function, it can have a different cnn value as long as the already trained complete model exists.

The root_dir defines the root for the folder that contains the notebook and the dataset. The root folder is called 'code' and inside of it, the following structure should be followed:

```
code/
    notebook.ipynb
    data/
        VOCdevkit/
    hypercolumn_samples/
        pre-trained/
            sqn/
            vgg/
    images/
        imgs/
        masks/
        test/
    models/
        trained/
            sqn/
            vgg/
```

Each folder contains the following.

**data:** contains de dataset. After downloading the VOC data set, it should be extracted inside data. It will extract a folder named VOCdevkit along with other subfolders. Those subfolders should not be changed.

**hypercolumn_samples:** This folder contains the saved feature maps extracted in the first stage. The file will be saved in this folder, but after the first time, it should be copied into sqn/ or vgg/ to avoid performing the same step in the future.

**images:** This folder contains the images used for training the complete model. It also contains the results (masks and test images)

**models:** This folder contains the trained models. As in hypercolumn_samples folder, once the model has been trained, it should be copied into sqn/ or vgg/ to avoid re training in the future.

## Contributing
Pull requests are welcome.

## License
[MIT](https://choosealicense.com/licenses/mit/)