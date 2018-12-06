# Hotels-50K
The Hotels-50K dataset was created to encourage work in hotel recognition, the task of identifying the hotel in images taken in hotel rooms. This task is particularly important as many photographs of human trafficking victims are captured in hotel rooms, and identifying which hotels the victims were photographed in is a top priority for trafficking investigators.

The Hotels-50K dataset (introduced in https://todo.com/paper.pdf) consists of over 1 million images from 50,000 different hotels around the world. These images come from both travel websites, as well as the TraffickCam mobile application, which allows every day travelers to submit images of their hotel room in order to help combat trafficking. The TraffickCam images are more visually similar to images from trafficking investigations than the images from travel websites.

The training dataset includes 1,027,871 images from 50,000 hotels, and 92 major hotel chains. Of the 50,000 hotels, 13,900 include user contributed images from the TraffickCam application  (a total of 55,061 TraffickCam images are included in the training set).

The test dataset includes 17,954 TraffickCam images from 5,000 different hotels (as well as versions of the test images that have medium and large occlusions to replicate the occlusions seen in real world trafficking victim photographs).

## Dependencies
We recommend using Python 2.7. To insure the correct dependencies are installed, run:

```
pip install -r requirements.txt
```

The evaluation code additionally requires the Facebook Research '''Fair AI Similarity Search (FAISS)''' library which can be installed using the directions at: https://github.com/facebookresearch/faiss/blob/master/INSTALL.md.

## Downloading the dataset
The metadata for the hotels, chains and images is in the 'input/dataset.tar.gz' file. When you un-compress this folder, you will find four csv files with the following headers:

* chain_info.csv: chain_id, chain_name
* hotel_info.csv: hotel_id, hotel_name, chain_id, latitude, longitude
* train_set.csv: image_id, hotel_id, image_url, image_source, upload_timestamp
* test_set.csv: image_id, hotel_id, image_url, image_source, upload_timestamp

To download the training images, we provide the 'input/download_train.py' file, which utilizes the python multiprocessing library to download the images in the train_set file to 'images/train'.

The test images (unoccluded and occluded) can be downloaded from https://todo.com/test.tar.gz
