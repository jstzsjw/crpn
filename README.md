# Corner-based Region Proposal Network

CRPN is a two-stage detection framework for multi-oriented scene text. The code is modified from [py-faster-rcnn](https://github.com/rbgirshick/py-faster-rcnn). 


### Requirements

1. Build Caffe and pycaffe (see: [Caffe installation instructions](http://caffe.berkeleyvision.org/installation.html))
    ```
    # In your Makefile.config, make sure to have this line uncommented
    WITH_PYTHON_LAYER := 1
    # Unrelatedly, it's also recommended that you use CUDNN
    USE_CUDNN := 1
    ```

2. Build the Cython modules
    ```
    cd $CRPN_ROOT/lib
    make
    ```

3. installation for training and testing models on PASCAL VOC dataset
    ```
    Create symlinks for YOUR dataset
    cd $CRPN_ROOT/data
    ln -s [dataset_path] VOCdevkit
    ```

4. Download pre-trained ImageNet VGG-16 models
    ```
    VGG16 comes from the [Caffe Model Zoo](https://github.com/BVLC/caffe/wiki/Model-Zoo)
    ```
5. Train with YOUR dataset
    ```
    cd $CRPN_ROOT
    ./experiments/scripts/train.sh [NET] [MODEL] [DATASET] [ITER_NUM]
    # NET is the network arch to use, only {vgg16} in this implemention
    # MODEL is the pre-trained model you want to use it to initial your network weights
    # DATASET points to your dataset
    # IETR_NUM 
    ```
