# 2023 AI CUP COMPETITION
【比賽介紹】<br>
透過競賽提供的事實資料庫以及陳述句 (claim)建立自動化的事實檢索與查核系統，以驗證陳述句的真偽。如果陳述句能夠「支持」或「反對」事實，系統也必須透過檢索資料庫中的文章來提供證據句。<br>
<br>
【模型】<br>
1.chinese-electra-base-generator<br>
2.chinese-electra-180g-base-discriminator<br>
<br>
【訓練方式】<br>
1.資料前處理：確定claim的wiki pages<br>
<br>
2.語句檢索：訓練模型判斷wiki page中的證據句。測試是從訓練集claim萃取的名詞與形容詞對應到的wiki page中找出證據句<br>
<br>
3.陳述句驗證：訓練用訓練集的claim + evidence + label來訓練模型辨別label。測試從語句檢索找出的證據句來判斷測試集的claim為support或refutes或not enough info<br>
<br>
【安裝配置環境】<br>
我們整個訓練過程都是在colab上面跑<br>
ipywidgets==8.0.5<br>
pandarallel==1.6.4<br>
pandas==1.5.3<br>
scikit-learn==1.2.2<br>
tensorboard==2.11.0<br>
torch==1.13.1+cu116<br>
tqdm==4.65.0<br>
opencc<br>
hanlp<br>
transformers==4.27.1<br>
wikipedia==1.4.0<br>
<br>
【重要模塊輸出/輸入】<br>
引入官方提供的library<br>
dataset.py<br>
utils.py<br>
<br>
【準確率】<br>
訓練集：0.5215 (loss:3)<br>
驗證集：0.447927<br>
測試集：0.394884<br>
<br>
** AI CUP COMPETITION RANKING **<br>
ranking : 25 / 301<br>
