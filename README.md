# Computer Pointer Controller
Project is to control the mouse pointer of your computer using gaze estimation model. 
You will be using the InferenceEngine API from Intel's OpenVino ToolKit to build the project. The gaze estimation model requires three inputs:
* The head pose
* The left eye image
* The right eye image.

To get these inputs, you will have to use three other OpenVino models:
* [Face Detection](https://docs.openvinotoolkit.org/latest/_models_intel_face_detection_adas_binary_0001_description_face_detection_adas_binary_0001.html)
* [Head Pose Estimation](https://docs.openvinotoolkit.org/latest/_models_intel_head_pose_estimation_adas_0001_description_head_pose_estimation_adas_0001.html)
* [Facial Landmarks Detection](https://docs.openvinotoolkit.org/latest/_models_intel_landmarks_regression_retail_0009_description_landmarks_regression_retail_0009.html)

##The Pipeline
You will have to coordinate the flow of data from the input, and then amongst the different models and finally to the mouse controller. The flow of data will look like this:
![pipleline of the system](images/pipeline.png)

## Project Set Up and Installation
* Follow the guidelines to install the [openVino](https://docs.openvinotoolkit.org/latest/index.html)
* 

## Running applicaitno (Demo)
* Check [how-to-run](how-to-run.md)


## Documentation
* Run command `python3 main.py -h` to get the supported arguments
* Inference Engine API Docs [here](https://docs.openvinotoolkit.org/latest/_inference_engine_ie_bridges_python_docs_api_overview.html)
* Model documentation [here](https://docs.openvinotoolkit.org/latest/_models_intel_index.html) 

## Benchmarks
I am not able to run the model on multiple devices because I don't have access to all kind of hardware. Though I did try to execute this on udacity's workspace but was getting `file not found ` erro for input file.
NOTE: I have attached the expected working python notebook to run this experiment on multiple devices.

## Results
System Info: MacBook Pro with intel i5
Inference time for full demo video:
    FP16: 113.7 sec
    FP32: 117.2 sec


## Stand Out Suggestions
This is where you can provide information about the stand out suggestions that you have attempted.

### Async Inference
If you have used Async Inference in your code, benchmark the results and explain its effects on power and performance of your project.

### Edge Cases
There will be certain situations that will break your inference flow. For instance, lighting changes or multiple people in the frame. Explain some of the edge cases you encountered in your project and how you solved them to make your project more robust.
