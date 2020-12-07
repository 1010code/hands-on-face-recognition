# hands-on-face-recognition


| 人臉辨識套件 (Demo 1)      |  Digital Makeup (Demo 2) |  手刻人臉辨識統 (Demo 3)                      |
|--------------------------------------|--------------------------------------|--------------------------------------|
| [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/1010code/hands-on-face-recognition/blob/main/Face_Recognition_using_face_recognition.ipynb) | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/1010code/hands-on-face-recognition/blob/main/digital_makeup.ipynb) | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/1010code/hands-on-face-recognition/blob/main/face-recognition.ipynb) |

## 人臉辨識套件 (Demo 1)
第一個手把手使用現成套件 [face_recognition](https://github.com/ageitgey/face_recognition) 來實作人臉辨識系統。透過此套件可以快速的將每張影像中識別人臉的關鍵點，包括`眼睛`、`鼻子`、`嘴`和`下巴`。

### 建立人臉資料庫
將所有要辨識的人物放到`image`資料夾中(一個人一張照片即可)。

![](https://i.imgur.com/BmZO5GA.png)

### 辨識圖片中人物
接下來另外實際找幾張照片進行人臉辨識。[face_recognition](https://github.com/ageitgey/face_recognition) 套件呼叫  `face_encodings()` 方法會將輸入的照片進行編碼，並與 `image` 資料夾所有照片逐一比對，尋找特徵相似度最近的人作為輸出。辨識成功就會以綠框表示並顯示人名，若資料庫中尚未此人則以紅框表示。

![](https://i.imgur.com/wiZZhs2.png)

## Digital Makeup (Demo 2)
我們可以透過人臉辨識偵測圖片中人物的眉毛、眼睛、嘴巴的位置。既然位置都定位得到，是否可以向美圖秀秀APP一樣將人物上妝？答案是可！

![](https://i.imgur.com/y7y2ZHo.png)

## 實作流程
1. 載入圖片並使用 `face_recognition.face_landmarks()` 找出人臉的輪廓
2. 將眉毛、眼睛、嘴巴上色

大家可以試試調整 `fill=(X, X, X, X)` 來上不同顏色的妝容。

![](https://i.imgur.com/iYjjfct.png)

## 手刻人臉辨識統 (Demo 3) 
利用預訓練好的 Dlib model，進行人臉辨識，並且實現僅用一張照片作為 database 就可以作出達到一定效果的人臉識別。在實作前需要下載以下兩個是先訓練好的參數，分別為找出68個臉部特徵點以及人臉Embedding模型。

- shape_predictor_68_face_landmarks.dat
- dlib_face_recognition_resnet_model_v1.dat

![](https://i.imgur.com/CW1CH2T.png)

![](https://i.imgur.com/RQcSUNm.png)

### 系統架構

![](https://i.imgur.com/zJZWVna.png)

### 辨識流程

![](https://i.imgur.com/rggAONr.png)