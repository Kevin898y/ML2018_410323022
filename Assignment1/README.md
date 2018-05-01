# Assignment 1
## Environment
>python 3.6.1

>jupyter notebook

## training samples
* Train_X 是取圖 K1,K2, I 各一個像素為一行，共 W * H 列
  
* Train_Y 是取圖 E 的像素為一行，共 W * H 列

## parameters

* MaxIterLimit = 100
* α = 1e-8
* 𝜖 = 1e-6
* Batch_Size = 32

## Method

* 處理圖片

    我使用Python的PIL套件來讀取圖片中的每個像素值，以此做為訓練資料的來源

* Loss Function

    <img src="http://chart.googleapis.com/chart?cht=tx&chl=L=\sum(y'-y)^2">
    
* Gradient Descent
    
    我使用mini-batch gradient descent，每一個epoch都先將所有Data亂數洗牌一次，再以每Batch_Size一組去計算Gradient，並更新W

* decrypt

    創一個W* H的空影像，利用求出的 W 計算出每一個像素值，並填入空影像


## Result
* Weight

   w = [ 0.2500258, 0.65998725 , 0.09003878]
 
     
* decrypt image

   ![screenshot](https://github.com/Kevin898y/ML2018_410323022/blob/master/Assignment1/decrypt.png)
   
## Discussions
  
  這一次試著使用老師上課提到的Mini-batch的方式，我認為最難的是在設定batch Size跟learning rate上，因為沒什麼概念，一開始learning rate設太大一直出錯，後來改小才正確，而batch Size會影響執行速度跟出來的結果正確率，不過基本上都有辦法解密出清晰的圖片
