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





#  Frequent Itemset Mining


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
