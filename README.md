# FASTER_RCNN_IN_CAPTCHA


## 概念來源
[[心得] 以CNN實作台鐵驗證碼辨識](https://www.ptt.cc/bbs/Python/M.1514130793.A.2E1.html)

看到網友在PTT上分享CNN驗證碼辨識，自己生成圖片、簡單的CNN，高辨識率，只能感嘆粗暴卻是有力的方法；但這個方法卻不能直接辨識其他英數混合的驗證碼，因此心生一計使用Faster R-CNN 方法，先選出目標的區域，在辨識該區域的內容。
[Faster](##faster-rcnn)

####  設備
|Name|Description|
|----|----|
|OS|Ubuntu 18.04|
|機器學習框架|Tensorflow-gpu1.10.1|
|CPU|Intel i5-3470|
|GPU|GTX 1060 6G|
#### Data 
仿照網友提供驗證碼規則，生成英數字混合之圖片（不包含O和I）<br />
LETTERSTR = '1234567890ABCDEFGHJKLMNPQRSTUVWXYZ'

<!--|項目|總類|圖示|
|---|---|---|
|Train|英數字混合| <img src="./read_img/train01.jpg" width="30%" height="30%">|
|驗證10|數字|<img src="./read_img/validation1001.jpg" width="30%" height="30%">|
|驗證34|英數字混合（同Train）|<img src="./read_img/validation3401.jpg" width="30%" height="30%">| -->

|Item|part1|part2|part3|part4|
|:---:|:---:|:---:|:---:|:---:|
|項目名稱|Faster RCNN (#Faster RCNN)|||||
|Data種類|英數字混合|數字|英數字混合（同part1）|英數字混合(英數字未旋轉)|
|Train個數|1,2000張|30,000張|35,000張|37,000張|
|圖例|![Image](./read_img/train01.jpg)|![Image](./read_img/validation1001.jpg)|![Image](./read_img/validation3401.jpg)|![Image](./read_img/.jpg)|
<!-- <img src="./read_img/train01.jpg" width="100%" height="100%">|<img src="./read_img/validation1001.jpg" width="30%" height="30%">|<img src="./read_img/validation3401.jpg" width="30%" height="30%">|<img src="./read_img/validation1001.jpg" width="30%" height="30%">| -->

## Faster RCNN 
### Train 及 Tensorboard 
  ![Image](./read_img/train_tensorboard.jpg)
  在Train data訓練完的結果無法準確辨識該區域內容，僅能分辨前景、背景
  * 調整模型
  * 確定NN模型英數字辨識準確率()
## NN模型
### 數字辨識
  首先縮減資料難度，僅使用數字的部分，訓練後結果顯著，正確率高
  <img src="./read_img/validation1002.gif" width="45%" height="50%"> <img src="./read_img/validation1003.png" width="45%" height="50%">
### 英數字混和辨識
  
  ##### 英數字混和訓練中，正確率只有0.35左右
  ![Image](/read_img/validation3402.png)
  ##### Test結果如下
  <img src="./read_img/validation3404.gif" width="45%" height="50%" ><img src="./read_img/validation3403.png" width="45%" height="50%" >
### 英數字未旋轉
  

