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

    yolox - exp - default - yolox_base.py 41번째 줄에서 데이터셋 경로 수정 가능
    yolox - exp - yolox_base.py 에서 augmentation 값을 조절 가능. imgsz도 여기서 조절 가능
    yolox - data - data_augment.py에서는 augmentation이 수행되는 함수들이 있음. 특이하게 함수로 augmentation수행코드를 작성
    yolox - data - dataset - coco.py에서 remove_useless_info 함수 코드를 확인해보면 annotations.json의 필요없는 데이터를 pop시키는것을 확인 가능. 그 밑 COCODataset class에서 print문으로 정제된 json의 결과값 확인 가능
    mosaic는  yolox - data - datasets - mosaicdetection.py 에서 실행되는것 같음. mix_up도 여기서 함수가 정의되어있음.
    yolox - data - datasets - coco_classes.py 에서는 object의 클래스들을 정의. annotations에 정의되어있는 class명과 일치해야함
    train.py를 통해 terminal에서 입력값들의 의미가 뭔지 확인 가능하고 훈련을 실행할 수 있음. 하지만 실질적인 train은 trainer.py에서 수행됨

<p align="center">
<img src="https://github.com/suhyeong-jeon/YOLOX_HumanDetector/assets/70623959/25b8bdcd-81bd-4f33-a6fa-e000481d1482">
  

윈도우 가상환경에서 진행되었음.
[YOLOX](https://github.com/Megvii-BaseDetection/YOLOX)
