# Coronal Jet detection and localisation

**by [Adrien Joliat](https://github.com/adrienjoliat)**  

**[[Paper]](./MLO_Semester_project_first_sub.pdf)**

Machine Learning model to effectively detect and locate Solar Coronal Jet


## Main Results
First model based on the backbone SwinB and the TransVod Lite architecture to capture coronal jets.

![Results](/Animations/animation_690.gif)



*Note:*
1. This model is trained  with pre-trained weights on COCO dataset.


## Installation

The codebase is built on top of [Deformable DETR](https://github.com/fundamentalvision/Deformable-DETR) and [TransVOD](https://github.com/SJTU-LuHe/TransVOD). An easier installation for Defromable DETR is available here : [Deformable DETR](https://github.com/adrienjoliat/Deformable-DETR)

### Requirements

#### Linux

* Linux, CUDA>=9.2, GCC>=5.4
  
* Python>=3.7

    We recommend you to use Anaconda to create a conda environment:
    ```bash
    conda create -n TransVOD python=3.7 pip
    ```
    Then, activate the environment:
    ```bash
    conda activate TransVOD
    ```
  
* PyTorch>=1.5.1, torchvision>=0.6.1 (following instructions [here](https://pytorch.org/)

    For example, if your CUDA version is 9.2, you could install pytorch and torchvision as following:
    ```bash
    conda install pytorch=1.5.1 torchvision=0.6.1 cudatoolkit=9.2 -c pytorch
    ```
  
* Other requirements
    ```bash
    pip install -r requirements.txt
    ```

* Build MultiScaleDeformableAttention
    ```bash
    cd ./models/ops
    sh ./make.sh
    ```

#### Windows
* Python>=3.7 and Cuda 

    We recommend you to use Anaconda to create a conda environment:
    ```bash
    conda create -n TransVOD python=3.11.7 pip
    ```
    Then, activate the environment:
    ```bash
    conda activate TransVOD
    ```
* Install Pytorch with cuda
    get your cuda version (last line : build_cuda_11.8 means that cuda 11.8 is used)
    ```bash
    nvcc --version
    ```
    then go [here](https://pytorch.org/) and install the required version, for windows and cuda 11.8 we have
    ```bash
    pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
    ```

* Other requirements  
    For all the next steps you need to go into this repository (where Solar_jet_model is saved locally, usually into Documents/Github/Solar_jet_model)
    ```bash
    cd ./Documents/Github/Solar_jet_model
    ```
    ```bash
    pip install -r requirements.txt
    ```

* Build MultiScaleDeformableAttention  
    Make sure you are still in the Solar_jet_model directory and
    now you need to run
    ```bash
    cd ./models/ops
    ```
    
    ```bash
    python setup.py build install
    ```
    At this point you should be good to go, you can go to the verification  
    Note: if there are some problems while installing MultiscaleDeformableAttention maybe delete the sources files for new try installations
    ```bash
    del MultiScaleDeformableAttention.egg-info/SOURCES.txt
    ```

* Verify the installation went well (sometimes even with errors with the build of multiscale it still succeed) so
run the fist cell of **Use_model_with_new_data.ipynb**
   

## Usage
Below, I provide the final selected model:

[DownLoad Link of Google Drive](https://drive.google.com/file/d/1mrA1RFCxGWZrM9RSylFH9PVzlTUHb2Ra/view?usp=sharing)

This model (checkpoint0010.pth) should be put in the exps folder to be used by the notebook available in the main folder, named : **Use_model_with_new_data.ipynb**

## Acknowledgements

This project is based on the following open-source projects. We thank their
authors for making the source code publically available.

* [Deformable DETR](https://github.com/fundamentalvision/Deformable-DETR)
* [TransVOD Lite](https://github.com/qianyuzqy/TransVOD_Lite)