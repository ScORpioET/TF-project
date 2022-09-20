# 卷積神經網路(Convolutional neural network, CNN) 

卷積神經網路實線的重點之一就是權重共享(Shared Weight)這件事情，下左圖，透過卷積運算的方法達到Local connected neural nets。

![alt text](./img/CNN.png)

## Convolution(卷積)

利用 filter 在輸入圖片上滑動並且持續進行矩陣內積，卷積後得到的圖片我們稱之為 feature map。

![alt text](https://i.imgur.com/JTqr2Yw.png)

![alt text](https://i.imgur.com/v4VM3qu.gif)

![alt text](./img/Convolution.png)



圖片來源：https://chih-sheng-huang821.medium.com/%E5%8D%B7%E7%A9%8D%E7%A5%9E%E7%B6%93%E7%B6%B2%E8%B7%AF-convolutional-neural-network-cnn-cnn%E9%81%8B%E7%AE%97%E6%B5%81%E7%A8%8B-ecaec240a631