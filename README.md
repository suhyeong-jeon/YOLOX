# YOLOX

### 1. Set conda environment

    conda env create -f YOLOX_ENV.yaml

### 2. Access to the folder

    cd YOLOX-main

### 3. Train the model

    python tools/train.py -f exps/example/custom/yolox_m.py -d 1 -b 32 --fp16 -o -c yolox/yolox_m.pth

### 4. Check the result

    python tools/demo.py video -f exps/example/custom/yolox_m.py -c YOLOX_outputs/yolox_m/latest_ckpt.pth --path yolox/test.mp4 --conf 0.25 --nms 0.45 --tsize 640 --save_result --device gpu


<p align="center">
<img src="https://github.com/suhyeong-jeon/YOLOX_HumanDetector/assets/70623959/25b8bdcd-81bd-4f33-a6fa-e000481d1482">
  

윈도우 가상환경에서 진행되었음.
[YOLOX](https://github.com/Megvii-BaseDetection/YOLOX)
