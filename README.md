### Helper utils for various tasks ###

### How should you use these scripts?
In your Dockerfile add one or more of these tools with:
```Dockerfile
```

#### every ####
Run command periodically -- poor mans cron
```ShellSession
$ every '1 hour 34 mins' date
...
```

#### if_changed ####
Run command if a file has changed since last time
```ShellSession
$ if_changed requirements.txt pip install -r requirements.txt
...
```

#### wait_for ####
Run command until it succeeds
```ShellSession
# Wait for cassandra startup
$ wait_for -t 60 nc -w0 localhost 9042
```
