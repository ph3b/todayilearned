## Shortcut SSH

In ~./ssh/config

```shell
Host shortcut
    Hostname ip-address
    User username
    Port 441
```
Then we can do
`$ ssh shortcut` instead `$ ssh -p 441 username@ip-address`

## Execute command on remote
`$ ssh shortcut "./some/script"`
