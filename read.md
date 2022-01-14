To start redis:
brew services start redis




me@localhostt ~ % brew install redis
==> Downloading https://ghcr.io/v2/homebrew/core/redis/manifests/6.2.5
######################################################################## 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/redis/blobs/sha256:fc47114ec01104559f63cd697eb25117ee37da92a5876a104c0d444a801e54f5
==> Downloading from https://pkg-containers.githubusercontent.com/ghcr1/blobs/sha256:fc47114ec01104559f63cd697eb25117ee37da92a5876a104c0d444a801e54f5?se=2022-01-08T05%3A45%3
######################################################################## 100.0%
==> Pouring redis--6.2.5.big_sur.bottle.tar.gz
==> Caveats
To start redis:
brew services start redis
Or, if you don't want/need a background service you can just run:
/usr/local/opt/redis/bin/redis-server /usr/local/etc/redis.conf
==> Summary
🍺  /usr/local/Cellar/redis/6.2.5: 14 files, 2.0MB
me@localhostt ~ %
