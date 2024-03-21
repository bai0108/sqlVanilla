# sqlVanilla

1. 批量插入代替单条插入
    * 表列少则500条插入一次，列多则100条插入一次
      
2. 关联更新代替单条更新，减少数据库连接造成的额外消耗。

3. DELETE效果很差，可建bak表辅助。
   * 新建bak表，先查询选出要保留的记录，插入bak表。
   * truncate原表
   * 将bak表中记录插入原表
   * 注：保证三步在事务中进行
     
4. DELETE后注意使用vacuum释放缓存，用reIndex重建索引

