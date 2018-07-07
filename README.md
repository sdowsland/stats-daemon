# Stats daemon #

This is a project to try and create a really lightweight stats daemon

For example to collect memory stats you can run:

```
echo {\"date\": \"$(date +"%Y-%m-%dT%T")\", $(free -m | grep Mem: | awk '{print "\"total\": "$2", \"available\":" $6 "}"}')
```

Loggers can also be passed through docker containers via std-in/out

```
echo "Hello world!" | sudo docker run -i  ubuntu cat 
```