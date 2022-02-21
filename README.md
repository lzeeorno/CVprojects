# 人脸识别考勤机

![img](https://github.com/lzeeorno/CVprojects/blob/main/visual_recognition%E4%BA%BA%E8%84%B8%E8%AF%86%E5%88%AB%E8%80%83%E5%8B%A4%E6%9C%BA/record.png)

## 一、硬件：

* Windows10或11（无需GPU）或MacOS 都测试可行
* 普通RBG USB摄像头

## 二、软件：

* Python：3.7
* opencv: pip install opencv-python  
* Dlib: pip install dlib 

## 三、用法：

使用`python demo_full.py --{参数名}={参数值}`

```
  -h, --help            show this help message and exit
  --mode MODE           运行模式：reg,recog 对应：注册人脸、识别人脸
  --id ID               人脸ID，正整数不可以重复
  --name NAME           人脸姓名，英文格式
  --interval INTERVAL   注册人脸每张间隔时间，秒
  --count COUNT         注册人脸照片数量
  --w W                 画面缩放宽度，默认相机宽度1/2
  --h H                 画面缩放高度，默认相机高度1/2
  --detector DETECTOR   人脸识别使用的检测器，可选haar、hog、cnn
  --threshold THRESHOLD
                        人脸识别距离阈值，越低越准确
  --record RECORD       人脸识别是否录制
```



### 2.1、下载模型与字体

**2.1.1 文件模型放到`./weights`目录下**：

* 文件列表

  * `dlib_face_recognition_resnet_model_v1.dat`

  * `haarcascade_frontalface_default.xml`

  * `mmod_human_face_detector.dat`

  * `shape_predictor_68_face_landmarks.dat`

**2.1.2下载`Songti.ttc`字体文件放到`./fonts`目录下**


### 2.2、注册人脸：将人脸特征写入`./data/feature.csv`

用法：

`python demo_full.py --mode=reg --id={人脸ID，正整数} --name={人脸姓名，英文格式} --interval={注册人脸每张间隔时间，秒} --count={注册人脸照片数量} --w={画面宽度} --h={画面高度} `

如：

`python demo_full.py --mode=reg --id=1 --name='yourname' --interval=5 --count=10`



### 2.3、识别人脸开始考勤：将考勤记录写入`./data/attendance.csv`

用法：

`python demo_full.py --mode=recog --detector={人脸识别使用的检测器，可选haar、hog、cnn} --threshold={人脸识别距离阈值，越低越准确} --record={人脸识别是否录制}`

如：

`python demo_full.py --mode=recog --detector=haar --threshold=0.2 --record=True`





