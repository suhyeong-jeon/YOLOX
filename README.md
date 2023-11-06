# YOLOX

### 1. Set conda environment

    conda env create -f YOLOX_ENV.yaml

### 2. Access to the folder

    cd YOLOX-main

### 3. Train the model

    python tools/train.py -f exps/example/custom/yolox_m.py -d 1 -b 32 --fp16 -o -c yolox/yolox_m.pth

### 4. Check the result

    python tools/demo.py video -f exps/example/custom/yolox_m.py -c YOLOX_outputs/yolox_m/latest_ckpt.pth --path yolox/test.mp4 --conf 0.25 --nms 0.45 --tsize 640 --save_result --device gpu

### 끄적끄적

#### 데이터셋 구조
main folder
datasets 
COCO
train2017
 - images
val2017
 - images
annotations
 - instances_train2017.json
 - instances_val2017.json

#### 구성요소
yolox - exp - yolox_base.py 에서 augmentation 값을 조절 가능. imgsz도 여기서 조절 가능


<p align="center">
<img src="https://github.com/suhyeong-jeon/YOLOX_HumanDetector/assets/70623959/25b8bdcd-81bd-4f33-a6fa-e000481d1482">
  

윈도우 가상환경에서 진행되었음.
[YOLOX](https://github.com/Megvii-BaseDetection/YOLOX)
