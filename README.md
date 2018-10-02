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



## 1. Data set Download

You can crawl celebrity pictures from google images if you don't have a ready Data set. Try to order the data set as bellow:

```

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
## 2. Image Annotation
you can annotate the images using an annotation tool like labelImg. But it will take a lot of time. That's why i created a script to generate xml files(exactly like PASCAL VOC). I used opencv to detect faces but, you can change it with any other tool( i recommend dlib or a neural network face detection model which are much more accurate than opencv).
#### Use [python annotation script to generate xml annotations](annotation.py)
The Xml files should look like :
```xml
<annotation verified="yes">
    <folder>celebrityDB</folder><filename>1d9k49.jpeg</filename>
    <path>/media/emna/datapartition/tutos/celebrityDB/dewayneJohnson/1d9k49.jpeg</path>
    <source>
        <database>Emna Amor</database>
    </source>
    <size>
        <width>104</width>
        <height>142</height>
        <depth>3</depth>
    </size>
    <segmented>0</segmented>
    <object>
        <name>dewayneJohnson</name>
        <pose>Unspecified</pose>
        <truncated>0</truncated>
        <difficult>0</difficult>
        <bndbox>
            <xmin>2</xmin>
            <ymin>34</ymin>
            <xmax>133</xmax>
            <ymax>99</ymax>
        </bndbox>
    </object>
</annotation>
```
## 3. Label Map preparation
After annotating the pictures we have, We need to generate a csv file containing all pictures details / classes. 
 #### Use  [python xml to csv script to generate the csv file](xml_to_csv.py)
The csv File should look like this:
| filename | width | height | class |xmin | ymin |xmax | ymax |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1jth1461.jpeg | 76 | 105 | kimKardashian |10 | 30 |89 | 59 |
| wenn33850496.jpg | 470 | 654 | AndySerkis |52 | 142 |494 | 352 |



| Command | Description | Description | 
| --- | --- | --- |
| git status | List all new or modified files | List all new or modified files |
| git diff | Show file differences that haven't been staged | List all new or modified files |
