# Face Recognition with the TensorFlow Object Detection API
![Screenshot](it5.jpg)

### Note: Tensorflow object detection is an accurate machine learning API capable of localizing and identifying multiple objects in a single image. You can use the API for multiple use cases like object detection , person recognition, text detection, etc..
Today, we will see together how tensorflow can recognize people. In this post I'll outline the steps I took to get from a collection of Celebrities images (crawled from the internet)

1. Data Set Download
2. Image Annotation
3. Label Map preparation
4. TF-Record Creation 
5. Pipeline Configuration
6. Training
7. Exporting Graph



## Data set Download

You can crawl celebrity pictures from google images if you don't have a ready Data set. Try to order the data set as bellow:
```ruby
CelebrityDB/
    TomHanks/
        img001.jpg
        tomhanks.jpg
        ...
    WillSmith/
        willsmith1.jpg
        will-smith-pic.jpg
        ...
    ... 
    ```
xxxx
