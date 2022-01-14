

luxuefengdeMacBook-Pro:~ luxuefeng$ redis-cli -h 10.4.10.17 -p 6379 -a 9f83d4682ba8b962

Warning: Using a password with '-a' or '-u' option on the command line interface may not be safe.
10.4.10.17:6379>

    10.4.10.17:6379> LRANGE queue_task_UserUniqueVerifyActiveRecordTask 0 1
    1) "{\"action\":\"xztoken\",\"userid\":\"77779202211842\",\"mobile\":\"13230670596\",\"email\":\"\",\"idcardno\":\"130825199402101420\",\"device\":\"\",\"ali_buyer_email\":\"\",\"ali_buyer_id\":\"\",\"ip\":\"10.4.10.17\"}"
    2) "{\"action\":\"xztoken\",\"userid\":\"73902623031298\",\"mobile\":\"17791578510\",\"email\":\"\",\"idcardno\":\"610524199804153620\",\"device\":\"\",\"ali_buyer_email\":\"\",\"ali_buyer_id\":\"\",\"ip\":\"10.4.10.17\"}"
       10.4.10.17:6379>

查看队列长度

    10.4.10.17:6379> LLEN queue_task_UserUniqueVerifyActiveRecordTask
    (integer) 175463
    10.4.10.17:6379>
    10.4.10.17:6379> LLEN queue_task_UserUniqueVerifyActiveRecordTask
    (integer) 175463
    10.4.10.17:6379> LLEN queue_task_UserUniqueVerifyActiveRecordTask
    (integer) 175464





    127.0.0.1:6379> lpush a1 a
    (integer) 1
    127.0.0.1:6379> lpush a1 b
    (integer) 2
    127.0.0.1:6379> lpush a1 c
    (integer) 3
    127.0.0.1:6379> lrange a1
    (error) ERR wrong number of arguments for 'lrange' command
    127.0.0.1:6379>
    127.0.0.1:6379> set ak aa
    OK
    127.0.0.1:6379> get ak
    "aa"
    127.0.0.1:6379> setex ak 5 addddd
    OK
    127.0.0.1:6379> get ak
    "addddd"
    127.0.0.1:6379> get ak
    "addddd"
    127.0.0.1:6379> get ak
    (nil)
    127.0.0.1:6379> get ak
    (nil)
    127.0.0.1:6379> get ak
    (nil)
    127.0.0.1:6379> LRANGE a1
    (error) ERR wrong number of arguments for 'lrange' command
    127.0.0.1:6379> LRANGE a1  0 4
    1) "c"
    2) "b"
    3) "a"
       127.0.0.1:6379> LRANGE a1  0 4
    1) "c"
    2) "b"
    3) "a"
       127.0.0.1:6379> LRANGE a1  0 2
    1) "c"
    2) "b"
    3) "a"
       127.0.0.1:6379> LRANGE a1  0 1
    1) "c"
    2) "b"
       127.0.0.1:6379> keys *
    1) "appstore:version:ios::6.22.05"
    2) "myzset"
    3) "a"
    4) "a1"
       127.0.0.1:6379> config set requirepass 1234567
       OK
       127.0.0.1:6379> auth 1234567
       OK
       127.0.0.1:6379> LRANGE aaa 0 1
    1) "bbb"
       127.0.0.1:6379>


LPUSH key value [value ...]

将一个或多个值 value 插入到列表 key 的表头

如果有多个 value 值，那么各个 value 值按从左到右的顺序依次插入到表头： 比如说，对空列表 mylist 执行命令 LPUSH mylist a b c ，列表的值将是 c b a ，这等同于原子性地执行 LPUSH mylist a 、 LPUSH mylist b 和 LPUSH mylist c 三个命令。

如果 key 不存在，一个空列表会被创建并执行 LPUSH 操作。

当 key 存在但不是列表类型时，返回一个错误


# 加入单个元素

redis> LPUSH languages python
(integer) 1


# 加入重复元素

redis> LPUSH languages python
(integer) 2

redis> LRANGE languages 0 -1     # 列表允许重复元素
1) "python"


    127.0.0.1:6379>
    127.0.0.1:6379> lpush que a
    (integer) 1
    127.0.0.1:6379> lpush que b
    (integer) 2
    127.0.0.1:6379> lpush que c
    (integer) 3
    127.0.0.1:6379> lrange que
    (error) ERR wrong number of arguments for 'lrange' command
    127.0.0.1:6379> lrange que 0 -1
    1) "c"
    2) "b"
    3) "a"
       127.0.0.1:6379> rrange que 0 -1
       (error) ERR unknown command `rrange`, with args beginning with: `que`, `0`, `-1`,
       127.0.0.1:6379>
       127.0.0.1:6379> rrange que -1 0
       (error) ERR unknown command `rrange`, with args beginning with: `que`, `-1`, `0`,
       127.0.0.1:6379> lrange que 0 -1
    1) "c"
    2) "b"
    3) "a"
       127.0.0.1:6379> llen que
       (integer) 3
       127.0.0.1:6379>

LPOP
LPOP key

移除并返回列表 key 的头元素。

    127.0.0.1:6379> lrange que 0 -1
    1) "c"
    2) "b"
    3) "a"
       127.0.0.1:6379> llen que
       (integer) 3
       127.0.0.1:6379> lpop que
       "c"
       127.0.0.1:6379> rpop que
       "a"
       127.0.0.1:6379> rpop que
       "b"
       127.0.0.1:6379> rpop que
       (nil)
       127.0.0.1:6379>