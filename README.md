# data-course-content-based
### 專案目的
以商品資料及評論資料，建立 content-based 推薦系統。

### 專案資料
專案中，將使用商品資料以及評論資料，以下為兩個資料集的詳細資訊：
#### 1. 評論資料：2000-01-10 - 2018-10-02 (共 371345)，以 2018-09-01 為切點切分資料集。
* 訓練資料：2000-01-10 - 2018-09-01 (共 370752)
* 測試資料：2018-09-01 - 2018-09-30 (共 590)
#### 2. 商品數量：共 32892 個商品

### 推薦邏輯
#### 1. content-based: 取過去一個月內 (2018-08-01 - 2018-08-31) 有銷售紀錄的商品，以商品的標題及描述為文字資訊，濾除文字資訊的 stopword 及標點符號並轉為小寫後，以 TFIDF 取得商品的文字向量。透過文字向量可計算商品的相似度，並由用戶過去一個月內的購買紀錄，推薦最相似的商品。
#### 2. rule-based: 新用戶無購買的歷史紀錄，無法使用 content-based filtering。因此針對新用戶，採用 rule-based 的推薦，推薦過去一個月內最多人購買的商品。

### 推薦結果
* 推薦系統取 10 名商品進行命中率的驗證：0.1525
* 推薦系統取 15 名商品進行命中率的驗證：0.1627
* 推薦系統取 20 名商品進行命中率的驗證：0.1932
