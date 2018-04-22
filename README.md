# TFHubRetrain

Retraining one of Google's CNN image classification models to new categories using Transfer Learning.
This can be an much faster (in a few minutes) than training from scratch ([Inception V3](https://github.com/EN10/KerasInception) took Google, 2 weeks).

* Based on Tensoflow [Retrain](https://www.tensorflow.org/versions/master/tutorials/image_retraining) (updated 30 March)    
* Originally based on [Tensorflow for Poets](https://github.com/EN10/TensorFlowForPoets)


## Install 
    pip install "tensorflow>=1.7.0"
    pip install tensorflow-hub

## Download Flowers
    cd ~
    curl -LO http://download.tensorflow.org/example_images/flower_photos.tgz
    tar xzf flower_photos.tgz

## Download Code
    mkdir ~/example_code
    cd ~/example_code
    curl -LO https://github.com/tensorflow/hub/raw/master/examples/image_retraining/retrain.py

## Retrain
    python retrain.py --image_dir ~/flower_photos
    
## Classify
    curl -LO https://github.com/tensorflow/tensorflow/raw/master/tensorflow/examples/label_image/label_image.py
    
    python label_image.py \
    --graph=/tmp/output_graph.pb  \
    --image=image.jpg