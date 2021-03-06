# MySql explain出的结果各项的意义

explain显示了mysql如何使用索引来处理select语句以及连接表。可以帮助选择更好的索引和写出更优化的查询语句。

```sql
EXPLAIN SELECT s.uid,s.username,s.name,f.email,f.mobile,f.phone,f.postalcode,f.address
FROM uchome_space AS s,uchome_spacefield AS f
WHERE s.groupid=0
AND s.uid=f.uid
```

![](https://github.com/johnxue2013/docs/blob/master/images/explain.png)

## type字段
连接(join)类型，有多个值，先从最佳到最差介绍

- `system`  

	表只有一行，这是下面要介绍的值为const类型的特例，平时不会出现，可以忽略不计
	
- `const`  
	针对主键或唯一索引的等值查询扫描, 最多只返回一行数据. `const`查询速度非常快, 因为它仅仅读取一次即可.
    例如下面的这个查询, 它使用了主键索引, 因此 `type`就是`const`类型的.
    
    ```sql
    	mysql> explain select * from user_info where id = 2\G
        *************************** 1. row ***************************
                   id: 1
          select_type: SIMPLE
                table: user_info
           partitions: NULL
                 type: const
        possible_keys: PRIMARY
                  key: PRIMARY
              key_len: 8
                  ref: const
                 rows: 1
             filtered: 100.00
                Extra: NULL
        1 row in set, 1 warning (0.00 sec)
    	```
- `eq-ref`  
	此类型通常出现在多表的 join 查询, 表示对于前表的每一个结果, 都只能匹配到后表的一行结果. 并且查询的比较操作通常是`=`, 查询效率较高. 例如:
	
	```sql
	mysql> EXPLAIN SELECT * FROM user_info, order_info WHERE user_info.id = order_info.user_id\G
    *************************** 1. row ***************************
               id: 1
      select_type: SIMPLE
            table: order_info
       partitions: NULL
             type: index
    possible_keys: user_product_detail_index
              key: user_product_detail_index
          key_len: 314
              ref: NULL
             rows: 9
         filtered: 100.00
            Extra: Using where; Using index
    *************************** 2. row ***************************
               id: 1
      select_type: SIMPLE
            table: user_info
       partitions: NULL
             type: eq_ref
    possible_keys: PRIMARY
              key: PRIMARY
          key_len: 8
              ref: test.order_info.user_id
             rows: 1
         filtered: 100.00
            Extra: NULL
    2 rows in set, 1 warning (0.00 sec)
	```
    
- `ref`  
	此类型通常出现在多表的 join 查询, 针对于非唯一或非主键索引, 或者是使用了 最左前缀 规则索引的查询.
	
	```sql
	mysql> EXPLAIN SELECT * FROM user_info, order_info WHERE user_info.id = order_info.user_id AND order_info.user_id = 5\G
    *************************** 1. row ***************************
               id: 1
      select_type: SIMPLE
            table: user_info
       partitions: NULL
             type: const
    possible_keys: PRIMARY
              key: PRIMARY
          key_len: 8
              ref: const
             rows: 1
         filtered: 100.00
            Extra: NULL
    *************************** 2. row ***************************
               id: 1
      select_type: SIMPLE
            table: order_info
       partitions: NULL
             type: ref
    possible_keys: user_product_detail_index
              key: user_product_detail_index
          key_len: 9
              ref: const
             rows: 1
         filtered: 100.00
            Extra: Using index
    2 rows in set, 1 warning (0.01 sec)
	```

- `range`  
   表示使用索引范围查询, 通过索引字段范围获取表中部分数据记录. 这个类型通常出现在 =, <>, >, >=, <, <=, IS NULL, <=>, BETWEEN, IN() 操作中.  
   
   当 type 是 range 时, 那么 EXPLAIN 输出的 ref 字段为 NULL, 并且 key_len 字段是此次查询中使用到的索引的最长的那个.
	
	```sql
	mysql> EXPLAIN SELECT *
        ->         FROM user_info
        ->         WHERE id BETWEEN 2 AND 8 \G
    *************************** 1. row ***************************
               id: 1
      select_type: SIMPLE
            table: user_info
       partitions: NULL
             type: range
    possible_keys: PRIMARY
              key: PRIMARY
          key_len: 8
              ref: NULL
             rows: 7
         filtered: 100.00
            Extra: Using where
    1 row in set, 1 warning (0.00 sec)
	```
	
- `index`  
   表示全索引扫描(full index scan), 和 ALL 类型类似, 只不过 ALL 类型是全表扫描, 而 index 类型则仅仅扫描所有的索引, 而不扫描数据.
   
   index 类型通常出现在: 所要查询的数据直接在索引树中就可以获取到, 而不需要扫描数据. 当是这种情况时, Extra 字段 会显示 Using index.

	```sql
	mysql> EXPLAIN SELECT name FROM  user_info \G
    *************************** 1. row ***************************
               id: 1
      select_type: SIMPLE
            table: user_info
       partitions: NULL
             type: index
    possible_keys: NULL
              key: name_index
          key_len: 152
              ref: NULL
             rows: 10
         filtered: 100.00
            Extra: Using index
    1 row in set, 1 warning (0.00 sec)
	```
- ALL  

	表示全表扫描, 这个类型的查询是性能最差的查询之一. 通常来说, 我们的查询不应该出现 ALL 类型的查询, 因为这样的查询在数据量大的情况下, 对数据库的性能是巨大的灾难. 如一个查询是 ALL 类型查询, 那么一般来说可以对相应的字段添加索引来避免.
	下面是一个全表扫描的例子, 可以看到, 在全表扫描时, possible_keys 和 key 字段都是 NULL, 表示没有使用到索引, 并且 rows 十分巨大, 因此整个查询效率是十分低下的.
	
	```sql
	mysql> EXPLAIN SELECT age FROM  user_info WHERE age = 20 \G
    *************************** 1. row ***************************
               id: 1
      select_type: SIMPLE
            table: user_info
       partitions: NULL
             type: ALL
    possible_keys: NULL
              key: NULL
          key_len: NULL
              ref: NULL
             rows: 10
         filtered: 10.00
            Extra: Using where
    1 row in set, 1 warning (0.00 sec)
	```

type性能比较:
通常来说, 不同的 type 类型的性能关系如下:
```
ALL < index < range ~ index_merge < ref < eq_ref < const < system
```
ALL 类型因为是全表扫描, 因此在相同的查询条件下, 它是速度最慢的.
而 index 类型的查询虽然不是全表扫描, 但是它扫描了所有的索引, 因此比 ALL 类型的稍快.
后面的几种类型都是利用了索引来查询数据, 因此可以过滤部分或大部分数据, 因此查询效率就比较高了.

原文连接: https://segmentfault.com/a/1190000008131735