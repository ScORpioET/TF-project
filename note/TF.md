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

## Instruction

### tf.ones()

- tf.ones([1,2,3])：建立都為1*2*3張量，其純量都為1

### tf.reshape()
tensor = tf.ones([1,2,3])
- tf.reshape(tensor ,[2,3,1])：將張量轉型成2*3*1(Tensor.shape必須乘積必須相同)
- tf.reshape(tenosr ,[3, -1])：將張量轉型成3*(2*1)(把剩下的乘進來)