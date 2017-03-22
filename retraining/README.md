# Tensorflow-Examples

## References
* https://www.tensorflow.org/tutorials/image_retraining
* Flower images: http://download.tensorflow.org/example_images/flower_photos.tgz
* TensorFlow for Poets: https://codelabs.developers.google.com/codelabs/tensorflow-for-poets/index.html

## Images
* curl -O http://download.tensorflow.org/example_images/flower_photos.tgz

## Dependencies
sudo apt-get update && sudo apt-get -y upgrade
sudo apt-get install -y python-numpy

## Extra Dependencies
sudo apt-get install -y build-essential git python-dev python-pip python-numpy python-pandas python-sklearn libfreetype6-dev libxft-dev libncurses-dev libopenblas-dev gfortran python-matplotlib libblas-dev liblapack-dev libatlas-base-dev python-dev python-pydot unzip python-numpy swig python-pandas python-sklearn unzip wget pkg-config zip g++ zlib1g-dev libcurl3-dev libcupti-dev

## Upgrade pip
sudo pip install -U pip


## Install Java
sudo add-apt-repository -y ppa:webupd8team/java
sudo apt-get update
echo debconf shared/accepted-oracle-license-v1-1 select true | sudo debconf-set-selections
echo debconf shared/accepted-oracle-license-v1-1 seen true | sudo debconf-set-selections
sudo apt-get install -y oracle-java8-installer


## Install Bazel
echo "deb [arch=amd64] http://storage.googleapis.com/bazel-apt stable jdk1.8" | sudo tee /etc/apt/sources.list.d/bazel.list
curl https://storage.googleapis.com/bazel-apt/doc/apt-key.pub.gpg | sudo apt-key add -
sudo apt-get update && sudo apt-get install -y bazel

## Installation
wget https://github.com/tensorflow/tensorflow/archive/v1.0.1.tar.gz
./configure
bazel build tensorflow/examples/image_retraining:retrain
bazel-bin/tensorflow/examples/image_retraining/retrain --image_dir ~/flower_photos
