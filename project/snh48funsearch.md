# SNH48 xox info search

## 表

### 1. 成员表 

> xox_info

|字段|含义|
|----|----|
|id|自增编号[primary key]|
|name|姓名|
|nickname|昵称|
|catchphrase|口号|
|hometown|籍贯|
|birth|生日|
|age|年龄|
|grade|期数|
|team|所属队|
|debut_time|出道时间|
|graduate_time|毕业时间|
|status|状态：nomal，quit，rest，graduted|

### 2. 总选排名表 

> election_rank_info

|字段|含义|
|----|----|
|id|自增编号[primary key]|
|time|举办时间|
|xox_name|xox名字[foreign key: xox_info]|
|rank|排名|

### 3. B50表 

> B50_info

|字段|含义|
|----|----|
|id|自增编号[primary key]|
|time|举办时间|
|performers|表演者名单|
|show_name|节目名称|
|rank|b50排名|

### 4. 公演表

> show_info

|字段|含义|
|----|----|
|id|自增编号[primary key]|
|time|举办时间|
|name|公演名称|
|performers|表演者名单|
|team|所属队|
|unit|unit名单|
|mc|mc话题|

### 5. CP表

> CP_info

|字段|含义|
|----|----|
|id|自增编号[primary key]|
|cp_name|CP名称|
|xox_names|xoxs|
|status|状态：good, be, unknown, avoid|
