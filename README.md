# bag2img
Extract images from a bag file.

# How-to-use

Usage: python bag2img --img_topic=/img_topic_name --bag=bag_filename --output=output_folder_name --output_format=jpg

# Optional arguments
"--img_topic" (mandatory) Name of image topic you want to extract
"--bag" (mandatory) Path to the bag file and name, e.g. ./dataset/Big.bag, tab auto-completion is possible.
"--file_name" (optional) Prefixed file name for stored images',default="frame"
"--output_format" (optional) output image format, e.g., jpg or png',default="jpg"
"--output_folder" (optional) Path to a output folder where extracted images will be stored.',default="./output"
