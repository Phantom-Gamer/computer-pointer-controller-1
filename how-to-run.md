##Pre-requisites:
1. Download all required models
    * `python3 /opt/intel/openvino/deployment_tools/tools/model_downloader/downloader.py --name face-detection-adas-binary-0001 --output_dir models`
    * `python3 /opt/intel/openvino/deployment_tools/tools/model_downloader/downloader.py --name head-pose-estimation-adas-0001 --output_dir models`
    * `python3 /opt/intel/openvino/deployment_tools/tools/model_downloader/downloader.py --name landmarks-regression-retail-0009 --output_dir models`
    * `python3 /opt/intel/openvino/deployment_tools/tools/model_downloader/downloader.py --name gaze-estimation-adas-0002 --output_dir models`


##Run application:
1. cd to the project directory
2. Download all models using above described commands
3. Checkout out the arguments using help argument
    `python3 main.py -h`
4. Run application using below command:
    `python3 main.py -fm ../models/intel/face-detection-adas-binary-0001/FP32-INT1/face-detection-adas-binary-0001.xml -pm ../models/intel/head-pose-estimation-adas-0001/FP32/head-pose-estimation-adas-0001.xml -lm ../models/intel/landmarks-regression-retail-0009/FP32/landmarks-regression-retail-0009.xml -gm ../models/intel/gaze-estimation-adas-0002/FP32/gaze-estimation-adas-0002.xml -i ../bin/demo.mp4  -o . -d "CPU" -c 0.5 -m 'async' -wi 'yes'`


