# human-pose-estimation-opencv
Perform Human Pose Estimation in OpenCV Using Activityrecognition MobileNet

![OpenCV Using Activityrecognition MobileNet](output.JPG)


# How to use

- Test with webcam

```
python Activityrecognition.py
```

- Test with image
```
python Activityrecognition.py --input image.jpg
```

- Use `--thr` to increase confidence threshold

```
python Activityrecognition.py --input image.jpg --thr 0.5
```

# Notes:
- I modified the [OpenCV DNN Example](https://github.com/opencv/opencv/blob/master/samples/dnn/Activityrecognition.py) to use the `Tensorflow MobileNet Model`, which is provided by [ildoonet/tf-pose-estimation](https://github.com/ildoonet/tf-pose-estimation/tree/master/models/graph/mobilenet_thin), instead of `Caffe Model` from CMU Activityrecognition. The original `Activityrecognition.py` from `OpenCV example` only uses `Caffe Model` which is more than 200MB while the `Mobilenet` is only 7MB.
- Basically, we need to change the `cv.dnn.blobFromImage` and use `out = out[:, :19, :, :]` to get only the first 19 rows in the `out` variable.
