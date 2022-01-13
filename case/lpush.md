lpush lrange, 
rpush, rrange



luxuefengdeMacBook-Pro:~ luxuefeng$ redis-cli -h 10.4.10.17 -p 6379 -a 9f83d4682ba8b962

Warning: Using a password with '-a' or '-u' option on the command line interface may not be safe.
10.4.10.17:6379>

    10.4.10.17:6379> LRANGE queue_task_UserUniqueVerifyActiveRecordTask 0 1
    1) "{\"action\":\"xztoken\",\"userid\":\"77779202211842\",\"mobile\":\"13230670596\",\"email\":\"\",\"idcardno\":\"130825199402101420\",\"device\":\"\",\"ali_buyer_email\":\"\",\"ali_buyer_id\":\"\",\"ip\":\"10.4.10.17\"}"
    2) "{\"action\":\"xztoken\",\"userid\":\"73902623031298\",\"mobile\":\"17791578510\",\"email\":\"\",\"idcardno\":\"610524199804153620\",\"device\":\"\",\"ali_buyer_email\":\"\",\"ali_buyer_id\":\"\",\"ip\":\"10.4.10.17\"}"
       10.4.10.17:6379>






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