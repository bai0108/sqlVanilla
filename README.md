# sqlVanilla

1. 批量插入代替单条插入
  a. 表列少则500条插入一次，列多则100条插入一次
2. 关联更新代替单条更新，减少数据库连接造成的额外消耗。
3. DELETE效果很差，可建bak表辅助。
  a. 新建bak表，先查询选出要保留的记录，插入bak表。
  b. truncate原表
  c. 将bak表中记录插入原表
  d. 注：保证三步在事务中进行
DELETE后注意使用vacuum释放缓存，用reIndex重建索引

![image](https://github.com/bai0108/sqlVanilla/assets/38966479/b67293c4-bcad-4c14-9f61-b9850f7df304)
