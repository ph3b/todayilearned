# Bind a local port to a remote port using SSH

```ssh -L 5901:127.0.0.1:5901 -N -f -l username host```

Will bind port 5901 on localhost to port 5901 on remote host.

**Great for**
- Connect to MySQL og Postgres instances when ports are blocked to public internet
- If you need an encrypted connection to any port for tcp connections
