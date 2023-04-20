# bag2img
Extract images from a bag file.

# How-to-use

Usage: `python bag2img --img_topic=/img_topic_name --bag=bag_filename --output_folder=output_folder_name --output_format=jpg --sampling 2`

# Optional arguments
```--img_topic``` (mandatory) Name of image topic you want to extract

```--bag``` (mandatory) Path to the bag file and name, e.g. ./dataset/Big.bag, tab auto-completion is possible.

```--file_name``` (optional) Prefixed file name for stored images',default="frame"

```--output_format``` (optional) output image format, e.g., jpg or png',default="jpg"

```--output_folder``` (optional) Path to a output folder where extracted images will be stored.',default="./output"

```--encoding``` (optional) encoding options, e.g., mono8, mono16, bgr8, rgb8, bgra8, rgba8', default="passthrough"

```--sampling``` (optional) save an image every n samples. If it is set to 1, it will store all frames, if set to 2, it will save an image every 2 samples (10Hz -> 5Hz), default="1"

# Simple test
To test the script, we will download a bag file and run the script.
Create a folder and download a bag file into it.
```bash
mkdir dataset & wget -O ./dataset/test.bag https://vision.in.tum.de/rgbd/dataset/freiburg3/rgbd_dataset_freiburg3_calibration_rgb_depth.bag
```
Then you will have dataset folder and `test.bag` file in it. The following command will create output folder named `rgbd_color_output` and store images with name `frame000000.png`. Note that in the downloaded bag file, the color images are stored as 640x480 8-bit RGB images in PNG format and the depth maps are stored as 640x480 16-bit monochrome images in PNG format. Please have a look [dataset description link](https://vision.in.tum.de/data/datasets/rgbd-dataset/file_formats) and [other encoding options](http://wiki.ros.org/cv_bridge/Tutorials/ConvertingBetweenROSImagesAndOpenCVImagesPython). 

## Extracting color images
```bash
python ./bag2img.py --img_topic=/camera/rgb/image_color --bag=./dataset/test.bag --output_folder=./rgbd_color_output --output_format=png
```
After excute the command, you will be able to see the following console output.

```shell
./rgbd_color_output/frame_000000.png saved
...
./rgbd_color_output/frame_001326.png saved
=====================================================
Extraction took 98.090s for extracting 1327 images
=====================================================
```
