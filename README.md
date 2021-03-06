# Localized Style Transfer

Localized Style Transfer is an application that performs style transfer while allowing the user control over which portion of the image the style transfer gets applied to. The user provides two images: a **style image** to emulate and a **content image** to apply the style to. The Flask web application provides the user with a list of objects detected to create a mask and control where the style transfer gets applied to, leaving the rest of the image intact.

## Installation

In order to host and run the web application on local machines, follow these steps:
1. Clone the repository.
2. For Ubuntu, install `libasound2-dev`: `sudo apt-get install libasound2-dev`
3. Create a virtual environment to install dependencies: `python3 -m venv path/to/my_venv`
4. Activate the virtual enviroment created: `source activate` 
5. Install dependencies from `requirements.txt`: `pip install -r requirements.txt`
6. To install dependencies needed to access MS COCO:

   On Linux, run `pip install git+https://github.com/waleedka/cocoapi.git#egg=pycocotools&subdirectory=PythonAPI` 
   
   On Windows, run `pip install git+https://github.com/philferriere/cocoapi.git#egg=pycocotools^&subdirectory=PythonAPI`
   
   *Try `pip3 install git+https://github.com/waleedka/coco.git#subdirectory=PythonAPI` if experiencing errors with above lines.
   
   
7. Run `pip install magenta` to install magenta machine learning packages. 

## Usage

1. Activate virtual environment and run the web application using the command `python main.py`
2. The script will automatically download mask_rcnn_coco.h5 file for the object detection model and arbitrary_style_transfer folder for the style transfer model.
3. Open a web browser and enter the address `localhost:5000` or `http://127.0.0.1:5000`
4. Select a style image and a content image.
5. Choose whether to apply the style transfer to:  
   - the whole image 
   - the whole image with adjustable style weights
   - selected objects
   - inverse of the selected objects.
6. In the case of the third and forth options, pick objects by inputing a comma or space separated list of numbers. Each number corresponds to the label number appeared at th beginning of the detected captions. Enter 1000 to select all detected objects. 

## Demos of the App
![Whole App Demo](static/assets/style-transfer-demo.gif)
* [Whole Functionality](https://drive.google.com/file/d/1dYCbiDzef4hw-n4JndIOGh-5ywuYqeIK/view?usp=sharing)
* [Single Style Transfer](https://drive.google.com/file/d/1FoMLvk-yN2U07wJ-w5DYDVdNS3fdmOdN/view?usp=sharing)
* [Object Detection with Style Transfer](https://drive.google.com/file/d/1id1w0Fs03p8N4_9hPUh3JLOWnqF_yyDQ/view?usp=sharing)
* [Inverse Object Detection with Style Transfer](https://drive.google.com/file/d/1pI6nU-ROYsez_FA5tLH0XG1CMx54rsYh/view?usp=sharing)

## Team
- [Huize Huang](https://www.linkedin.com/in/huize-huang-868a46158/) 
- [Aaron Alphonsus](https://www.linkedin.com/in/aaron-alphonsus/)
- [Michael Hu](https://www.linkedin.com/in/michael-lejeune-hu-33a4b921/)
- [Luis Gruber](https://www.linkedin.com/in/luis-gruber2609/)
- [Sarah Saleem](https://www.linkedin.com/in/sarah-saleem/)

## Resources
* [Magenta](https://github.com/tensorflow/magenta)
* [Mask R-CNN](https://github.com/matterport/Mask_RCNN)
