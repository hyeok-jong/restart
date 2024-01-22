# restart  



When have no permission to connect via ssh, making specific file can restart the docker by runing the code background.  

```
echo "$(date) - started!"

while true; do
    if [ -f "do.txt" ]; then
        docker restart 821f47005f75
        echo "$(date) - restarted!"
    fi

    sleep 10m
done
```

Of course the code should be run on the server via ssh at the first time.  

Then, run by `nohup bash restart_lhj.sh &` and check `ps -ef | grep *lhj*`.  

Once it runs on the server, one can activate the restart code line by just making do.txt file in the docker evn.  

i.e) restart the docker inside the docker
