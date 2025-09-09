# **台灣近十年失業率之探討**

## **專題介紹**
本專題是針對台灣近十年來失業率(青年失業、總失業)來進行探討，主要是利用管制圖來判斷哪些年份有出現異常，並試著找出造成異常的原因。後續嘗試利用時間序列的模型來進行分析與解釋。

---

## **資料介紹**  
- 資料來源 : 中華民國統計資訊網、勞動部統計查詢網  
- 資料時間 : 民國100年至112年，共13年  
- 資料單位 : 年單位及月單位 

---

## **資料初步分析**
- 比較民國69年至112年的失業率
- 整理民國100年至112年的資料(青年失業、總失業)
- 失業因果圖(魚骨圖)
- 總失業率與青年失業率比較
  
---

## **研究方法** 

### 1. **資料是否為常態分佈**
- 利用Q-Q plot 與 Shaprio-wilk normality test
- 青年失業與總失業率都有滿足


### 2. **管制圖**  
- 總失業 :   
  - Individual Chart : 民國100年(金融風暴影響)、民國112年(疫情解封影響)為out of control  
  - Moving Range Chart : 沒有異常  
  - Cusum Chart : 前半段out of control，可以對應前面Individual Chart的推測
  - EWMA : 前半段out of control，也可對應金融風暴影響
- 青年失業 : 
  - Individual Chart : 民國100年out of control，民國112年接近下管制線
  - Moving Range Chart : 沒有異常
  - Cusum Chart : 前半段out of control，可以對應前面Individual Chart的推測
  - EWMA : 前半段out of control, 也可對應金融風暴影響

### 3. **時間序列模型(時間為月單位)**
- 總失業 :
  1. ADF檢定 : 檢定結果為序列不穩定，需進行一皆差分  
  2. 序列有自相關  
  3. AR(2)MR(2)模型     
  4. 模型殘差管制圖 : out of control點推測與疫情相關    
- 青年失業 :  
  1. ADF檢定 : 檢定結果為序列穩定，不進行一皆差分    
  2. 序列有自相關  
  3. AR(3)MR(1)模型    
  4. 模型殘差管制圖 : out of control點推測與疫情相關 

---

## **結語**
1. 雖然青年失業率相較總失業率高出不少，但整體趨勢是差不多的。  
2. 從時間序列模型可以發現總失業率與青年失業率在疫情期間都會有預測比較不穩定的情形。  
3. 續可以利用比較多年的資料來探討兩者之間的差異，因為這幾年比較有影響的事件只有疫情，所以較難了解外部因素對兩個種類的差別。

---  

## **參考資料**
[中華民國統計資訊網](https://www.stat.gov.tw/)  
[勞動部統計查詢網](https://statfy.mol.gov.tw/index02.aspx)  
[ARMA](https://medium.com/@cindy050244_52136/%E6%99%82%E9%96%93%E5%BA%8F%E5%88%97%E6%8E%A2%E7%B4%A2-%E4%BA%8C-arima%E5%AE%B6%E6%97%8F%E7%B0%A1%E4%BB%8B-8d533f0b18d6)

---

## **結構**
Unemployment_Rate_Quality_Analysis  
│── README.md    
│── unemployment_main.pdf # 書面報告(總失業)，youth(青年失業)     
│── unemployment_code.Rmd # 程式碼(總失業)，youth(青年失業)      
│── unemployment_reort.pdf  # 簡報(總失業)，youth(青年失業)     
│── unemployment_year.csv # 總失業率資料(年)，youth(青年失業)  
│── unemployment_month.csv #總失業率資料(月)，youth(青年失業)

