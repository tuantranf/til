# Run Lua script with redis-cli using eval option

I want to update Hubot storage value on RedisCloud.
When using the command line interface to set a value with a very long string (about 12000 characters).
```bash
SET mystring "[long string]"
```
String gets cut off at 4,066 characters.
Same at [stackoverflow](http://stackoverflow.com/questions/20362951/redis-is-there-a-limit-on-set-for-datatype-string)

Arrcording to that, redis-cli uses linenoise custom library for terminal input, which happens to have hard-coded input buffer size of 4096 bytes
See: [linenoise.c#L101](https://github.com/antirez/redis/blob/unstable/deps/linenoise/linenoise.c#L101)

Run Lua script with redis-cli using eval option

Write a Lua script file
```
# vim set_storage.lua
redis.call("SET", "hubot:storage", "{\"users\":{\" ........very long.....")
```
Run Lua script file using --eval option
```
$ redis-cli --eval ~/set_storage.lua
$ (nil)
```

Done. :beer:
