Pre-requisites:
1. Download all required models
    * python3 /opt/intel/openvino/deployment_tools/tools/model_downloader/downloader.py --name face-detection-adas-binary-0001 --output_dir models
    * python3 /opt/intel/openvino/deployment_tools/tools/model_downloader/downloader.py --name head-pose-estimation-adas-0001 --output_dir models
    * python3 /opt/intel/openvino/deployment_tools/tools/model_downloader/downloader.py --name landmarks-regression-retail-0009 --output_dir models
    * python3 /opt/intel/openvino/deployment_tools/tools/model_downloader/downloader.py --name gaze-estimation-adas-0002 --output_dir models



Run application:
    python3 main.py -fm ../models/intel/face-detection-adas-binary-0001/FP32-INT1/face-detection-adas-binary-0001.xml -pm ../models/intel/head-pose-estimation-adas-0001/FP32/head-pose-estimation-adas-0001.xml -lm ../models/intel/landmarks-regression-retail-0009/FP32/landmarks-regression-retail-0009.xml -gm ../models/intel/gaze-estimation-adas-0002/FP32/gaze-estimation-adas-0002.xml -i '../bin/demo.mp4' -o . -d "CPU" -c 0.5

    python3 main.py -fm ../models/intel/face-detection-adas-binary-0001/FP32-INT1/face-detection-adas-binary-0001.xml -pm ../models/intel/head-pose-estimation-adas-0001/FP32/head-pose-estimation-adas-0001.xml -lm ../models/intel/landmarks-regression-retail-0009/FP32/landmarks-regression-retail-0009.xml -gm ../models/intel/gaze-estimation-adas-0002/FP32/gaze-estimation-adas-0002.xml -i 'cam' -o . -d "CPU" -c 0.5



Error and their resolution:
1. Error log: ```Traceback (most recent call last):
    File "main.py", line 5, in <module>
    import cv2
    ImportError: dlopen(/opt/intel/openvino_2020.1.023/python/python2.7/cv2.so, 2): Symbol not found: _PyCObject_Type
    Referenced from: /opt/intel/openvino_2020.1.023/python/python2.7/cv2.so
    Expected in: flat namespace
    in /opt/intel/openvino_2020.1.023/python/python2.7/cv2.so
    ```

Under `/opt/intel/openvino_2020.1.023/python` -- it has cv2.so for all python version.
**Resolution** .. just copy pasted python3/cv2.so to python2.7

2. Error log: ModuleNotFoundError: No module named 'openvino'
    Resolution: Add this line to your .bashrc or zhrc file `source /opt/intel/openvino/bin/setupvars.sh`



