Today I learned to rsync directories to remote server by SSH. Assuming SSH key exists.
```shell
$ rsync -avzh ./dir-to-sync username@server.com:/absolute/path/to/target
```
