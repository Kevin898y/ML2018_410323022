# Assignment2 - Handwritten Character Recognition 

## Environment
>python 3.6.1

>jupyter notebook

## Evaluate

>Accuracy

   下表是各分類器在不同維度下的正確率(%)，而在PCA的調整上，參考老師的建議在0.95~0.97的範圍內

 |   Classifier\ PCA       | 0.95  | 0.96 | 0.97 |
  | :--------------------: |:-----:| :---:|:---: |
  | **SVM**                | 0.969 |0.9666|0.9633|
  | **Logistic Regression**| 0.9133|0.915 |0.9148|
  | **Decision Tree**      | 0.831 |0.8321|0.8298|
  
## Method
1. fetch data  
   使用sklearn可以直接下載資料
   ```python
    mnist = fetch_mldata('MNIST original')
   ```
2. Database normalization  
   圖片是灰階，值介於0 ~ 255，將其除與255轉成0 ~ 1之間，方便訓練  
3. reduced dimensions  
   使用PCA來做降維來增加訓練速度，也避免維度的詛咒，實做方面是以sklearn來完成  
4. training  

   在分類器的選取上，使用了以下三種老師上課所介紹的方法:

   + SVM

   ```python
   clf = SVC(decision_function_shape='ovo')
   clf.fit(x_train, y_train)
   ```

   + Logistic Regression
   ```python
   clf = LogisticRegression(solver = 'lbfgs')
   clf.fit(x_train, y_train)
   ```
   + Decision Tree
   ```python
   clf = tree.DecisionTreeClassifier()
   clf.fit(x_train, y_train)
```
##Result
