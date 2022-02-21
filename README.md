# visual_recognition

![img](https://github.com/lzeeorno/CVprojects/blob/main/visual_recognition%E4%BA%BA%E8%84%B8%E8%AF%86%E5%88%AB%E8%80%83%E5%8B%A4%E6%9C%BA/record.png)

## 1、hardware：

* Windows10or11（no GPU needed）or MacOS 
* normal RBG USB camera

## 2、software：

* Python：3.7
* opencv: pip install opencv-python  
* Dlib: pip install dlib 

## 3、How ro use：

use `python demo_full.py --{variable}={value}`

```
  -h, --help            show this help message and exit
  --mode MODE           mode：reg,recog -> input face information、face recognition
  --id ID               face ID，int, not repeated
  --name NAME           English people name
  --interval INTERVAL   register face intyerval per second
  --count COUNT         register how many picture of your
  --w W                 windows width，default 1/2 of computer windows 
  --h H                 height width，default 1/2 of computer windows
  --detector DETECTOR   choice detector，option: haar、hog、cnn
  --threshold THRESHOLD from 1- 0, more low value means more recognition points so that more clear
                        
  --record RECORD       detect whether video is recorded 
```



### 2.1、Download models and fonts

* 1. [Download links](https://github.com/lzeeorno/CVprojects/releases/tag/HostedFile1.0)
* 2. unzip two folders(weights, fonts)
* 3. put two folders in same director with demo_full.py


### 2.2、Face register：input face features`./data/feature.csv`

How：

`python demo_full.py --mode=reg --id={face_ID，int} --name={your_name} --interval={int, per second} --count={int, how many picture} --w={int} --h={int} `

like：

`python demo_full.py --mode=reg --id=1 --name='yourname' --interval=5 --count=10`



### 2.3、Face recognition：input Attendance in `./data/attendance.csv`

How to use：

`python demo_full.py --mode=recog --detector={choice detector，option: haar、hog、cnn} --threshold={number from 0-1 } --record={bool}`

like：

`python demo_full.py --mode=recog --detector=haar --threshold=0.2 --record=True`





