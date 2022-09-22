## 訓練模型的目的
給予模型<font color=#EB3F5C>數據</font>和<font color=#EB3F5C>答案</font>，使其訓練出一個<font color=#EB3F5C>**規則**</font>用來判斷數據的對錯

## 三種ML種類
- 監督式(Supervised Learning)<br/>
    ML會從標籤化(labeled)的Data中分析後做預測的方式。Labeled可想像成表準答案，ML會對比誤差一邊修正達到更高的準確率。

    優點：非常有效率<br/>
    缺點：事前做大量的Label，需要倚靠大量的事前人工作業

- 非監督式(Unsupervised Learning)<br/>
    把一大堆Data丟進去，讓ML自行尋找Data的規律。

    優點：不用標籤所以節省大量前置作業<br/>
    缺點：費時且會把無意義的特徵(Feature)過度放大

- 強化式(Reinforcement Learning)<br/>
    會有代理人(Agent)、環境(Environment)、獎懲(Positive/nagative reward)，代理人會在未知的環境探索並在根據我們規定好獎懲機制，並做出更有效率的行動(Action)

## batch、iteration、epoch、step
假設有1000個DataSet而我們分200份來進行分批訓練，<font color=#EB3F5C>batch(批次)</font>就是200。而我們送完1000個DataSet需要5次，所以<font color=#EB3F5C>iteration(迭代)</font>就是5。當全部都丟進去然後運算完成以後，就是1個<font color=#EB3F5C>epoch(期)</font>

    Data set size = Iteration * Batch size （1 Epoch）

<font color=#EB3F5C>Step</font>就是會一直跑DataSet直到跑到<font color=#EB3F5C>Step所設定的數字</font>，<font color=#EB3F5C>資料跑完就重頭繼續跑</font>

## Parameter(參數) & Hyperparameter(超參數)

- Parameter：即為模型根據訓練資料自動學習出來的變量，Weight和Bias就屬於Parameter。
- Hyperparameter：即是在模型訓練之前，事先根據經驗給定的參數，Epochs和Layer數就屬於Hyperparameter。

## Validation Set(驗證集)

    用於評估模型的初步能力與超參數調整的依據，是非必要的。

## Learning Rate(學習率)

    決定Weight更新的速度

## K-means運作概念

假設為手寫範例，手寫會有0~9的數字

1. 先設定好K個群(K=9)
2. 在某個D為空間中隨機給K個群心放置在某個位置
3. 每個Data都會合每個群心有歐式距離
4. 將每個Data分類成離他最近的群心
5. 每個群心根據分配過來的Data，更新一次群心位置，位置會在分配的Data中間
6. 重複3-5，直到群心不會有太大的變化(收斂)，結束

## Hidden Markov Models

    基於過去的事件推測未來事件發生的機率

同類型的事件（不同的狀態）依序發生的機率，舉例來說，假設天氣有三種狀態：「晴天」、「陰天」跟「雨天」。如果昨天是雨天，那麼今天是「雨天」的機率，會跟昨天是「晴天」而今天是「雨天」的機率有所不同，這是因為我們相信天氣現象在時間上有某種連續性，前面發生的狀態會影響到後面發生的狀態，而馬可夫模型就是描述這種前後關係的數學語言。

在每個馬爾可夫模型中，我們都有一組有限的狀態。這些狀態可能是“暖”和“冷”或“高”和“低”，甚至是“紅色”、“綠色”和“藍色”。這些狀態“隱藏”在模型中，這意味著我們不會直接觀察它們。

## Bias(偏差)

    給予一個恆定值可以左移或右移激勵函數


## Loss Function(損失函數)

    用於計算輸出與預期的結果相差多遠

## Activation function(激勵函數)

    在神經網路當中，每一層的輸入都是上一層的輸出，導致輸出和輸入存在線性關係，但現實中所有問題都是非線性的，因此激勵函數則把輸出和輸入關係變為非線性。


## Gradient descent(梯度下降)

損失函數遇到代表神經網路優化越好，而梯度下降使我們能找到最佳參數(weight&bias)。

    梯度下降是一種優化算法，用於通過在梯度負值定義的最陡下降方向上迭代移動來最小化某些函數。


![alt text](https://cdn-images-1.medium.com/max/1000/1*iU1QCnSTKrDjIPjSAENLuQ.png)

## Backpropagation(反向傳播)

    將誤差值往回傳遞資訊，使權重可以利用這樣的資訊進行梯度下降法來更新權重。計算輸出層對應的loss，然後將loss以導數的形式不斷向上一層網絡進行傳遞，並修正相應的權重參數，達到降低loss之目的。

## Vanishing Gradient(梯度消失)

    反向傳播時，當梯度從後往前傳時，梯度不斷減小，最後變為零，使得淺層的隱藏層不在被更新，使準確率下降。

## Exploding Gradient(梯度爆炸)

    和消失相反，往前傳時，梯度不斷變大，使權重變得很大，甚至溢出，導致出現NaN

## Overfitting(過度擬合)

    模型的使命就是找出最小的loss，但當資料量太少且epochs太多時，會導致模型在小圈圈過得太爽太有自信，結果出去外面(測試集)發現世界長的不一樣，直接屌打你的準確度。


![alt text](https://d1dwq032kyr03c.cloudfront.net/upload/images/20181020/20112540PwCCbhGvkb.png)
---

## Instruction

### tf.ones()

    tf.ones([1,2,3])：建立都為1*2*3張量，其純量都為1

### tf.reshape()  
    tensor = tf.ones([1,2,3])
    tf.reshape(tensor ,[2,3,1])：將張量轉型成2*3*1(Tensor.shape必須乘積必須相同)
    tf.reshape(tenosr ,[3, -1])：將張量轉型成3*(2*1)(把剩下的乘進來)


