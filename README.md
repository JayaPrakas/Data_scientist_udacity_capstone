# Dod Breed Classifier

Blog post corresponding to this notebook can be read [here](https://jayaprakashks.medium.com/dog-breed-classification-from-udacity-4e4be4f918b0)

## Table of contents

- [Installation](#installation)
- [Project Description](#Project-Description)
- [Project motivation](#project-motivation)
- [Interacting with this project](#Interacting-with-this-project)
- [File descriptions](#File-descriptions)
- [Instructions](#Instructions)
- [Results](#Results)
- [Acknowledgements](#Acknowledgements)
- [License](#License)


## Installation

This notebook runs on **anaconda distribution** with **python**. The following are used along with anaconda distribution.

- keras
- PIL
- random
- glob
- sklearn
- cv2

## Project Description

 This project, given an image of a dog, will identify an estimate of the canine’s breed.  If supplied an image of a human, the code will identify the resembling dog breed.
 Details of input data used is given below in instructions.

## Project motivation

As a requirement for the nanodegree [become a data scientist](https://www.udacity.com/course/data-scientist-nanodegree--nd025) of [Udacity](https://www.udacity.com/).

## Interacting with this project

- To interact, clone the repo: `git clone https://github.com/JayaPrakas/Data_scientist_udacity_capstone.git` or fork this repository

## File descriptions

With this download you'll find the following files.

```text
    
- dog_app.ipynb 
- README.md
- LICENSE
- report.html 
- image1
- image2
- image3
- image4
- image5
- image6

```

## Instructions

This project is built with convolutional models from keras, ResNet50 and InceptionV3 models and our expected solution is breed name of dog if it is a dog, resembling breed if it is human and not a human message if it is neither a dog or human. Here we use accuracy metrics to evaluate our models.

To get started we must follow instructions below.

1. Clone the repository and navigate to the downloaded folder.
```	
git clone https://github.com/JayaPrakas/Data_scientist_udacity_capstone.git
```

2. Download the [dog dataset](https://s3-us-west-1.amazonaws.com/udacity-aind/dog-project/dogImages.zip).  Unzip the folder and place it in the repo, at location `path/to/dog-project/dogImages`. 

3. Download the [human dataset](https://s3-us-west-1.amazonaws.com/udacity-aind/dog-project/lfw.zip).  Unzip the folder and place it in the repo, at location `path/to/dog-project/lfw`.  If you are using a Windows machine, you are encouraged to use [7zip](http://www.7-zip.org/) to extract the folder. 

4. Donwload the [VGG-16 bottleneck features](https://s3-us-west-1.amazonaws.com/udacity-aind/dog-project/DogVGG16Data.npz) for the dog dataset.  Place it in the repo, at location `path/to/dog-project/bottleneck_features`.

5. (Optional) __If you plan to install TensorFlow with GPU support on your local machine__, follow [the guide](https://www.tensorflow.org/install/) to install the necessary NVIDIA software on your system.  If you are using an EC2 GPU instance, you can skip this step.

6. (Optional) **If you are running the project on your local machine (and not using AWS)**, create (and activate) a new environment.

	- __Linux__ (to install with __GPU support__, change `requirements/dog-linux.yml` to `requirements/dog-linux-gpu.yml`): 
	```
	conda env create -f requirements/dog-linux.yml
	source activate dog-project
	```  
	- __Mac__ (to install with __GPU support__, change `requirements/dog-mac.yml` to `requirements/dog-mac-gpu.yml`): 
	```
	conda env create -f requirements/dog-mac.yml
	source activate dog-project
	```  
	**NOTE:** Some Mac users may need to install a different version of OpenCV
	```
	conda install --channel https://conda.anaconda.org/menpo opencv3
	```
	- __Windows__ (to install with __GPU support__, change `requirements/dog-windows.yml` to `requirements/dog-windows-gpu.yml`):  
	```
	conda env create -f requirements/dog-windows.yml
	activate dog-project
	```

7. (Optional) **If you are running the project on your local machine (and not using AWS)** and Step 6 throws errors, try this __alternative__ step to create your environment.

	- __Linux__ or __Mac__ (to install with __GPU support__, change `requirements/requirements.txt` to `requirements/requirements-gpu.txt`): 
	```
	conda create --name dog-project python=3.5
	source activate dog-project
	pip install -r requirements/requirements.txt
	```
	**NOTE:** Some Mac users may need to install a different version of OpenCV
	```
	conda install --channel https://conda.anaconda.org/menpo opencv3
	```
	- __Windows__ (to install with __GPU support__, change `requirements/requirements.txt` to `requirements/requirements-gpu.txt`):  
	```
	conda create --name dog-project python=3.5
	activate dog-project
	pip install -r requirements/requirements.txt
	```
	
8. (Optional) **If you are using AWS**, install Tensorflow.
```
sudo python3 -m pip install -r requirements/requirements-gpu.txt
```
	
9. Switch [Keras backend](https://keras.io/backend/) to TensorFlow.
	- __Linux__ or __Mac__: 
		```
		KERAS_BACKEND=tensorflow python -c "from keras import backend"
		```
	- __Windows__: 
		```
		set KERAS_BACKEND=tensorflow
		python -c "from keras import backend"
		```

10. (Optional) **If you are running the project on your local machine (and not using AWS)**, create an [IPython kernel](http://ipython.readthedocs.io/en/stable/install/kernel_install.html) for the `dog-project` environment. 
```
python -m ipykernel install --user --name dog-project --display-name "dog-project"
```

11. Open the notebook.
```
jupyter notebook dog_app.ipynb
```

12. (Optional) **If you are running the project on your local machine (and not using AWS)**, before running code, change the kernel to match the dog-project environment by using the drop-down menu (**Kernel > Change kernel > dog-project**). Then, follow the instructions in the notebook.

# Results

First we took images data of dogs and humans and we pre-processed it to fixed size and then we built simple keras model with few convolutional layers and filters which gave less accuracy

Next we used our data with VGG model using transfer learning which gave more accuracy.

Finally we used Inception model which further increased accuracy of model and thus what I find interesting is concept of Inception model which is deep and challenging and exciting to work with as it gives lot of ease for classification of image.

Results are when supplied with image of dog, it results it is a dog and predicted dog breed label, if image is human, it results as it is human and resembling predicted breed name and if it is other than dog and human, it results as it is not both and resembling breed name is shown.

# Acknowledgements

Thanks to [Udacity](https://www.udacity.com/) for data, starter code and instructions

image1 - <span>Photo by <a href="https://unsplash.com/@e_d_g_a_r?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Edgar</a> on <a href="https://unsplash.com/s/photos/animals?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>

image4 - <span>Photo by <a href="https://unsplash.com/@gxldy?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Ash Goldsbrough</a> on <a href="https://unsplash.com/s/photos/dogs?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>

image3 - <span>Photo by <a href="https://unsplash.com/@skucinic9?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Sven Kucinic</a> on <a href="https://unsplash.com/s/photos/dogs?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>

image2 - <span>Photo by <a href="https://unsplash.com/@camilofierro14?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Camilo Fierro</a> on <a href="https://unsplash.com/s/photos/dogs?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>


## License

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

