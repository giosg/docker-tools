### Helper utils for various tasks ###

### How should you use these scripts?
In your Dockerfile add one or more of these tools with:

```Dockerfile
ADD https://raw.githubusercontent.com/giosg/docker-tools/86743551aebacf4a0289a86e1fee04a75d63519b/wait_for /usr/local/bin/wait_for
RUN chmod +x /usr/local/bin/wait_for
```
You should probably use a specific commit in the url to make sure that no one will break your build by accident

If you don't care then you can just use the latest version every time
```Dockerfile
ADD https://raw.githubusercontent.com/giosg/docker-tools/master/wait_for /usr/local/bin/wait_for
RUN chmod +x /usr/local/bin/wait_for
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
