    me@localhostt ~ % redis-cli
    127.0.0.1:6379>
    127.0.0.1:6379>
    127.0.0.1:6379> set key_a value
    OK
    127.0.0.1:6379> get key_a
    "value"
    127.0.0.1:6379> set key_b value_b EX 5
    OK
    127.0.0.1:6379> get key_b
    "value_b"
    127.0.0.1:6379> get key_b
    (nil)
    127.0.0.1:6379>
    
    
    127.0.0.1:6379> setex k_c 5 value_c
    OK
    127.0.0.1:6379> get k_c
    "value_c"
    127.0.0.1:6379> get k_c
    (nil)
    127.0.0.1:6379>