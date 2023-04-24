# 作業目標
目標:
練習pre-processing、discretize、reduce dimensionality
自己寫程式、不會的時候看懂別人寫的github程式
找出interesting的rule
了解資料!(特性、數目、領域、留下的欄位attribute、欄位性質、用來的tasks、空/缺失的欄位、hits點閱)
			
		stockCode	商品編號
		Quantity	賣了多少
		Date	交易時間
		Unitprice	價錢/盒
		Customer ID	客戶名
		Country	國家

問題與討論:
|遇到的問題|	解決方法|
|---------|--------|
|Print語法不同|	Python3要加()|
|在安裝mpi4py的時候，使用conda install mpi4py安裝插件後會無法使用。|	因為使用mpi4py的時候會需要call 其他函式庫一併使用，所以要用Microsoft MPI的指令:conda install -c conda-forge mpi4py msmpi|
|Xrange無法使用|	由於python3之後的版本就沒有Xrange了，而range可以完全取代Xrange的用法，所以只需要將Xrange()的地方更換成range()即可|
|會出現Error:iterator should return strings, not bytes|因為’rb’型態會將讀取的資料用byte來開啟，而改成’r’就可以把資料用text mode開啟了|
|使用到sys.argv[]作為引數的部分，在cmd會無法顯示結果出來|	把sys.argv[2]使用自己設定的輸入參數inp[2]取代。(位在apriori_mpi.py程式的第10行。)|
 









#  [Github原文] Frequent Itemset Mining


Apriori algorithm for discovering frequent itemsets for mining Boolean association rules.

**Motivation** : http://cse.iitkgp.ac.in/~bivasm/uc_notes/07apriori.pdf

**Original Paper** :

> *Rakesh Agrawal and Ramakrishnan Srikant Fast algorithms for mining association rules in large databases. Proceedings of the 20th International Conference on Very Large Data Bases, VLDB, pages 487-499, Santiago, Chile, September 1994.*

##Usage

The algorithm can be executed with (Both minimum support and minimum confidence lie between [0, 1]):

    python apriori.py <data_set> <minimum_support> <minimum_confidence>

Example:

    python apriori.py datasets/retail.csv 0.3 0.6



##Dataset:

`retail.dat` contains the (anonymized) retail market basket data from an anonymous Belgian retail store(Source: http://fimi.ua.ac.be/data/).
Additionally, `retail.dat` was converted into `retail.csv` using `dat2csv.py` provided in the repository
