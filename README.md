# FASTER_RCNN_IN_CAPTCHA


## 概念來源
[[心得] 以CNN實作台鐵驗證碼辨識](https://www.ptt.cc/bbs/Python/M.1514130793.A.2E1.html)

看到網友在PTT上分享CNN驗證碼辨識，自己生成圖片、簡單的CNN，高辨識率，只能感嘆粗暴卻是有力的方法；但這個方法卻不能套用到英數混合的驗證碼，因此心生一計使用Faster R-CNN 方法，先選出目標的區域，在辨識該區域的內容。

## Train 及 Tensorboard 
  ![Image](./)
  在Train data訓練完的結果無法準確辨識該區域內容，
  * 調整模型
  * 確定NN模型英數字辨識準確率
### NN模型數字辨識
  ![Image](./)
  
### 英數字混和辨識
  ![Image](./)
  在英數字混和辨識中，準確率低
  
####  設備
|Name|Description|
|----|----|
|OS|Ubuntu 18.04|
|CPU|Intel i5-4460|
|GPU|GTX 1060 6G|
