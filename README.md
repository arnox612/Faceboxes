# Faceboxes
Faceboxes in Pytorch and trained with dataset FDDB and change the input size to 512*512


## Annotations transfer
The original annotations of FDDB is ellipsel form, in order to be direct trained in Faceboxes we should change it to VOC form.

[ellipsel transform to VOC](https://blog.csdn.net/minstyrain/article/details/77938596)

use the /data/FDDB/fddbannotation.py it will automaticlly generate the VOC annotations. 

Also we should take care of the img_list.txt with the same form as WIDER_FACE(with both .jpg and .xml information).
To transform the orginal img_list.txt using : data/FDDB/trans.py



## Train 

change input size to 512*512 in the train.py
```python
img_dim = 512 # only 1024 is supported
```

And train the FDDB as below:

```ubuntu
python3 train.py --train './data/FDDB'

```

## Test
when we trained FACEBOXES with FDDB, then it could be test with WIDER_FACE.

As the same take care of the img_list.txt without xml info(otherwise the image can not be read).
using /data/WIDER_FACE/trans.py

## Result 
![](https://github.com/arnox612/Faceboxes/blob/master/screenshot/1.png)
![](https://github.com/arnox612/Faceboxes/blob/master/screenshot/2.png)

