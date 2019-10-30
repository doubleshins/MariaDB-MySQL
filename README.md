# MariaDB-MySQL


## MariaDB
MariaDB的開發是由MySQL的一些原始開發者領導的，他們擔心甲骨文公司收購MySQL後會有一些隱患。


- MariaDB直到5.5版本，均依照MySQL的版本。因此，使用MariaDB5.5的人會從MySQL 5.5中了解到MariaDB的所有功能。

- 從==2012年11月12日==起釋出的10.0.0版開始，不再依照MySQL的版號。10.0.x版以5.5版為基礎，加上移植自MySQL 5.6版的功能和自行開發的新功能。



| 版本|原始釋出日期   |
|:---|:-----------:|
|5.1 |2009年10月29日|
|5.2 |2010年4月10日 |
|5.3 |2011年7月26日 |
|5.5 |2012年2月25日 |
|10.0|==2012年11月12日==|
|10.1|2014年6月30日 |
|10.2|2016年4月18日 |
|10.3|2017年4月16日 |
|10.4|2018年11月9日 |



## MySQL
原本是一個開放原始碼的關聯式資料庫管理系統，原開發者為瑞典的MySQL AB公司。

- 2009年，甲骨文公司（Oracle）收購昇陽微系統公司，MySQL成為Oracle旗下產品。

- MySQL針對不同的用戶，分了社區版和企業服務器版，還提供一些其它版本，是屬於MySQL相關工具。

1. MySQL Community Server 社區版本，開源免費，但不提供官方技術支持。
2. MySQL Enterprise Edition 企業版本，需付費，可以試用30天。
3. MySQL Cluster 集群版，開源免費。可將幾個MySQL Server封裝成一個Server。
4. MySQL Cluster CGE 高級集群版，需付費。
5. MySQL Workbench（GUI TOOL）一款專為MySQL設計的ER/數據庫建模工具。

| 版本|原始釋出日期   |
|:---|:-----------:|
|5.1 |2008年11月14日|
|5.5 |2010年12月03日 |
|5.6 |2013年02月05日 |
|5.7 |2015年10月21日 |
|8.0|==2018年04月19日==|


## Microsoft SQL Server
Microsoft SQL Server(微軟結構化查詢語言伺服器)是由美國微軟公司所推出的關聯式資料庫



| 版本|年份   |
|:---|:-----------:|
|1.0 (OS/2) |1989|
|1.1 (OS/2) |1990|
|4.2A (OS/2)|1992|
|4.2B (OS/2) |1993|
|4.21a (WinNT)|1993|
|6.0|1995|
|7.0|1998|
|8.0|2003|
|9.0|2005|
|10.0|2018|
|11.0|2012|
|12.0|2014|
|13.0|2016|
|14.0|2017|
|15.0|2019|

## 1.和SQL server語法主要不同的地方
MySQL和SQL Server一樣，對大小寫不敏感。但不同的是
在MySQL中對部分對象的引用是大小寫敏感的，如數據庫名、表名，但對字段、索引、函數、存儲過程等的引用不敏感。

## 2.註釋符
在MySQL中支持三種註釋方法：以下都可以是行內註釋。

1. 使用#作為開頭，後面的全是註釋。
2. 使用/**/註釋符。
3. 使用--作為註釋開頭，但要註意，MySQL中這種註釋方法和SQL Server等其他標準數據庫註釋語法稍有不同，MySQL要求第二個短線後面必須跟一個空白字符，如空格。

## 3.auto_increment

MySQL中設置自增列(auto_increment)的列必須是有索引的列，且創建表時要顯式指定的種子值需要在建表語句之後。另外MySQL一張表只能有一個自增列。

而SQL Server中可以有多個自增列。且MySQL中向自增列插入數據時必須使用null來表示插入的是自增列，除非顯式指定插入列表中不包含自增列，而SQL Server向自增列插入數據時可以且必須無視該列，除非設置顯示插入模式。

## 4.查看表的屬性
```bash
-- SQL Server使用存儲過程sp_help
exec sp_help emp;

-- MySQL使用desc描述或者使用show
mysql> desc emp1;
```

## 5.修改表名
```bash
-- SQL Server使用存儲過程sp_rename
EXEC sp_rename emp,emp2 [object]

-- mysql使用alter語句中的rename功能
alter table emp rename [to] emp3;
```

## 6.刪除表
MySQL比SQL Server要方便很多，判斷起來也方便很多。
```bash
-- SQL Server刪除表，每次只能刪除一張表
if object_id('table_name') is not null drop table table_name;
if exists(select object_id('table_name')) drop table table_name;

-- MySQL可以直接判斷，且一次可以刪除多表
drop table if exists table_name1,table_name2...
```

[MySQL基本語法(一)：和SQL Server語法的差異小歸納](https://www.itread01.com/articles/1506369615.html)




## 連結

https://en.wikipedia.org/wiki/MySQL#Release_history


