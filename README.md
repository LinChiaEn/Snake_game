# Snake_game
## Introduction
### 作業題目
作業內容:以ML模式完貪吃蛇，蛇的長度超過30即可通過
遊戲進行方式: 
設定rule，以rule based model 進行比賽，並以此取得data
從數據中提取特徵，以機器學習模型對特徵進行training
### 觀察到的現象
純粹根據球的方位移動，若蛇的長度太長則會有snake_head碰到snake_body的情形
有時球的位置會導致蛇需折返，但如果球的x座標換snake_head和snake_body一樣時，得先向旁邊繞再折返
## Method
先依據snake_head和snake_body的位置，判斷是否可以上下左右移動
尋找food前，先將snake_head移至左下角再開始尋找food，避免snake_head碰到snake_body每吃到food一次，便將snake_head移到左下角再繼續找食物
![image](https://github.com/LinChiaEn/Snake_game/assets/93340978/582baa0b-e1dd-47c7-943a-df45036a9471)
![image](https://github.com/LinChiaEn/Snake_game/assets/93340978/9d53701a-5d09-46ef-86d7-2a613336f407)
j
### 提取之特徵
snake_head_x 
snake_head_y 
food_x 
food_y 
head_direction_x 
head_direction_y 
direction 
Command 
### 機器模型
KNN
## Result
用rule去執行分數平均約在60
用機器學習的分數約落在40-70
## Discussion
隨著資料量的增加，貪吃蛇跑的規則越符合rule跑的規則，同時出錯率也減少
一開始有考慮過較複雜的rule，雖然跑出來的過程比較相似個人玩貪吃蛇時會走的路徑，但是分數出來的結果差距很大，有的不滿30、有的答到80以上，所以我尚未train之前就先將rule改成方向較單一的規則，雖然分數到80以上的機率不高，但是每是的分數都超過30，也因rule寫的方式，所以這次還是採去KNN的機器學習

