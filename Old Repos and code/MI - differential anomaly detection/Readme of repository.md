# Differential Anomaly Detection

This repository contains code for detecting manipulated face images using a differential approach. The project is a joint work between Mathias Ibsen and Lázaro Janier González-Soler.
The work received the best paper award at WIFS'21.
The repository contains **code for getting detection score using a pre-trained VAE model with a subtraction feature extraction**, coressponding to the best model in our paper. Results vary slightly compared to the results in the paper, however the uploaded model produce very similar results to those in Table 1 of the paper for the VAE model. 
Reasons for differences is that the original model could not be probably saved due to issues in pyod, this has since been fixed in the pyod library which means that a new model could be trained and saved.

## Getting started
The following is a brief description of how to get started.

### Training and testing data
In the paper, the [[Face Recognition methods#ArcFace|ArcFace]] face recognition system was used using the code from the [insightface repository](https://github.com/deepinsight/insightface). 
Other face recognition systems, e.g. AdaFace can be used instead if preferred. 
To use the ArcFace code included in this repository, **you will need a pretrained resnet100 model:**
Download the zip file and extract it in /insightface/models/

* Link: https://cloud.h-da.de/s/gznLT9fszRw5eQM
* Password: vCexb9f43NQ

Make sure the path to the unzipped directory is: *<path_to_git_repo>/insightface/models/model-r100-ii*

Additionally, you will need a pretrained model from the detector:

* Link: https://cloud.h-da.de/s/Zf4fKYkCqY9nFX9
* Password: Gxd3MmSRxsa

This file needs to be saved as follows: <HOME_DIR>/.insightface/models/retinaface_mnet025_v2
where <HOME_DIR> is the path to the home directory of the user that runs the code

The InsightFace implementation of ArcFace (original) is not the most well-documented FR system but it performs rather good. It is possible to replace this system with others as stated above, e.g. AdaFace which is much easier to use. In this case you need to replace the *extract_embedding* function in *detection.py*. In that case you might want to retrain the model to perform best which you might want to do in any case to suit your needs.

For information about the training and testing data please refer to the description in the paper.

### Installation

* Clone this repository
* Install dependencies from environment.yml

Depending on the OS used the installation from the .yml might fail. If this is the case you can try to manually install the neccesary packages:
```shell
conda create -n diff-anomaly-det python=3.7
conda activate diff-anomaly-det
pip install pyod
pip install tensorflow
pip install mxnet
pip install opencv-python
pip install tqdm
pip install scikit-image
```

### Usage
Modify training and testing scripts to suit your needs and then train and test your models.

**Testing** 
You can use the following script to get the differential deteciton score from two images:
Note: A saved VAE model is stored in /saved_vae_model
It is important you point to the directory and not a specific file, as the VAE model is stored in three files which are currently loaded automatically
```shell
python detection.py --model_dir <dir_saved_vae_model> --reference_p <path_reference_image> --probe_p <path_probe_image>
```

**Training**
How to train the network will depend on the specific training database used and its structure. However the following general steps can be followed:

* Extract embeddings from all probe and reference images of your training data set. 
* Combine the embeddings using the *combine_feature_embeddings* method from the *feature_combination* directory
* Train an anomaly detection models. If you use *pyod* you can refer to the documentation in https://github.com/yzhao062/pyod .

## Contributing
Please contact Mathias before making changes to this repository.

## Acknowledgement

If you use this detector, please cite our work:

```
@inproceedings{Ibsen-DifferentialAnomalyDetectionForFacialImages-WIFS-2021,
 Author = {M. Ibsen and L. J. Gonzalez-Soler and C. Rathgeb and P. Drozdowski and M. Gomez-Barrero and C. Busch},
 Booktitle = {{IEEE} Intl. Workshop on Information Forensics and Security ({WIFS})},
 Pages = {1--6},
 Title = {Differential Anomaly Detection for Facial Images},
 Year = {2021}
}
```

## Contact
For inquiries please contact us:

* https://dasec.h-da.de/staff/mathias-ibsen/
* https://dasec.h-da.de/staff/janier-soler/
