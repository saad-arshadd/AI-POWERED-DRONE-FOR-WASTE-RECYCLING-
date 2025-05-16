<p align="center">
<img src="https://raw.githubusercontent.com/wiki/pedropro/TACO/images/logonav.png" width="25%"/>
</p>

TACO is a growing image dataset of waste in the wild. It contains images of litter taken under
diverse environments: woods, roads and beaches. These images are manually labeled and segmented
according to a hierarchical taxonomy to train and evaluate object detection algorithms. Currently,
images are hosted on Flickr and we have a server that is collecting more images and
annotations @ [tacodataset.org](http://tacodataset.org)


<div align="center">
  <div class="column">
    <img src="https://raw.githubusercontent.com/wiki/pedropro/TACO/images/1.png" width="17%" hspace="3">
    <img src="https://raw.githubusercontent.com/wiki/pedropro/TACO/images/2.png" width="17%" hspace="3">
    <img src="https://raw.githubusercontent.com/wiki/pedropro/TACO/images/3.png" width="17%" hspace="3">
    <img src="https://raw.githubusercontent.com/wiki/pedropro/TACO/images/4.png" width="17%" hspace="3">
    <img src="https://raw.githubusercontent.com/wiki/pedropro/TACO/images/5.png" width="17%" hspace="3">
  </div>
</div>
</br>

For convenience, annotations are provided in COCO format. Check the metadata here:
http://cocodataset.org/#format-data

TACO is still relatively small, but it is growing. Stay tuned!





# Getting started

### Requirements 

To install the required python packages simply type
```
pip3 install -r requirements.txt
```
Additionaly, to use ``demo.pynb``, you will also need [coco python api](https://github.com/cocodataset/cocoapi). You can get this using
```
pip3 install git+https://github.com/philferriere/cocoapi.git#subdirectory=PythonAPI
```



**Unlabeled data**

A list of URLs for both unlabeled and labeled images is now also provided in `data/all_image_urls.csv`.
Each image contains one URL for each original image (second column) and one URL for a VGA-resized version (first column)
for images hosted by Flickr. If you decide to annotate these images using other tools, please make them public and contact us so we can keep track.

**Unofficial data**

Annotations submitted via our website are added weekly to `data/annotations_unofficial.json`. These have not yet been been reviewed by us -- some may be inaccurate or have poor segmentations. 
You can use the same command to download the respective images:
```
python3 download.py --dataset_path ./data/annotations_unofficial.json
```

.

As you can see [here](http://tacodataset.org/stats), most of the original classes of TACO have very few annotations, therefore these must be either left out or merged together. Depending on the problem, ``detector/taco_config`` contains several class maps to target classes, which maintain the most dominant classes, e.g., Can, Bottles and Plastic bags. Feel free to make your own classes.

<p align="center">
<img src="https://raw.githubusercontent.com/wiki/pedropro/TACO/images/teaser.gif" width="75%"/></p>
