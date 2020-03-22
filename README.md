# covid19-detection
Detection of Covid-19 from X-ray images

## Train
``` shell script
python3 TRAIN.py -d dataset/test -m model_name.hdf5
```
**NOTE** :
- Model with `model_name.hdf5` will save in SavedModel directory.
- `ep` variable in TRAIN.py file is epoch count. you can change it.

example:
```shell script
python3 TRAIN.py -d dataset/test -m amin.hdf5
```
result:
![train result](/ReadmeImages/train_result.png)

## Test 
### test 10 random image
``` shell script
python3 test_model_10_images.py -d dataset/validation -m model_name.hdf5
```
load and show 10 labeled samples

example:

![test result](/ReadmeImages/example_1.png)

### test single image

```shell script
python3 test_model_1_image.py -i path_to_image  -m path_to_model

```
example:
```shell script
python3 test_model_1_image.py -i ./dataset/one/covid/Chest.jpeg  -m ./SavedModel/amin.hdf5
```

# Todo
- Simple API for upload new images and gathering new datasets. data immediately predict by the system and validate by the user for the cleaner dataset.

## API ( WIP )
for gathering more images and make the dataset better, I create e simple API for upload the X-RAY image like below examples:
![](/dataset/validation/covid/01.jpeg)
![](/dataset/validation/covid/02.jpeg)
![](/dataset/validation/covid/03.jpeg)


The uploaded image will validate after upload and the server return label of the image.
Label my be incorrect. (because of the low count of images in the dataset).
![](docs.png)
